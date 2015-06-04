# Accessing the ARM Performance Monitoring Unit (PMU) #
This code examples shows how to access and setup the performance monitoring unit. The files v7\_pmu.S and v7\_pmu.h were originally downloaded from arm.com but modified by me to be GCC friendly.


### v7\_pmu.h ###
PMU Access Functions
```
// ------------------------------------------------------------
// PMU for Cortex-A/R (v7-A/R)
// ------------------------------------------------------------

#ifndef _V7_PMU_H
#define _V7_PMU_H

// Returns the number of progammable counters
unsigned int getPMN(void);

// Sets the event for a programmable counter to record
// counter = r0 = Which counter to program  (e.g. 0 for PMN0, 1 for PMN1)
// event   = r1 = The event code (from appropiate TRM or ARM Architecture Reference Manual)
void pmn_config(unsigned int counter, unsigned int event);

// Enables/disables the divider (1/64) on CCNT
// divider = r0 = If 0 disable divider, else enable dvider
void ccnt_divider(int divider);

//
// Enables and disables
//

// Global PMU enable
// On ARM11 this enables the PMU, and the counters start immediately
// On Cortex this enables the PMU, there are individual enables for the counters
void enable_pmu(void);

// Global PMU disable
// On Cortex, this overrides the enable state of the individual counters
void disable_pmu(void);

// Enable the CCNT
void enable_ccnt(void);

// Disable the CCNT
void disable_ccnt(void);

// Enable PMN{n}
// counter = The counter to enable (e.g. 0 for PMN0, 1 for PMN1)
void enable_pmn(unsigned int counter);

// Enable PMN{n}
// counter = The counter to enable (e.g. 0 for PMN0, 1 for PMN1)
void disable_pmn(unsigned int counter);

//
// Read counter values
//

// Returns the value of CCNT
unsigned int read_ccnt(void);

// Returns the value of PMN{n}
// counter = The counter to read (e.g. 0 for PMN0, 1 for PMN1)
unsigned int read_pmn(unsigned int counter);

//
// Overflow and interrupts
//

// Returns the value of the overflow flags
unsigned int read_flags(void);

// Writes the overflow flags
void write_flags(unsigned int flags);

// Enables interrupt generation on overflow of the CCNT
void enable_ccnt_irq(void);

// Disables interrupt generation on overflow of the CCNT
void disable_ccnt_irq(void);

// Enables interrupt generation on overflow of PMN{x}
// counter = The counter to enable the interrupt for (e.g. 0 for PMN0, 1 for PMN1)
void enable_pmn_irq(unsigned int counter);

// Disables interrupt generation on overflow of PMN{x}
// counter = r0 =  The counter to disable the interrupt for (e.g. 0 for PMN0, 1 for PMN1)
void disable_pmn_irq(unsigned int counter);

//
// Counter reset functions
//

// Resets the programmable counters
void reset_pmn(void);

// Resets the CCNT
void reset_ccnt(void);

//
// Software Increment

// Writes to software increment register
// counter = The counter to increment (e.g. 0 for PMN0, 1 for PMN1)
void pmu_software_increment(unsigned int counter);

//
// User mode access
//

// Enables User mode access to the PMU (must be called in a priviledged mode)
void enable_pmu_user_access(void);

// Disables User mode access to the PMU (must be called in a priviledged mode)
void disable_pmu_user_access(void);

#endif
// ------------------------------------------------------------
// End of v7_pmu.h
// ------------------------------------------------------------
```

