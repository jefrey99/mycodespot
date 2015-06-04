# Control Script for Agilent/HP E3632A #

This script works great for logging the power and calculating the energy used during the execution of a static workload.



## Details ##


```
#### Control Script for Agilent/HP E3632A ############
# Jeffrey Eastlack - "Last Name"@gmail.com
#!/usr/bin/perl

use Device::SerialPort; 

my $port = new Device::SerialPort("/dev/ttyS0") || die "can't open ttyS0\n";

$port->baudrate(9600);
$port->parity("none");
$port->handshake("none");
$port->databits(8);
$port->stopbits(2);
$port->read_char_time(0);
$port->read_const_time(1);

### DEBUG Variables
#  Set DEBUG to 1 to print all of the debug statements
my $HP_DBG = 1;   my $DEBUG = 1;
my $delay;
if ($DEBUG){ print "Power Log Started\nCurrent,\tTime\n";}



####  Control Agilent/HP E3632A ############
&send_cmd('*RST');		  # reset
&send_cmd('SYSTem:REMote');	  # remote control necessary for rs232 control


#&send_cmd("VOLTage:RANGe P30V"); # Use this supply for larger voltage / lower current
&send_cmd("VOLTage:RANGe P15V");  # Use this supply for lower voltage / larger current

#&send_cmd("APPL 19.0, 4.0");  #Intel Atom and Core_i3 Set to 19V rated at 4A
&send_cmd("APPL 5.0, 7.0");  #ARM Cortex-A9 Set to 5V rated at 7A
&send_cmd("OUTP ON");		  #turn ON

$current=0;

open DATA_OUT, ">CortexA8_SD2_neon_fftw_current.txt" or die $!;  # open file, erase previous
close DATA_OUT;

while(1){
	open DATA_OUT, ">>CortexA8_SD2_neon_fftw_current.txt" or die $!;  # open file APPEND	
	&send_cmd("MEASure:CURRent?");
	$delay=time+.1;           	#delay to allow read to finish
	while(time<$delay){};	
	$current = $port->lookfor;	# look for data from rs232
	($sec,$min,$hour,$mday,$mon,$year,$wday,$yday,$isdst) = localtime(time);	
	printf DATA_OUT "%f, %d:%d:%d\n",$current,$hour, $min, $sec;
	printf "%f, %d:%d:%d\n",$current,$hour, $min, $sec;
	$current=0;
	close DATA_OUT;
}
if ($DEBUG){ print "TEST ENDED\n";}



## fucntion written assuming $RS232 object was already created
sub send_cmd {
	my $cmd=shift;
	my $delay;
	#$RS232->write_done(0);
	$port->write("$cmd\r\n");
	$delay=time+.05;           #delay to allow command to finish sending
	while(time<$delay){};
}

```