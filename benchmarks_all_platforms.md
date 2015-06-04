# Benchmark results #



## i.MX53 - Cortex-A8 ##
Stream
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
### Linpack ###
```
lucid@lucid-desktop:~/Documents$ gcc -DSP -DROLL -mtune=cortex-a8 -mfpu=neon -o linpack_dsp_droll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_dsp_droll 
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.37
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      36140       0.06       0.34
Rolled Single  Precision 32698 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$ gcc -DSP -DUNROLL -mtune=cortex-a8 -mfpu=neon -o linpack_dsp_dunroll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_dsp_dunroll 
Unrolled Single Precision Linpack

Unrolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
 times for array with leading dimension of 200
       0.02       0.01       0.03      22889       0.09       0.54
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.37
Unrolled Single  Precision 32698 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$ gcc -DDP -DUNROLL -mtune=cortex-a8 -mfpu=neon -o linpack_ddp_dunroll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_ddp_dunroll 
Unrolled Double Precision Linpack

Unrolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
 times for array with leading dimension of 200
       0.02       0.01       0.03      22889       0.09       0.54
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
Unrolled Double  Precision 34333 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$ gcc -DDP -DROLL -mtune=cortex-a8 -mfpu=neon -o linpack_ddp_droll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_ddp_droll 
Rolled Double Precision Linpack

Rolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.37
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      38148       0.05       0.32
Rolled Double  Precision 32698 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$

```

### Whetstone ###
```
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a8 -mfpu=neon -o whetstone whetstone.c -lm

Loops: 100000, Iterations: 1, Duration: 55 sec.
C Converted Double Precision Whetstones: 181.8 MIPS
lucid@lucid-desktop:~/Documents$ 
```

### Dhrystone ###
```
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a8 -mfpu=neon -o dry1.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a8 -mfpu=neon -DPASS2 dry.c dry1.o -o dry2
lucid@lucid-desktop:~/Documents$ ./dry2 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled without 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          1486856
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          1486856
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.9 
Dhrystones per Second:                         1057082 

lucid@lucid-desktop:~/Documents$ 


```

```
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a8 -mfpu=neon -DREG -o dry2.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a8 -mfpu=neon -DPASS2 -DREG dry.c dry2.o -o dry2nr
lucid@lucid-desktop:~/Documents$ ./dry2nr 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled with 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          31600648
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          31600648
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.9 
Dhrystones per Second:                         1168224 

lucid@lucid-desktop:~/Documents$
```




## 4x CA9 Versatile ##

### stream versatile ###

```
user41@ca9-natty:~$ gcc -fopenmp -mtune=cortex-a9 -mfpu=neon -o stream stream.c
user41@ca9-natty:~$ ./stream 
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
Number of Threads requested = 4
-------------------------------------------------------------
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
-------------------------------------------------------------
Your clock granularity/precision appears to be 3 microseconds.
Each test below will take on the order of 94007 microseconds.
   (= 31335 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function      Rate (MB/s)   Avg time     Min time     Max time
Copy:         356.8956       0.0897       0.0897       0.0899
Scale:        375.8653       0.0854       0.0851       0.0865
Add:          379.1383       0.1267       0.1266       0.1271
Triad:        331.7666       0.1447       0.1447       0.1448
-------------------------------------------------------------
Solution Validates
-------------------------------------------------------------
user41@ca9-natty:~$ 

```

### linpack versatile ###

