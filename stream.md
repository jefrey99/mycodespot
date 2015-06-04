## Building and running STREAM ##

Notes - On multicore SoC use the -fopenmp flag (like below) to compile the program for multicore memory access. You may need to install the OpenMP librarys.

More info:
http://www.cs.virginia.edu/stream/

```
lucid@lucid-desktop:~/Documents$ gcc -fopenmp -mtune=cortex-a8 -mfpu=neon -o stream stream.c 
lucid@lucid-desktop:~/Documents$ ls
boinc       fftw-3.2.2-neon-1.diff  op           run_oprofile.sh  stream
fftw-3.2.2  fftw-3.2.2.tar.gz       oprofile.sh  seti_boinc       stream.c
lucid@lucid-desktop:~/Documents$ ./stream 
-------------------------------------------------------------
STREAM version $Revision: 5.9 $
-------------------------------------------------------------
This system uses 8 bytes per DOUBLE PRECISION word.
-------------------------------------------------------------
Array size = 2000000, Offset = 0
Total memory required = 45.8 MB.
Each test is run 10 times, but only
the *best* time for each is used.
-------------------------------------------------------------
Number of Threads requested = 1
-------------------------------------------------------------
Printing one line per active thread....
-------------------------------------------------------------
Your clock granularity/precision appears to be 2 microseconds.
Each test below will take on the order of 124891 microseconds.
   (= 62445 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function      Rate (MB/s)   Avg time     Min time     Max time
Copy:         345.0247       0.0930       0.0927       0.0938
Scale:        302.2316       0.1065       0.1059       0.1076
Add:          301.2221       0.1597       0.1594       0.1602
Triad:        291.7895       0.1649       0.1645       0.1659
-------------------------------------------------------------
Solution Validates
-------------------------------------------------------------
lucid@lucid-desktop:~/Documents$ 

```

On