### v7\_pmu.S ###
This assembly code file access the unit via CP14
```
/*------------------------------------------------------------
Performance Monitor Block	
------------------------------------------------------------*/
    .arm  @ Make sure we are in ARM mode.
    .text
    .align 2
    .global getPMN @ export this function for the linker

/*  Returns the number of progammable counters uint32_t getPMN(void) */

getPMN:
  MRC     p15, 0, r0, c9, c12, 0 /* Read PMNC Register	*/
  MOV     r0, r0, LSR #11        /* Shift N field down to bit 0	*/
  AND     r0, r0, #0x1F          /* Mask to leave just the 5 N bits	*/
  BX      lr

  

    .global pmn_config @ export this function for the linker
  /* Sets the event for a programmable counter to record	*/
  /* void pmn_config(unsigned counter, uint32_t event)	*/
  /* counter = r0 = Which counter to program  (e.g. 0 for PMN0, 1 for PMN1)	*/
  /* event   = r1 = The event code	*/
pmn_config:
  AND     r0, r0, #0x1F          /* Mask to leave only bits 4:0	*/
  MCR     p15, 0, r0, c9, c12, 5 /* Write PMNXSEL Register	*/
  MCR     p15, 0, r1, c9, c13, 1 /* Write EVTSELx Register	*/
  BX      lr

  

    .global ccnt_divider @ export this function for the linker
  /* Enables/disables the divider (1/64) on CCNT	*/
  /* void ccnt_divider(int divider)	*/
  /* divider = r0 = If 0 disable divider, else enable dvider	*/
ccnt_divider:
  MRC     p15, 0, r1, c9, c12, 0  /* Read PMNC	*/

  CMP     r0, #0x0                /* IF (r0 == 0)	*/
  BICEQ   r1, r1, #0x08           /* THEN: Clear the D bit (disables the divisor)	*/
  ORRNE   r1, r1, #0x08           /* ELSE: Set the D bit (enables the divisor)	*/

  MCR     p15, 0, r1, c9, c12, 0  /* Write PMNC	*/
  BX      lr
 

  /* ---------------------------------------------------------------	*/
  /* Enable/Disable	*/
  /* ---------------------------------------------------------------	*/

    .global enable_pmu @ export this function for the linker
  /* Global PMU enable	*/
  /* void enable_pmu(void)	*/
enable_pmu:
  MRC     p15, 0, r0, c9, c12, 0  /* Read PMNC	*/
  ORR     r0, r0, #0x01           /* Set E bit	*/
  MCR     p15, 0, r0, c9, c12, 0  /* Write PMNC	*/
  BX      lr
 


    .global disable_pmu @ export this function for the linker
  /* Global PMU disable	*/
  /* void disable_pmu(void)	*/
disable_pmu:
  MRC     p15, 0, r0, c9, c12, 0  /* Read PMNC	*/
  BIC     r0, r0, #0x01           /* Clear E bit	*/
  MCR     p15, 0, r0, c9, c12, 0  /* Write PMNC	*/
  BX      lr
 
  

    .global enable_ccnt @ export this function for the linker
  /* Enable the CCNT	*/
  /* void enable_ccnt(void)	*/
enable_ccnt:
  MOV     r0, #0x80000000         /* Set C bit	*/
  MCR     p15, 0, r0, c9, c12, 1  /* Write CNTENS Register	*/
  BX      lr
 
  

    .global disable_ccnt @ export this function for the linker
  /* Disable the CCNT	*/
  /* void disable_ccnt(void)	*/
disable_ccnt:
  MOV     r0, #0x80000000         /* Clear C bit	*/
  MCR     p15, 0, r0, c9, c12, 2  /* Write CNTENC Register	*/
  BX      lr
 
  

    .global enable_pmn @ export this function for the linker
  /* Enable PMN{n}	*/
  /* void enable_pmn(uint32_t counter)	*/
  /* counter = r0 = The counter to enable (e.g. 0 for PMN0, 1 for PMN1)	*/
enable_pmn:
  MOV     r1, #0x1                /* Use arg (r0) to set which counter to disable	*/
  MOV     r1, r1, LSL r0

  MCR     p15, 0, r1, c9, c12, 1  /* Write CNTENS Register	*/
  BX      lr

  

    .global disable_pmn @ export this function for the linker
  /* Enable PMN{n}	*/
  /* void disable_pmn(uint32_t counter)	*/
  /* counter = r0 = The counter to enable (e.g. 0 for PMN0, 1 for PMN1)	*/
disable_pmn:
  MOV     r1, #0x1                /* Use arg (r0) to set which counter to disable	*/
  MOV     r1, r1, LSL r0

  MCR     p15, 0, r1, c9, c12, 1  /* Write CNTENS Register	*/
  BX      lr
 
  
  
    .global enable_pmu_user_access @ export this function for the linker
  /* Enables User mode access to the PMU (must be called in a priviledged mode)	*/
  /* void enable_pmu_user_access(void)	*/
enable_pmu_user_access:
  MRC     p15, 0, r0, c9, c14, 0  /* Read PMUSERENR Register	*/
  ORR     r0, r0, #0x01           /* Set EN bit (bit 0)	*/
  MCR     p15, 0, r0, c9, c14, 0  /* Write PMUSERENR Register	*/
  BX      lr
  
  
  
    .global disable_pmu_user_access @ export this function for the linker
  /* Disables User mode access to the PMU (must be called in a priviledged mode)	*/
  /* void disable_pmu_user_access(void)	*/
disable_pmu_user_access:
  MRC     p15, 0, r0, c9, c14, 0  /* Read PMUSERENR Register	*/
  BIC     r0, r0, #0x01           /* Clear EN bit (bit 0)	*/
  MCR     p15, 0, r0, c9, c14, 0  /* Write PMUSERENR Register	*/
  BX      lr


  /* ---------------------------------------------------------------	*/
  /* Counter read registers	*/
  /* ---------------------------------------------------------------	*/

    .global read_ccnt @ export this function for the linker
  /* Returns the value of CCNT	*/
  /* uint32_t read_ccnt(void)	*/
read_ccnt:
  MRC     p15, 0, r0, c9, c13, 0 /* Read CCNT Register	*/
  BX      lr


    .global read_pmn @ export this function for the linker
  /* Returns the value of PMN{n}	*/
  /* uint32_t read_pmn(uint32_t counter)	*/
  /* counter = r0 =  The counter to read (e.g. 0 for PMN0, 1 for PMN1)	*/
read_pmn:
  AND     r0, r0, #0x1F          /* Mask to leave only bits 4:0	*/
  MCR     p15, 0, r0, c9, c12, 5 /* Write PMNXSEL Register	*/
  MRC     p15, 0, r0, c9, c13, 2 /* Read current PMNx Register	*/
  BX      lr
  
  
  /* ---------------------------------------------------------------	*/
  /* Software Increment	*/
  /* ---------------------------------------------------------------	*/

    .global pmu_software_increment @ export this function for the linker
	/* Writes to software increment register	*/
	/* void pmu_software_increment(uint32_t counter)	*/
	/* counter = r0 =  The counter to increment (e.g. 0 for PMN0, 1 for PMN1)	*/
pmu_software_increment:
  MOV     r1, #0x01
  MOV			r1, r1, LSL r0
  MCR     p15, 0, r1, c9, c12, 4 /* Write SWINCR Register	*/
  BX      lr

  /* ---------------------------------------------------------------	*/
  /* Overflow & Interrupt Generation	*/
  /* ---------------------------------------------------------------	*/

    .global read_flags @ export this function for the linker
  /* Returns the value of the overflow flags	*/
  /* uint32_t read_flags(void)	*/
read_flags:
  MRC     p15, 0, r0, c9, c12, 3 /* Read FLAG Register	*/
  BX      lr
  

    .global write_flags @ export this function for the linker
  /* Writes the overflow flags	*/
  /* void write_flags(uint32_t flags)	*/
write_flags:
  MCR     p15, 0, r0, c9, c12, 3 /* Write FLAG Register	*/
  BX      lr
  

    .global enable_ccnt_irq @ export this function for the linker
  /* Enables interrupt generation on overflow of the CCNT	*/
  /* void enable_ccnt_irq(void)	*/
enable_ccnt_irq:
  MOV     r0, #0x80000000
  MCR     p15, 0, r0, c9, c14, 1  /* Write INTENS Register	*/
  BX      lr

    .global disable_ccnt_irq @ export this function for the linker
  /* Disables interrupt generation on overflow of the CCNT	*/
  /* void disable_ccnt_irq(void)	*/
disable_ccnt_irq:
  MOV     r0, #0x80000000
  MCR     p15, 0, r0, c9, c14, 2   /* Write INTENC Register	*/
  BX      lr
  

    .global enable_pmn_irq @ export this function for the linker
  /* Enables interrupt generation on overflow of PMN{x}	*/
  /* void enable_pmn_irq(uint32_t counter)	*/
  /* counter = r0 =  The counter to enable the interrupt for (e.g. 0 for PMN0, 1 for PMN1)	*/
enable_pmn_irq:
  MOV     r1, #0x1                 /* Use arg (r0) to set which counter to disable	*/
  MOV     r0, r1, LSL r0
  MCR     p15, 0, r0, c9, c14, 1   /* Write INTENS Register	*/
  BX      lr

    .global disable_pmn_irq @ export this function for the linker
  /* Disables interrupt generation on overflow of PMN{x}	*/
  /* void disable_pmn_irq(uint32_t counter)	*/
  /* counter = r0 =  The counter to disable the interrupt for (e.g. 0 for PMN0, 1 for PMN1)	*/
disable_pmn_irq:
  MOV     r1, #0x1                /* Use arg (r0) to set which counter to disable	*/
  MOV     r0, r1, LSL r0
  MCR     p15, 0, r0, c9, c14, 2  /* Write INTENC Register	*/
  BX      lr

  /* ---------------------------------------------------------------	*/
  /* Reset Functions	*/
  /* ---------------------------------------------------------------	*/

    .global reset_pmn @ export this function for the linker
  /* Resets the programmable counters	*/
  /* void reset_pmn(void)	*/
reset_pmn:
  MRC     p15, 0, r0, c9, c12, 0  /* Read PMNC	*/
  ORR     r0, r0, #0x02           /* Set P bit (Event Counter Reset)	*/
  MCR     p15, 0, r0, c9, c12, 0  /* Write PMNC	*/
  BX      lr


	.global reset_ccnt @ export this function for the linker
  /* Resets the CCNT	*/
  /* void reset_ccnt(void)	*/
reset_ccnt:
  MRC     p15, 0, r0, c9, c12, 0  /* Read PMNC	*/
  ORR     r0, r0, #0x04           /* Set C bit (Event Counter Reset)	*/
  MCR     p15, 0, r0, c9, c12, 0  /* Write PMNC	*/
  BX      lr

 
    .end @end of code, this line is optional.
/* ------------------------------------------------------------	*/
/* End of v7_pmu.s	*/
/* ------------------------------------------------------------	*/
```