```

user41@ca9-natty:~$ gcc -DSP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_droll linpackc.c -lm
user41@ca9-natty:~$ ./linpack_dsp_droll 
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.38
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.37
Rolled Single  Precision 32698 Kflops ; 10 Reps 

user41@ca9-natty:~$ gcc -DSP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_droll linpackc.c -lm
user41@ca9-natty:~$ ./linpack_dsp_droll Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.01       0.00       0.01      68667       0.03       0.18
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.38
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      29855       0.07       0.41
Rolled Single  Precision 29855 Kflops ; 10 Reps 
user41@ca9-natty:~$ ./linpack_dsp_droll 
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.37
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.38
Rolled Single  Precision 32698 Kflops ; 10 Reps 
user41@ca9-natty:~$ gcc -DSP -DUNROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_dunroll linpackc.c -lm
user41@ca9-natty:~$ ./linpack_dsp_dunroll 
Unrolled Single Precision Linpack

Unrolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      68667       0.03       0.18
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      40392       0.05       0.30
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      40392       0.05       0.30
Unrolled Single  Precision 40392 Kflops ; 10 Reps 
user41@ca9-natty:~$ gcc -DDP -DUNROLL -mtune=cortex-a9 -mfpu=neon -o linpack_ddp_dunroll linpackc.c -lm
user41@ca9-natty:~$ ./linpack_ddp_dunroll
Unrolled Double Precision Linpack

Unrolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.02       0.00       0.02      42917       0.05       0.29
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.01       0.00       0.02      42917       0.05       0.29
Unrolled Double  Precision 42917 Kflops ; 10 Reps 
user41@ca9-natty:~$ gcc -DDP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_ddp_droll linpackc.c -lm
user41@ca9-natty:~$ ./linpack_ddp_droll
Rolled Double Precision Linpack

Rolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.02       0.00       0.02      34333       0.06       0.36
       0.01       0.00       0.01      68667       0.03       0.18
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      31212       0.06       0.39
 times for array with leading dimension of 200
       0.01       0.00       0.01      68667       0.03       0.18
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      32698       0.06       0.37
Rolled Double  Precision 31212 Kflops ; 10 Reps 
user41@ca9-natty:~$ 


```

### whetstone versatile ###

```
user41@ca9-natty:~$ gcc -mtune=cortex-a9 -mfpu=neon -o whetstone whetstone.c -lmuser41@ca9-natty:~$ ./whetstone 10000

Loops: 10000, Iterations: 1, Duration: 4 sec.
C Converted Double Precision Whetstones: 250.0 MIPS
user41@ca9-natty:~$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 41 sec.
C Converted Double Precision Whetstones: 243.9 MIPS


```

### dhrystone versatile ###
```
user41@ca9-natty:~$ gcc -mtune=cortex-a9 -mfpu=neon -o dry1.o -c dry.c
dry.c:503:18: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549:6: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572:3: warning: incompatible implicit declaration of built-in function ‘strcpy’
user41@ca9-natty:~$ gcc -mtune=cortex-a9 -mfpu=neon -DPASS2 dry.c dry1.o -o dry2user41@ca9-natty:~$ ./dry2 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled without 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          90120
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          90120
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        1.7 
Dhrystones per Second:                          585480 

user41@ca9-natty:~$ gcc -mtune=cortex-a9 -mfpu=neon -DREG -o dry2.o -c dry.c
dry.c:503:18: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549:6: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572:3: warning: incompatible implicit declaration of built-in function ‘strcpy’
user41@ca9-natty:~$ gcc -mtune=cortex-a9 -mfpu=neon -DPASS2 -DREG dry.c dry2.o -o dry2nr
user41@ca9-natty:~$ ./dry2nr

Dhrystone Benchmark, Version C, Version 2.2
Program compiled with 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          90120
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          90120
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        1.4 
Dhrystones per Second:                          712251 

user41@ca9-natty:~$ 


```


## 4xCA9 @1GHz ##

```
mw 0x020c8140 0x007C3E1F   --- command to raise the core voltage
clk core 1008   --- increase the core frequency
```

### stream ###
```
lucid@lucid-desktop:~/Documents$ gcc -fopenmp -mtune=cortex-a9 -mfpu=neon -o stream stream.c
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
Number of Threads requested = 4
-------------------------------------------------------------
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
-------------------------------------------------------------
Your clock granularity/precision appears to be 1 microseconds.
Each test below will take on the order of 23661 microseconds.
   (= 23661 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function      Rate (MB/s)   Avg time     Min time     Max time
Copy:        1322.9156       0.0245       0.0242       0.0250
Scale:       1245.4783       0.0261       0.0257       0.0268
Add:         1550.1328       0.0312       0.0310       0.0318
Triad:       1481.9880       0.0329       0.0324       0.0337
-------------------------------------------------------------
Solution Validates
-------------------------------------------------------------
lucid@lucid-desktop:~/Documents$ 
```

### linpack ###

```
lucid@lucid-desktop:~/Documents$ gcc -DSP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_droll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_dsp_droll
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00        inf       0.00       0.00
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.01       0.02      34333       0.06       0.36
       0.01       0.00       0.01      68667       0.03       0.18
 times for array with leading dimension of 200
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
Rolled Single  Precision 68667 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$ gcc -DSP -DUNROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_dunroll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_dsp_dunroll
Unrolled Single Precision Linpack

Unrolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00        inf       0.00       0.00
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
 times for array with leading dimension of 200
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      85833       0.02       0.14
Unrolled Single  Precision 68667 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$ gcc -DDP -DUNROLL -mtune=cortex-a9 -mfpu=neon -o linpack_ddp_dunroll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_ddp_dunroll 
Unrolled Double Precision Linpack

Unrolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00        inf       0.00       0.00
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
 times for array with leading dimension of 200
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      68667       0.03       0.18
Unrolled Double  Precision 68667 Kflops ; 10 Reps 

lucid@lucid-desktop:~/Documents$ gcc -DDP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_ddp_droll linpackc.c -lm
lucid@lucid-desktop:~/Documents$ ./linpack_ddp_droll
Rolled Double Precision Linpack

Rolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      68667       0.03       0.18
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.01       0.00       0.01      52821       0.04       0.23
 times for array with leading dimension of 200
       0.02       0.00       0.02      34333       0.06       0.36
       0.02       0.00       0.02      34333       0.06       0.36
       0.01       0.00       0.01      68667       0.03       0.18
       0.01       0.00       0.01      62424       0.03       0.20
Rolled Double  Precision 52821 Kflops ; 10 Reps 
lucid@lucid-desktop:~/Documents$
```

### whetstone ###

```
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a9 -mfpu=neon -o whetstone whetstone.c -lm
lucid@lucid-desktop:~/Documents$ ./whetstone 10000

Loops: 10000, Iterations: 1, Duration: 2 sec.
C Converted Double Precision Whetstones: 500.0 MIPS

```
### dhrystone ###
```
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a9 -mfpu=neon -o dry1.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a9 -mfpu=neon -DPASS2 dry.c dry1.o -o dry2
lucid@lucid-desktop:~/Documents$ ./dry2 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled without 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          86024
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          86024
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.9 
Dhrystones per Second:                         1126126 
```
```
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a9 -mfpu=neon -DREG -o dry2.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
lucid@lucid-desktop:~/Documents$ gcc -mtune=cortex-a9 -mfpu=neon -DPASS2 -DREG dry.c dry2.o -o dry2nr
lucid@lucid-desktop:~/Documents$ ./dry2nr 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled with 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          86024
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          86024
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.8 
Dhrystones per Second:                         1291990 

lucid@lucid-desktop:~/Documents$ 

```