### pmu\_matrix\_test.c ###
Use this example to see the performance counter events logged when multiplying a square matrix
```
#include "v7_pmu.h"
#include <stdio.h>
#include <time.h>
#include <stdlib.h>

int random_range(int max);
void pmu_start(unsigned int event0,unsigned int event1,unsigned int event2,unsigned int event3,unsigned int event4,unsigned int event5);
void pmu_stop(void);

int main ( int argc, char *argv[] ){
int matrix_size;
int i,j,k,z;



// To access CPU time
clock_t start, end;
double cpu_time_used;

  if ( argc != 2 ) {
    fputs ( "usage: $prog <square matrix size>\n", stderr );
    exit ( EXIT_FAILURE );
	}

    matrix_size = (int)strtol(argv[1],NULL,10);


printf("square matrix size = %d\n", matrix_size);


/*Using time function output for seed value*/
	unsigned int seed = (unsigned int)time(NULL);
  	srand(seed);

/* Initialize square matrix with command line input value */
int a[matrix_size][matrix_size], b[matrix_size][matrix_size], c[matrix_size][matrix_size];

/* Intialize both A[][] and B[][] with random values between 0-5 and set C[][] to zero*/
	for(i=0;i<matrix_size;i++){
		for(j=0;j<matrix_size;j++){
		a[i][j]=random_range(6);
		b[i][j]=random_range(6);
		c[i][j]=0;
		}
	}

/* Multiply A[][] and B[][] and store into C[][]*/
 start = clock();



for(z=0;z<7;z++){
	if(z==0)
	pmu_start(0x01,0x02,0x03,0x04,0x05,0x06);
	if(z==1)
	pmu_start(0x07,0x08,0x09,0x0A,0x0B,0x0C);
	if(z==2)
	pmu_start(0x0D,0x0E,0x0F,0x10,0x11,0x12);
	if(z==3)
	pmu_start(0x50,0x51,0x60,0x61,0x62,0x63);
	if(z==4)
	pmu_start(0x64,0x65,0x66,0x67,0x68,0x6E);
	if(z==5)
	pmu_start(0x70,0x71,0x72,0x73,0x74,0x81);
	if(z==6)
	pmu_start(0x82,0x83,0x84,0x85,0x86,0x8A);

   for(i=0; i<matrix_size; i++)
   {
	 for(j=0; j<matrix_size; j++)
	 {
	    for(k=0; k<matrix_size; k++)
	    {
		  /* c[0][0]=a[0][0]*b[0][0]+a[0][1]*b[1][0]+a[0][2]*b[2][0]; */
		  c[i][j] += a[i][k]*b[k][j];
	    }
	 }
  }

	pmu_stop();

}
    end = clock();
    cpu_time_used = (end - start) / ((double) CLOCKS_PER_SEC);

printf("CPU time used = %.4lf\n",cpu_time_used);
printf("square matrix size = %d\n", matrix_size);


  return 0;
}

int random_range(int max){
    return ((rand()%(max-1)) +1);
}



void pmu_start(unsigned int event0,unsigned int event1,unsigned int event2,unsigned int event3,unsigned int event4,unsigned int event5){

  enable_pmu();              // Enable the PMU
  reset_ccnt();              // Reset the CCNT (cycle counter)
  reset_pmn();               // Reset the configurable counters
  pmn_config(0, event0);       // Configure counter 0 to count event code 0x03
  pmn_config(1, event1);       // Configure counter 1 to count event code 0x03
  pmn_config(2, event2);       // Configure counter 2 to count event code 0x03
  pmn_config(3, event3);       // Configure counter 3 to count event code 0x03
  pmn_config(4, event4);       // Configure counter 4 to count event code 0x03
  pmn_config(5, event5);       // Configure counter 5 to count event code 0x03

  enable_ccnt();             // Enable CCNT
  enable_pmn(0);             // Enable counter
  enable_pmn(1);             // Enable counter
  enable_pmn(2);             // Enable counter
  enable_pmn(3);             // Enable counter
  enable_pmn(4);             // Enable counter
  enable_pmn(5);             // Enable counter

  printf("CountEvent0=0x%x,CountEvent1=0x%x,CountEvent2=0x%x,CountEvent3=0x%x,CountEvent4=0x%x,CountEvent5=0x%x\n", event0,event1,event2,event3,event4,event5);
}

void pmu_stop(void){
  unsigned int cycle_count, overflow, counter0, counter1, counter2, counter3, counter4, counter5;

  disable_ccnt();            // Stop CCNT
  disable_pmn(0);            // Stop counter 0
  disable_pmn(1);            // Stop counter 1
  disable_pmn(2);            // Stop counter 2
  disable_pmn(3);            // Stop counter 3
  disable_pmn(4);            // Stop counter 4
  disable_pmn(5);            // Stop counter 5

  counter0    = read_pmn(0); // Read counter 0
  counter1    = read_pmn(1); // Read counter 1
  counter2    = read_pmn(2); // Read counter 2
  counter3    = read_pmn(3); // Read counter 3
  counter4    = read_pmn(4); // Read counter 4
  counter5    = read_pmn(5); // Read counter 5

  cycle_count = read_ccnt(); // Read CCNT
  overflow=read_flags();	//Check for overflow flag

  printf("Counter0=%d,Counter1=%d,Counter2=%d,Counter3=%d,Counter4=%d,Counter5=%d\n", counter0, counter1,counter2,counter3,counter4,counter5);
  printf("Overflow flag: = %d, Cycle Count: = %d \n\n", overflow,cycle_count);
}
```

### Compile Command ###
```
$ gcc -O3 -mtune=cortex-a9 -mfpu=neon -o  pmu_matrix pmu_matrix_test.c v7_pmu.S -lm
```