## OMAP4430 Pandaboard ##
### stream ###
```

jeff@CortexA9x2:~/stuff$ gcc -fopenmp -mtune=cortex-a9 -mfpu=neon -o stream stream.c
jeff@CortexA9x2:~/stuff$ ./stream 
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
Number of Threads requested = 2
-------------------------------------------------------------
Printing one line per active thread....
Printing one line per active thread....
-------------------------------------------------------------
Your clock granularity/precision appears to be 29 microseconds.
Each test below will take on the order of 78461 microseconds.
   (= 2705 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function      Rate (MB/s)   Avg time     Min time     Max time
Copy:         459.3021       0.0712       0.0697       0.0726
Scale:        430.9821       0.0772       0.0742       0.0903
Add:          587.7668       0.0838       0.0817       0.0846
Triad:        350.4593       0.1381       0.1370       0.1394
-------------------------------------------------------------
Solution Validates
-------------------------------------------------------------
jeff@CortexA9x2:~/stuff$ 
```
### linpack ###
```
jeff@CortexA9x2:~/stuff$ gcc -DSP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_droll linpackc.c -lm
jeff@CortexA9x2:~/stuff$ ./linpack_dsp_droll 
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      58596       0.03       0.21
 times for array with leading dimension of 200
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      87888       0.02       0.14
       0.02       0.00       0.02      43947       0.05       0.28
       0.01       0.00       0.01      62781       0.03       0.20
Rolled Single  Precision 58596 Kflops ; 10 Reps 
jeff@CortexA9x2:~/stuff$ gcc -DSP -DUNROLL -mtune=cortex-a9 -mfpu=neon -o linpack_dsp_dunroll linpackc.c -lm
jeff@CortexA9x2:~/stuff$ ./linpack_dsp_dunroll
Unrolled Single Precision Linpack

Unrolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.6        3.80277634e-05  1.19209290e-07 -1.38282776e-05 -7.51018524e-06
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      79903       0.03       0.15
 times for array with leading dimension of 200
       0.01       0.00       0.01      87899       0.02       0.14
       0.02       0.00       0.02      43947       0.05       0.28
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      73244       0.03       0.17
Unrolled Single  Precision 73244 Kflops ; 10 Reps 
jeff@CortexA9x2:~/stuff$ gcc -DDP -DUNROLL -mtune=cortex-a9 -mfpu=neon -o linpack_ddp_dunroll linpackc.c -lm
jeff@CortexA9x2:~/stuff$ ./linpack_ddp_dunroll
Unrolled Double Precision Linpack

Unrolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      73245       0.03       0.17
 times for array with leading dimension of 200
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87893       0.02       0.14
Unrolled Double  Precision 73245 Kflops ; 10 Reps 
jeff@CortexA9x2:~/stuff$ gcc -DDP -DROLL -mtune=cortex-a9 -mfpu=neon -o linpack_ddp_droll linpackc.c -lm
jeff@CortexA9x2:~/stuff$ ./linpack_ddp_droll
Rolled Double Precision Linpack

Rolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.7        7.41628980e-14  2.22044605e-16 -1.49880108e-14 -1.89848137e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.00       0.01      87899       0.02       0.14
       0.02       0.00       0.02      43947       0.05       0.28
       0.01       0.00       0.01      62780       0.03       0.20
 times for array with leading dimension of 200
       0.01       0.00       0.01      87899       0.02       0.14
       0.01       0.01       0.02      43947       0.05       0.28
       0.01       0.00       0.01      87888       0.02       0.14
       0.01       0.00       0.01      62782       0.03       0.20
Rolled Double  Precision 62780 Kflops ; 10 Reps 
jeff@CortexA9x2:~/stuff$
```
### whetstone ###
```
jeff@CortexA9x2:~/stuff$ gcc -mtune=cortex-a9 -mfpu=neon -o whetstone whetstone.c -lm
jeff@CortexA9x2:~/stuff$ ./whetstone 10000

Loops: 10000, Iterations: 1, Duration: 3 sec.
C Converted Double Precision Whetstones: 333.3 MIPS
jeff@CortexA9x2:~/stuff$ ./whetstone 10000

Loops: 10000, Iterations: 1, Duration: 2 sec.
C Converted Double Precision Whetstones: 500.0 MIPS
jeff@CortexA9x2:~/stuff$ ./whetstone 10000

Loops: 10000, Iterations: 1, Duration: 3 sec.
C Converted Double Precision Whetstones: 333.3 MIPS
jeff@CortexA9x2:~/stuff$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 22 sec.
C Converted Double Precision Whetstones: 454.5 MIPS
jeff@CortexA9x2:~/stuff$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 22 sec.
C Converted Double Precision Whetstones: 454.5 MIPS
jeff@CortexA9x2:~/stuff$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 21 sec.
C Converted Double Precision Whetstones: 476.2 MIPS
jeff@CortexA9x2:~/stuff$ 
```
### dhrystone ###
```
jeff@CortexA9x2:~/stuff$ gcc -mtune=cortex-a9 -mfpu=neon -o dry1.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
jeff@CortexA9x2:~/stuff$ gcc -mtune=cortex-a9 -mfpu=neon -DPASS2 dry.c dry1.o -o dry2
jeff@CortexA9x2:~/stuff$ ./dry2 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled without 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          6045704
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          6045704
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.8 
Dhrystones per Second:                         1231527 

jeff@CortexA9x2:~/stuff$ 
```
```
jeff@CortexA9x2:~/stuff$ gcc -mtune=cortex-a9 -mfpu=neon -DREG -o dry2.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
jeff@CortexA9x2:~/stuff$ gcc -mtune=cortex-a9 -mfpu=neon -DPASS2 -DREG dry.c dry2.o -o dry2nr
jeff@CortexA9x2:~/stuff$ ./dry2nr 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled with 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          1736712
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          1736712
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.7 
Dhrystones per Second:                         1440922 

jeff@CortexA9x2:~/stuff$
```

## Intel Atom D525 ##
### stream ###
```
xbmc@atom:~/Documents/test$ gcc -fopenmp -mtune=atom -o stream stream.c
xbmc@atom:~/Documents/test$ ./stream 
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
Number of Threads requested = 4
-------------------------------------------------------------
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
-------------------------------------------------------------
Your clock granularity/precision appears to be 1 microseconds.
Each test below will take on the order of 8820 microseconds.
   (= 8820 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function      Rate (MB/s)   Avg time     Min time     Max time
Copy:        2582.3103       0.0124       0.0124       0.0126
Scale:       2563.9163       0.0126       0.0125       0.0131
Add:         2910.8530       0.0165       0.0165       0.0167
Triad:       2922.9071       0.0166       0.0164       0.0168
-------------------------------------------------------------
Solution Validates
-------------------------------------------------------------
xbmc@atom:~/Documents/test$
```
### linpack ###
```
xbmc@atom:~/Documents/test$ gcc -DSP -DROLL -mtune=atom -o linpack_dsp_droll linpackc.c -lm
xbmc@atom:~/Documents/test$ ./linpack_dsp_droll
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        4.52336171e-05  1.19209290e-07 -1.31130219e-05 -1.30534172e-05
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01      95365       0.02       0.13
 times for array with leading dimension of 200
       0.01       0.00       0.01      85833       0.02       0.14
       0.01       0.00       0.01      85823       0.02       0.14
       0.01       0.00       0.01      85833       0.02       0.14
       0.01       0.00       0.01     107283       0.02       0.11
Rolled Single  Precision 95365 Kflops ; 10 Reps 

xbmc@atom:~/Documents/test$ gcc -DSP -DUNROLL -mtune=atom -o linpack_dsp_dunroll linpackc.c -lm
xbmc@atom:~/Documents/test$ ./linpack_dsp_dunroll
Unrolled Single Precision Linpack

Unrolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        4.52336171e-05  1.19209290e-07 -1.31130219e-05 -1.30534172e-05
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01      95365       0.02       0.13
 times for array with leading dimension of 200
       0.01       0.00       0.01      85833       0.02       0.14
       0.01       0.00       0.01      85823       0.02       0.14
       0.01       0.00       0.01      85833       0.02       0.14
       0.01       0.00       0.01     107283       0.02       0.11
Unrolled Single  Precision 95365 Kflops ; 10 Reps 
xbmc@atom:~/Documents/test$
```

```
xbmc@atom:~/Documents/test$ gcc -DDP -DUNROLL -mtune=atom -o linpack_ddp_dunroll linpackc.c -lm
xbmc@atom:~/Documents/test$ ./linpack_ddp_dunroll
Unrolled Double Precision Linpack

Unrolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        8.39915160e-14  2.22044605e-16 -6.22835117e-14 -4.16333634e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01     107287       0.02       0.11
 times for array with leading dimension of 200
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171624       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01      95364       0.02       0.13
Unrolled Double  Precision 95364 Kflops ; 10 Reps 
xbmc@atom:~/Documents/test$ gcc -DDP -DROLL -mtune=atom -o linpack_ddp_droll linpackc.c -lm
xbmc@atom:~/Documents/test$ ./linpack_ddp_droll
Rolled Double Precision Linpack

Rolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        8.39915160e-14  2.22044605e-16 -6.22835117e-14 -4.16333634e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01     100974       0.02       0.12
 times for array with leading dimension of 200
       0.01       0.00       0.01      85833       0.02       0.14
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01      85833       0.02       0.14
       0.01       0.00       0.01      90345       0.02       0.14
Rolled Double  Precision 90345 Kflops ; 10 Reps 
xbmc@atom:~/Documents/test$
```
### whetstone ###
```
xbmc@atom:~/Documents/test$ gcc -mtune=atom -o whetstone whetstone.c -lm
xbmc@atom:~/Documents/test$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 21 sec.
C Converted Double Precision Whetstones: 476.2 MIPS
xbmc@atom:~/Documents/test$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 21 sec.
C Converted Double Precision Whetstones: 476.2 MIPS

```
### dhrystone ###

```
xbmc@atom:~/Documents/test$ gcc -mtune=atom -o dry1.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
xbmc@atom:~/Documents/test$ gcc -mtune=atom -DPASS2 dry.c dry1.o -o dry2
xbmc@atom:~/Documents/test$ ./dry2 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled without 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          163528712
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          163528712
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.5 
Dhrystones per Second:                         2192982 

xbmc@atom:~/Documents/test$
```
```
xbmc@atom:~/Documents/test$ gcc -mtune=atom -DREG -o dry2.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
xbmc@atom:~/Documents/test$ gcc -mtune=atom -DPASS2 -DREG dry.c dry2.o -o dry2nr
xbmc@atom:~/Documents/test$ ./dry2nr 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled with 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    5550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          135122952
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          135122952
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.4 
Dhrystones per Second:                         2232143 

xbmc@atom:~/Documents/test$
```
## Intel Core i3 330M ##
### stream ###
```

jeff@east:~/boinc$ gcc -fopenmp -mtune=core2 -o stream stream.c
jeff@east:~/boinc$ ./stream 
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
Number of Threads requested = 4
-------------------------------------------------------------
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
Printing one line per active thread....
-------------------------------------------------------------
Your clock granularity/precision appears to be 1 microseconds.
Each test below will take on the order of 11505 microseconds.
   (= 11505 clock ticks)
Increase the size of the arrays if this shows that
you are not getting at least 20 clock ticks per test.
-------------------------------------------------------------
WARNING -- The above is only a rough guideline.
For best results, please be sure you know the
precision of your system timer.
-------------------------------------------------------------
Function      Rate (MB/s)   Avg time     Min time     Max time
Copy:        6753.9059       0.0057       0.0047       0.0121
Scale:       6627.9337       0.0050       0.0048       0.0053
Add:         7414.2533       0.0066       0.0065       0.0069
Triad:       7323.6643       0.0066       0.0066       0.0067
-------------------------------------------------------------
Solution Validates
-------------------------------------------------------------
jeff@east:~/boinc$ 
```

### linpack ###

```
jeff@east:~/boinc$ gcc -DSP -DROLL -mtune=core2 -o linpack_dsp_droll linpackc.c -lm
jeff@east:~/boinc$ ./linpack_dsp_droll 
Rolled Single Precision Linpack

Rolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        4.52336171e-05  1.19209290e-07 -1.31130219e-05 -1.30534172e-05
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.01       0.00       0.01      85833       0.02       0.14
       0.00       0.00       0.00     171624       0.01       0.07
       0.00       0.00       0.00     214570       0.01       0.06
 times for array with leading dimension of 200
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00        inf       0.00       0.00
       0.00       0.00       0.00     214570       0.01       0.06
Rolled Single  Precision 214570 Kflops ; 10 Reps 
jeff@east:~/boinc$ gcc -DSP -DUNROLL -mtune=core2 -o linpack_dsp_dunroll linpackc.c -lm
jeff@east:~/boinc$ ./linpack_dsp_dunroll 
Unrolled Single Precision Linpack

Unrolled Single Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        4.52336171e-05  1.19209290e-07 -1.31130219e-05 -1.30534172e-05
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00        inf       0.00       0.00
       0.00       0.00       0.00     245229       0.01       0.05
 times for array with leading dimension of 200
       0.00       0.00       0.00        inf       0.00       0.00
       0.00       0.00       0.00     171624       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     286099       0.01       0.04
Unrolled Single  Precision 245229 Kflops ; 10 Reps 
jeff@east:~/boinc$ gcc -DDP -DUNROLL -mtune=core2 -o linpack_ddp_dunroll linpackc.c -lm
jeff@east:~/boinc$ ./linpack_ddp_dunroll 
Unrolled Double Precision Linpack

Unrolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        8.39915160e-14  2.22044605e-16 -6.22835117e-14 -4.16333634e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00        inf       0.00       0.00
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     343316       0.01       0.04
 times for array with leading dimension of 200
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171624       0.01       0.07
       0.00       0.00       0.00     245229       0.01       0.05
Unrolled Double  Precision 245229 Kflops ; 10 Reps 
jeff@east:~/boinc$ cc -DDP -DROLL -mtune=core2 -o linpack_ddp_droll linpackc.c -lm
jeff@east:~/boinc$ ./linpack_ddp_droll 
Rolled Double Precision Linpack

Rolled Double Precision Linpack

     norm. resid      resid           machep         x[0]-1        x[n-1]-1
       1.9        8.39915160e-14  2.22044605e-16 -6.22835117e-14 -4.16333634e-14
    times are reported for matrices of order   100
      dgefa      dgesl      total       kflops     unit      ratio
 times for array with leading dimension of  201
       0.01       0.00       0.01      85833       0.02       0.14
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     214570       0.01       0.06
 times for array with leading dimension of 200
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     171667       0.01       0.07
       0.00       0.00       0.00     214570       0.01       0.06
Rolled Double  Precision 214570 Kflops ; 10 Reps 
jeff@east:~/boinc$ 

```
### whetstone ###
```
jeff@east:~/boinc$ gcc -mtune=core2 -o whetstone whetstone.c -lm
jeff@east:~/boinc$ ./whetstone 10000

Loops: 10000, Iterations: 1, Duration: 1 sec.
C Converted Double Precision Whetstones: 1000.0 MIPS
jeff@east:~/boinc$ ./whetstone 100000

Loops: 100000, Iterations: 1, Duration: 8 sec.
C Converted Double Precision Whetstones: 1250.0 MIPS
jeff@east:~/boinc$ 

```

### dhrystone ###

```
jeff@east:~/boinc$ gcc -mtune=core2 -o dry1.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
jeff@east:~/boinc$ gcc -mtune=core2 -DPASS2 dry.c dry1.o -o dry2
jeff@east:~/boinc$ ./dry2 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled without 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 50000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    55550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          165969928
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          165969928
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.2 
Dhrystones per Second:                         4844961 

jeff@east:~/boinc$ 

```

```
jeff@east:~/boinc$  gcc -mtune=core2 -DREG -o dry2.o -c dry.c
dry.c:503: warning: conflicting types for built-in function ‘malloc’
dry.c: In function ‘main’:
dry.c:549: warning: incompatible implicit declaration of built-in function ‘exit’
dry.c:572: warning: incompatible implicit declaration of built-in function ‘strcpy’
jeff@east:~/boinc$ gcc -mtune=core2 -DPASS2 -DREG dry.c dry2.o -o dry2nrjeff@east:~/boinc$ ./dry2nr 

Dhrystone Benchmark, Version C, Version 2.2
Program compiled with 'register' attribute
Using times(), HZ=100

Trying 50000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 500000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 5000000 runs through Dhrystone:
Measured time too small to obtain meaningful results

Trying 50000000 runs through Dhrystone:
Final values of the variables used in the benchmark:

Int_Glob:            5
        should be:   5
Bool_Glob:           1
        should be:   1
Ch_1_Glob:           A
        should be:   A
Ch_2_Glob:           B
        should be:   B
Arr_1_Glob[8]:       7
        should be:   7
Arr_2_Glob[8][7]:    55550010
        should be:   Number_Of_Runs + 10
Ptr_Glob->
  Ptr_Comp:          157024264
        should be:   (implementation-dependent)
  Discr:             0
        should be:   0
  Enum_Comp:         2
        should be:   2
  Int_Comp:          17
        should be:   17
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Next_Ptr_Glob->
  Ptr_Comp:          157024264
        should be:   (implementation-dependent), same as above
  Discr:             0
        should be:   0
  Enum_Comp:         1
        should be:   1
  Int_Comp:          18
        should be:   18
  Str_Comp:          DHRYSTONE PROGRAM, SOME STRING
        should be:   DHRYSTONE PROGRAM, SOME STRING
Int_1_Loc:           5
        should be:   5
Int_2_Loc:           13
        should be:   13
Int_3_Loc:           7
        should be:   7
Enum_Loc:            1
        should be:   1
Str_1_Loc:           DHRYSTONE PROGRAM, 1'ST STRING
        should be:   DHRYSTONE PROGRAM, 1'ST STRING
Str_2_Loc:           DHRYSTONE PROGRAM, 2'ND STRING
        should be:   DHRYSTONE PROGRAM, 2'ND STRING

Microseconds for one run through Dhrystone:        0.2 
Dhrystones per Second:                         6180470 

jeff@east:~/boinc$ 
```