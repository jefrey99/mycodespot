# PMU events for the Cortex-A8 #

```
lucid@lucid-desktop:~$ sudo opcontrol --list-events                             
[sudo] password for lucid:                                                      
oprofile: available events for CPU type "ARM V7 PMNC"                           
                                                                                
See ARM11 Technical Reference Manual                                            
Cortex A8 DDI (ARM DDI 0344B, revision r1p1)                                    
PMNC_SW_INCR: (counter: 1, 2, 3, 4)                                             
        Software increment of PMNC registers (min count: 500)                   
IFETCH_MISS: (counter: 1, 2, 3, 4)                                              
        Instruction fetch misses from cache or normal cacheable memory (min cou 
ITLB_MISS: (counter: 1, 2, 3, 4)                                                
        Instruction fetch misses from TLB (min count: 500)                      
DCACHE_REFILL: (counter: 1, 2, 3, 4)                                            
        Data R/W operation that causes a refill from cache or normal cacheable  
        500)                                                                    
DCACHE_ACCESS: (counter: 1, 2, 3, 4)                                            
        Data R/W from cache (min count: 500)                                    
DTLB_REFILL: (counter: 1, 2, 3, 4)                                              
        Data R/W that causes a TLB refill (min count: 500)                      
DREAD: (counter: 1, 2, 3, 4)                                                    
        Data read architecturally executed (note: architecturally executed = fo 
        are unconditional or that pass the condition code) (min count: 500)     
DWRITE: (counter: 1, 2, 3, 4)                                                   
        Data write architecturally executed (min count: 500)                    
INSTR_EXECUTED: (counter: 1, 2, 3, 4)                                           
        All executed instructions (min count: 500)                              
EXC_TAKEN: (counter: 1, 2, 3, 4)                                                
        Exception taken (min count: 500)                                        
EXC_EXECUTED: (counter: 1, 2, 3, 4)                                             
        Exception return architecturally executed (min count: 500)              
CID_WRITE: (counter: 1, 2, 3, 4)                                                
        Instruction that writes to the Context ID Register architecturally exec 
        500)                                                                    
PC_WRITE: (counter: 1, 2, 3, 4)                                                 
        SW change of PC, architecturally executed (not by exceptions) (min coun 
PC_IMM_BRANCH: (counter: 1, 2, 3, 4)                                            
        Immediate branch instruction executed (taken or not) (min count: 500)   
PC_PROC_RETURN: (counter: 1, 2, 3, 4)                                           
        Procedure return architecturally executed (not by exceptions) (min coun 
UNALIGNED_ACCESS: (counter: 1, 2, 3, 4)                                         
        Unaligned access architecturally executed (min count: 500)              
PC_BRANCH_MIS_PRED: (counter: 1, 2, 3, 4)                                       
        Branch mispredicted or not predicted. Counts pipeline flushes because o 
        count: 500)                                                             
PC_BRANCH_MIS_USED: (counter: 1, 2, 3, 4)                                       
        Branch or change in program flow that could have been predicted (min co 
WRITE_BUFFER_FULL: (counter: 1, 2, 3, 4)                                        
        Any write buffer full cycle (min count: 500)                            
L2_STORE_MERGED: (counter: 1, 2, 3, 4)                                          
        Any store that is merged in L2 cache (min count: 500)                   
L2_STORE_BUFF: (counter: 1, 2, 3, 4)                                            
        Any bufferable store from load/store to L2 cache (min count: 500)       
L2_ACCESS: (counter: 1, 2, 3, 4)                                                
        Any access to L2 cache (min count: 500)                                 
L2_CACH_MISS: (counter: 1, 2, 3, 4)                                             
        Any cacheable miss in L2 cache (min count: 500)                         
AXI_READ_CYCLES: (counter: 1, 2, 3, 4)                                          
        Number of cycles for an active AXI read (min count: 500)                
AXI_WRITE_CYCLES: (counter: 1, 2, 3, 4)                                         
        Number of cycles for an active AXI write (min count: 500)               
MEMORY_REPLAY: (counter: 1, 2, 3, 4)                                            
        Any replay event in the memory subsystem (min count: 500)               
UNALIGNED_ACCESS_REPLAY: (counter: 1, 2, 3, 4)                                  
        Unaligned access that causes a replay (min count: 500)                  
L1_DATA_MISS: (counter: 1, 2, 3, 4)                                             
        L1 data cache miss as a result of the hashing algorithm (min count: 500 
L1_INST_MISS: (counter: 1, 2, 3, 4)                                             
        L1 instruction cache miss as a result of the hashing algorithm (min cou 
L1_DATA_COLORING: (counter: 1, 2, 3, 4)                                         
        L1 data access in which a page coloring alias occurs (min count: 500)   
L1_NEON_DATA: (counter: 1, 2, 3, 4)                                             
        NEON data access that hits L1 cache (min count: 500)                    
L1_NEON_CACH_DATA: (counter: 1, 2, 3, 4)                                        
        NEON cacheable data access that hits L1 cache (min count: 500)          
L2_NEON: (counter: 1, 2, 3, 4)                                                  
        L2 access as a result of NEON memory access (min count: 500)            
L2_NEON_HIT: (counter: 1, 2, 3, 4)                                              
        Any NEON hit in L2 cache (min count: 500)                               
L1_INST: (counter: 1, 2, 3, 4)                                                  
        Any L1 instruction cache access, excluding CP15 cache accesses (min cou 
PC_RETURN_MIS_PRED: (counter: 1, 2, 3, 4)                                       
        Return stack misprediction at return stack pop (incorrect target addres 
PC_BRANCH_FAILED: (counter: 1, 2, 3, 4)                                         
        Branch prediction misprediction (min count: 500)                        
PC_BRANCH_TAKEN: (counter: 1, 2, 3, 4)                                          
        Any predicted branch that is taken (min count: 500)                     
PC_BRANCH_EXECUTED: (counter: 1, 2, 3, 4)                                       
        Any taken branch that is executed (min count: 500)                      
OP_EXECUTED: (counter: 1, 2, 3, 4)                                              
        Number of operations executed (in instruction or mutli-cycle instructio 
CYCLES_INST_STALL: (counter: 1, 2, 3, 4)                                        
        Cycles where no instruction available (min count: 500)                  
CYCLES_INST: (counter: 1, 2, 3, 4)                                              
        Number of instructions issued in a cycle (min count: 500)               
CYCLES_NEON_DATA_STALL: (counter: 1, 2, 3, 4)                                   
        Number of cycles the processor waits on MRC data from NEON (min count:  
CYCLES_NEON_INST_STALL: (counter: 1, 2, 3, 4)                                   
        Number of cycles the processor waits on NEON instruction queue or NEON  
        count: 500)                                                             
NEON_CYCLES: (counter: 1, 2, 3, 4)                                              
        Number of cycles NEON and integer processors are not idle (min count: 5 
PMU0_EVENTS: (counter: 1, 2, 3, 4)                                              
        Number of events from external input source PMUEXTIN[0] (min count: 500 
PMU1_EVENTS: (counter: 1, 2, 3, 4)                                              
        Number of events from external input source PMUEXTIN[1] (min count: 500 
PMU_EVENTS: (counter: 1, 2, 3, 4)                                               
        Number of events from both external input sources PMUEXTIN[0] and PMUEX 
        500)                                                                    
CPU_CYCLES: (counter: 0)                                                        
        Number of CPU cycles (min count: 500)                                   
lucid@lucid-desktop:~$

```

# SETI oprofile run script #
```
#!/bin/bash
# iMX53 - ARM Cortex A8 Oprofile Script
SleepSeconds=5 #213 on real run
sudo opcontrol --shutdown
./seti_boinc --standalone &

# Running Timer Mode

sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --start
sudo opcontrol --status
echo "profiling for $SleepSeconds seconds"
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L2_ACCESS:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L2_CACH_MISS:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L1_DATA_MISS:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L1_INST:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L1_DATA_MISS:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=PC_BRANCH_FAILED:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=PC_BRANCH_TAKEN:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L1_NEON_DATA:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CYCLES_INST_STALL:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CYCLES_INST_STALL:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CYCLES_INST:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CYCLES_NEON_DATA_STALL:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CYCLES_NEON_INST_STALL:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=NEON_CYCLES:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=L2_NEON_HIT:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=INS_MAIN_EXEC:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=INS_SND_EXEC:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=INS_LSU:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=INS_FP_RR:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

```

# SETI Oprofile results #
```
Sat Aug 20 01:24:59 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
L1_DATA_MISS:1...|
  samples|      %|
------------------
     3421 98.7872 seti_boinc
       17  0.4909 libc-2.11.1.so
        9  0.2599 libglib-2.0.so.0.2400.1
        5  0.1444 bash
        5  0.1444 ld-2.11.1.so
        4  0.1155 python2.6
        1  0.0289 libpthread-2.11.1.so
        1  0.0289 libX11.so.6.3.0
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
1171     34.2298  top_sum2(float**, PoTPlan*)
820      23.9696  top_sum3(float**, PoTPlan*)
652      19.0588  top_sum4(float**, PoTPlan*)
327       9.5586  top_sum5(float**, PoTPlan*)
276       8.0678  t_funct(int, int, int)
103       3.0108  find_pulse(float const*, int, float, int, int)
41        1.1985  sw_sum2_t31(float**, PoTPlan*)
9         0.2631  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
3         0.0877  t1_16
2         0.0585  memset
2         0.0585  t1_32
2         0.0585  tape::tape()
2         0.0585  v_BaseLineSmooth(float (*) [2], int, int, int)
1         0.0292  GenChirpFftPairs(ChirpFftPair_t**, double*)
1         0.0292  GetFixedPoT(float*, int, int, float*, int, int)
1         0.0292  __ieee754_log
1         0.0292  _int_malloc
1         0.0292  apply_dit
1         0.0292  malloc
1         0.0292  memcpy
1         0.0292  mkcldw
1         0.0292  mkplan
1         0.0292  n1_8
1         0.0292  time_to_ra_dec(double, double*, double*)
 
 
Sat Aug 20 01:28:56 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
  L2_ACCESS:10000|
  samples|      %|
------------------
    48503 93.6912 seti_boinc
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	    48414 99.8165 seti_boinc
	       89  0.1835 [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
     1026  1.9819 python2.6
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	     1019 99.3177 python2.6
	        7  0.6823 [vectors] (tgid:4694 range:0xffff0000-0xffff1000)
      733  1.4159 libc-2.11.1.so
      371  0.7166 libglib-2.0.so.0.2400.1
      285  0.5505 ld-2.11.1.so
      185  0.3574 bash
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	      184 99.4595 bash
	        1  0.5405 [vectors] (tgid:12678 range:0xffff0000-0xffff1000)
      150  0.2897 libpthread-2.11.1.so
       72  0.1391 Xorg
       60  0.1159 libdbus-1.so.3.4.0
       33  0.0637 libapt-pkg-libc6.10-6.so.4.8.0
       27  0.0522 libgobject-2.0.so.0.2400.1
       22  0.0425 libX11.so.6.3.0
       21  0.0406 _glib.so
       20  0.0386 libgio-2.0.so.0.2400.1
       19  0.0367 libpyglib-2.0-python2.6.so.0.0.0
       18  0.0348 libecore-ver-svn-05.so.0.9.9
       18  0.0348 libstdc++.so.6.0.13
       16  0.0309 libpulsecommon-0.9.21.so
       16  0.0309 libxcb.so.1.1.0
       15  0.0290 libavahi-core.so.6.0.1
       14  0.0270 oprofiled
       13  0.0251 gawk
       11  0.0212 libgthread-2.0.so.0.2400.1
        9  0.0174 libavahi-common.so.3.5.1
        9  0.0174 libpulse.so.0.12.2
        8  0.0155 gpgv
        7  0.0135 libgvfscommon.so.0.0.0
        6  0.0116 dash
        6  0.0116 http
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        5 83.3333 http
	        1 16.6667 [vectors] (tgid:12609 range:0xffff0000-0xffff1000)
        6  0.0116 gnome-settings-daemon
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        6 100.000 [vectors] (tgid:4409 range:0xffff0000-0xffff1000)
        6  0.0116 libgdk-x11-2.0.so.0.2000.1
        4  0.0077 apt-get
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        4 100.000 [vectors] (tgid:12605 range:0xffff0000-0xffff1000)
        4  0.0077 nautilus
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        2 50.0000 nautilus
	        2 50.0000 [vectors] (tgid:4439 range:0xffff0000-0xffff1000)
        4  0.0077 libpulse-mainloop-glib.so.0.0.4
        4  0.0077 gdm-binary
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        4 100.000 [vectors] (tgid:3377 range:0xffff0000-0xffff1000)
        4  0.0077 ntpd
        4  0.0077 rsyslogd
        3  0.0058 modprobe
        3  0.0058 libgtk-x11-2.0.so.0.2000.1
        3  0.0058 avahi-daemon
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        2 66.6667 [vectors] (tgid:3189 range:0xffff0000-0xffff1000)
	        1 33.3333 avahi-daemon
        2  0.0039 libm-2.11.1.so
        2  0.0039 libpopt.so.0.0.0
        2  0.0039 librt-2.11.1.so
        2  0.0039 netbook-launcher-efl
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        2 100.000 [vectors] (tgid:4432 range:0xffff0000-0xffff1000)
        2  0.0039 wget
        2  0.0039 libdbus-glib-1.so.2.1.0
        2  0.0039 libecore_evas-ver-svn-05.so.0.9.9
        2  0.0039 libecore_x-ver-svn-05.so.0.9.9
        2  0.0039 libevas-ver-svn-05.so.0.9.9
        1  0.0019 cat
        1  0.0019 grep
        1  0.0019 libncurses.so.5.7
        1  0.0019 libnss_nis-2.11.1.so
        1  0.0019 libudev.so.0.6.1
        1  0.0019 tr
        1  0.0019 gpgv
        1  0.0019 clock-applet
	  L2_ACCESS:10000|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4533 range:0xffff0000-0xffff1000)
        1  0.0019 libORBit-2.so.0.1.0
        1  0.0019 libcairo.so.2.10800.10
        1  0.0019 gconfd-2
        1  0.0019 libusbmuxd.so.1.0.0
        1  0.0019 libexa.so
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_ACCESS events (Any access to L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
18570    38.2863  seti_boinc               top_sum2(float**, PoTPlan*)
8944     18.4401  seti_boinc               top_sum3(float**, PoTPlan*)
6666     13.7435  seti_boinc               top_sum4(float**, PoTPlan*)
4971     10.2489  seti_boinc               top_sum5(float**, PoTPlan*)
1205      2.4844  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
1101      2.2700  seti_boinc               find_pulse(float const*, int, float, int, int)
877       1.8081  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
789       1.6267  seti_boinc               t_funct(int, int, int)
740       1.5257  seti_boinc               memset
363       0.7484  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
302       0.6226  seti_boinc               _int_malloc
275       0.5670  seti_boinc               analysis_config::analysis_config()
260       0.5360  seti_boinc               workunit_grp::workunit_grp()
235       0.4845  seti_boinc               malloc
217       0.4474  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
167       0.3443  seti_boinc               splitter_config::splitter_config()
163       0.3361  seti_boinc               tape::tape()
147       0.3031  seti_boinc               pulse::pulse()
139       0.2866  seti_boinc               time_to_ra_dec(double, double*, double*)
134       0.2763  seti_boinc               data_description_t::data_description_t()
125       0.2577  seti_boinc               malloc_consolidate
120       0.2474  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
118       0.2433  seti_boinc               operator new(unsigned int)
115       0.2371  seti_boinc               __ieee754_log
113       0.2330  seti_boinc               workunit_header::workunit_header()
111       0.2289  seti_boinc               result::result()
105       0.2165  seti_boinc               recorder_config::recorder_config()
103       0.2124  seti_boinc               _int_free
103       0.2124  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
102       0.2103  seti_boinc               n1_64
89        0.1835  [vectors] (tgid:10375 range:0xffff0000-0xffff1000) [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
76        0.1567  seti_boinc               n1_32
69        0.1423  seti_boinc               receiver_config::receiver_config()
68        0.1402  seti_boinc               PULSE_INFO::PULSE_INFO()
57        0.1175  seti_boinc               calc_detection_freq(double, double, double)
57        0.1175  seti_boinc               subband_description_t::subband_description_t()
55        0.1134  seti_boinc               cnvt_bin_hz(int, int)
44        0.0907  seti_boinc               __ieee754_pow
35        0.0722  seti_boinc               find_triplets(float const*, int, float, int, int)
33        0.0680  seti_boinc               __exp1
32        0.0660  seti_boinc               free
29        0.0598  seti_boinc               T.9822
29        0.0598  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
27        0.0557  seti_boinc               floorf
27        0.0557  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
26        0.0536  seti_boinc               T.9827
26        0.0536  seti_boinc               __divsi3
26        0.0536  seti_boinc               operator delete(void*)
25        0.0515  seti_boinc               n1_16
23        0.0474  seti_boinc               T.9826
23        0.0474  seti_boinc               boinc_fraction_done
20        0.0412  seti_boinc               PULSE_INFO::~PULSE_INFO()
20        0.0412  seti_boinc               spike::spike()
19        0.0392  seti_boinc               log10l
18        0.0371  seti_boinc               seti_analyze(ANALYSIS_STATE&)
17        0.0350  seti_boinc               logl
17        0.0350  seti_boinc               t1_8
15        0.0309  seti_boinc               SPIKE_INFO::SPIKE_INFO()
11        0.0227  seti_boinc               T.9831
11        0.0227  seti_boinc               fftwf_execute_dft
9         0.0186  seti_boinc               __aeabi_read_tp
8         0.0165  seti_boinc               powl
6         0.0124  seti_boinc               SpikeProgressUnits(int)
6         0.0124  seti_boinc               fftwf_malloc
6         0.0124  seti_boinc               memcpy
5         0.0103  seti_boinc               __ieee754_log10
5         0.0103  seti_boinc               apply
5         0.0103  seti_boinc               nanosleep
4         0.0082  seti_boinc               __libc_enable_asynccancel
4         0.0082  seti_boinc               fftwf_free
3         0.0062  seti_boinc               ____libc_disable_asynccancel_veneer
3         0.0062  seti_boinc               __libc_disable_asynccancel
3         0.0062  seti_boinc               getrusage
3         0.0062  seti_boinc               worker_signal_handler(int)
2         0.0041  seti_boinc               apply_dit
2         0.0041  seti_boinc               boinc_sleep(double)
2         0.0041  seti_boinc               checkpoint(unsigned char)
2         0.0041  seti_boinc               fmodl
2         0.0041  seti_boinc               fraction_done(double, double)
2         0.0041  seti_boinc               gettimeofday
2         0.0041  seti_boinc               timer_handler()
1         0.0021  seti_boinc               MFILE::MFILE()
1         0.0021  seti_boinc               PulseProgressUnits(double, int)
1         0.0021  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
1         0.0021  seti_boinc               TripletProgressUnits()
1         0.0021  seti_boinc               ____libc_enable_asynccancel_veneer
1         0.0021  seti_boinc               __default_sa_restorer_v2
1         0.0021  seti_boinc               fftwf_kernel_malloc
1         0.0021  seti_boinc               floor
1         0.0021  seti_boinc               free_a(void*)
1         0.0021  seti_boinc               isnanl
1         0.0021  seti_boinc               lcgf(double, double)
1         0.0021  seti_boinc               malloc_a(unsigned int, unsigned int)
1         0.0021  seti_boinc               std::string::reserve(unsigned int)
1         0.0021  seti_boinc               timer_thread(void*)
1         0.0021  seti_boinc               vfprintf
 
 
Sat Aug 20 01:32:54 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
L2_CACH_MISS:1...|
  samples|      %|
------------------
    24474 96.7849 seti_boinc
	L2_CACH_MISS:1...|
	  samples|      %|
	------------------
	    24455 99.9224 seti_boinc
	       19  0.0776 [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
      347  1.3722 libc-2.11.1.so
      194  0.7672 python2.6
       81  0.3203 libglib-2.0.so.0.2400.1
       51  0.2017 ld-2.11.1.so
       43  0.1700 bash
       16  0.0633 libpthread-2.11.1.so
       11  0.0435 libdbus-1.so.3.4.0
       10  0.0395 Xorg
       10  0.0395 libapt-pkg-libc6.10-6.so.4.8.0
        9  0.0356 libX11.so.6.3.0
        7  0.0277 libgobject-2.0.so.0.2400.1
        4  0.0158 libgio-2.0.so.0.2400.1
        3  0.0119 libavahi-common.so.3.5.1
        3  0.0119 libpulse.so.0.12.2
        2  0.0079 libm-2.11.1.so
        2  0.0079 libgvfscommon.so.0.0.0
        2  0.0079 libpyglib-2.0-python2.6.so.0.0.0
        2  0.0079 libxcb.so.1.1.0
        2  0.0079 _glib.so
        2  0.0079 ntpd
        2  0.0079 rsyslogd
        1  0.0040 librt-2.11.1.so
        1  0.0040 modprobe
        1  0.0040 apt-get
        1  0.0040 gawk
        1  0.0040 nautilus
	L2_CACH_MISS:1...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4439 range:0xffff0000-0xffff1000)
        1  0.0040 oprofiled
        1  0.0040 libavahi-core.so.6.0.1
        1  0.0040 libcairo.so.2.10800.10
        1  0.0040 libdbus-glib-1.so.2.1.0
        1  0.0040 libgthread-2.0.so.0.2400.1
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L2_CACH_MISS events (Any cacheable miss in L2 cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
9333     38.1343  seti_boinc               n1_32
2184      8.9238  seti_boinc               fftwf_cpy2d_pair
2072      8.4661  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
2010      8.2128  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
1801      7.3588  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
1500      6.1290  seti_boinc               apply
1465      5.9859  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
1333      5.4466  seti_boinc               n1_64
974       3.9797  seti_boinc               t1_16
590       2.4107  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
128       0.5230  seti_boinc               analysis_config::analysis_config()
121       0.4944  seti_boinc               t1_32
111       0.4535  seti_boinc               rotate_sqrtn_table
107       0.4372  seti_boinc               t1_8
77        0.3146  seti_boinc               splitter_config::splitter_config()
72        0.2942  seti_boinc               cosl
43        0.1757  seti_boinc               operator new(unsigned int)
40        0.1634  seti_boinc               malloc
40        0.1634  seti_boinc               memset
39        0.1594  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
31        0.1267  seti_boinc               result::result()
31        0.1267  seti_boinc               sinl
27        0.1103  seti_boinc               q1_4
27        0.1103  seti_boinc               t1_64
20        0.0817  seti_boinc               __ieee754_log
20        0.0817  seti_boinc               workunit_header::workunit_header()
19        0.0776  [vectors] (tgid:10375 range:0xffff0000-0xffff1000) [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
17        0.0695  seti_boinc               workunit_grp::workunit_grp()
15        0.0613  seti_boinc               _int_malloc
14        0.0572  seti_boinc               apply_dit
13        0.0531  seti_boinc               recorder_config::recorder_config()
13        0.0531  seti_boinc               t1_4
12        0.0490  seti_boinc               subband_description_t::subband_description_t()
11        0.0449  seti_boinc               __dubsin
8         0.0327  seti_boinc               n1_16
7         0.0286  seti_boinc               data_description_t::data_description_t()
7         0.0286  seti_boinc               find_pulse(float const*, int, float, int, int)
7         0.0286  seti_boinc               top_sum3(float**, PoTPlan*)
6         0.0245  seti_boinc               T.9831
6         0.0245  seti_boinc               apply
6         0.0245  seti_boinc               find_triplets(float const*, int, float, int, int)
6         0.0245  seti_boinc               tape::tape()
5         0.0204  seti_boinc               apply
5         0.0204  seti_boinc               apply
5         0.0204  seti_boinc               csloww1
5         0.0204  seti_boinc               gaussian::gaussian()
4         0.0163  seti_boinc               __exp1
4         0.0163  seti_boinc               pulse::pulse()
4         0.0163  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
4         0.0163  seti_boinc               timer_handler()
3         0.0123  seti_boinc               T.9826
3         0.0123  seti_boinc               __aeabi_read_tp
3         0.0123  seti_boinc               __dubcos
3         0.0123  seti_boinc               __ieee754_pow
3         0.0123  seti_boinc               _int_free
3         0.0123  seti_boinc               csloww
3         0.0123  seti_boinc               free
2         0.0082  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
2         0.0082  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
2         0.0082  seti_boinc               SpikeProgressUnits(int)
2         0.0082  seti_boinc               T.9827
2         0.0082  seti_boinc               TripletProgressUnits()
2         0.0082  seti_boinc               __default_sa_restorer_v2
2         0.0082  seti_boinc               __docos
2         0.0082  seti_boinc               __libc_disable_asynccancel
2         0.0082  seti_boinc               apply_dif
2         0.0082  seti_boinc               fftwf_execute_dft
2         0.0082  seti_boinc               floor
2         0.0082  seti_boinc               receiver_config::receiver_config()
2         0.0082  seti_boinc               seti_analyze(ANALYSIS_STATE&)
2         0.0082  seti_boinc               time_to_ra_dec(double, double*, double*)
2         0.0082  seti_boinc               top_sum2(float**, PoTPlan*)
2         0.0082  seti_boinc               worker_signal_handler(int)
1         0.0041  seti_boinc               GaussFit(float*, int, int)
1         0.0041  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
1         0.0041  seti_boinc               T.9822
1         0.0041  seti_boinc               __divsi3
1         0.0041  seti_boinc               __ieee754_fmod
1         0.0041  seti_boinc               __ieee754_log10
1         0.0041  seti_boinc               __libc_enable_asynccancel
1         0.0041  seti_boinc               __udivsi3
1         0.0041  seti_boinc               apply
1         0.0041  seti_boinc               boinc_fraction_done
1         0.0041  seti_boinc               cnvt_bin_hz(int, int)
1         0.0041  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
1         0.0041  seti_boinc               fraction_done(double, double)
1         0.0041  seti_boinc               logl
1         0.0041  seti_boinc               malloc_consolidate
1         0.0041  seti_boinc               powl
1         0.0041  seti_boinc               sincos
1         0.0041  seti_boinc               spike::spike()
1         0.0041  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
1         0.0041  seti_boinc               t_funct(int, int, int)
1         0.0041  seti_boinc               top_sum4(float**, PoTPlan*)
1         0.0041  seti_boinc               top_sum5(float**, PoTPlan*)
 
Sat Aug 20 01:36:52 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
L1_DATA_MISS:1...|
  samples|      %|
------------------
      400 89.6861 seti_boinc
       17  3.8117 libc-2.11.1.so
        7  1.5695 libglib-2.0.so.0.2400.1
        6  1.3453 ld-2.11.1.so
        4  0.8969 libdbus-1.so.3.4.0
        3  0.6726 bash
        3  0.6726 python2.6
        2  0.4484 libpthread-2.11.1.so
        1  0.2242 Xorg
        1  0.2242 libgdk-x11-2.0.so.0.2000.1
        1  0.2242 libpulsecommon-0.9.21.so
        1  0.2242 libpyglib-2.0-python2.6.so.0.0.0
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
50       12.5000  fftwf_cpy2d_pair
49       12.2500  n1_32
39        9.7500  v_GetPowerSpectrum(float (*) [2], float*, int)
37        9.2500  t1_16
37        9.2500  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
27        6.7500  GetFixedPoT(float*, int, int, float*, int, int)
27        6.7500  analyze_pot(float*, int, ChirpFftPair_t&)
26        6.5000  n1_64
23        5.7500  t1_64
17        4.2500  apply
15        3.7500  rotate_sqrtn_table
15        3.7500  t1_32
14        3.5000  q1_4
12        3.0000  FindSpikes(float*, int, int, SETI_WU_INFO&)
3         0.7500  sinl
2         0.5000  t1_8
1         0.2500  GaussFit(float*, int, int)
1         0.2500  PulseProgressUnits(double, int)
1         0.2500  __ieee754_pow
1         0.2500  _int_malloc
1         0.2500  analysis_config::analysis_config()
1         0.2500  cosl
1         0.2500  sw_sum4_t31(float**, PoTPlan*)
 
 
Sat Aug 20 01:40:49 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_INST events (Any L1 instruction cache access, excluding CP15 cache accesses) with a unit mask of 0x00 (No unit mask) count 10000
    L1_INST:10000|
  samples|      %|
------------------
   663864 95.3599 seti_boinc
	    L1_INST:10000|
	  samples|      %|
	------------------
	   663273 99.9110 seti_boinc
	      591  0.0890 [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
    12359  1.7753 libc-2.11.1.so
     9301  1.3360 oprofiled
	    L1_INST:10000|
	  samples|      %|
	------------------
	     9178 98.6776 oprofiled
	      123  1.3224 [vectors] (tgid:16510 range:0xffff0000-0xffff1000)
     2576  0.3700 bash
	    L1_INST:10000|
	  samples|      %|
	------------------
	     2390 92.7795 bash
	      186  7.2205 [vectors] (tgid:16513 range:0xffff0000-0xffff1000)
     2523  0.3624 python2.6
	    L1_INST:10000|
	  samples|      %|
	------------------
	     2425 96.1157 python2.6
	       98  3.8843 [vectors] (tgid:4694 range:0xffff0000-0xffff1000)
     1637  0.2351 ld-2.11.1.so
     1105  0.1587 libglib-2.0.so.0.2400.1
      687  0.0987 libpthread-2.11.1.so
      273  0.0392 modprobe
      245  0.0352 libavahi-common.so.3.5.1
      213  0.0306 libdbus-1.so.3.4.0
      166  0.0238 Xorg
	    L1_INST:10000|
	  samples|      %|
	------------------
	      162 97.5904 Xorg
	        4  2.4096 [vectors] (tgid:3895 range:0xffff0000-0xffff1000)
       89  0.0128 libX11.so.6.3.0
       88  0.0126 libxcb.so.1.1.0
       78  0.0112 libgobject-2.0.so.0.2400.1
       72  0.0103 nautilus
	    L1_INST:10000|
	  samples|      %|
	------------------
	       46 63.8889 [vectors] (tgid:4439 range:0xffff0000-0xffff1000)
	       26 36.1111 nautilus
       69  0.0099 libgio-2.0.so.0.2400.1
       66  0.0095 libavahi-core.so.6.0.1
       61  0.0088 gawk
       57  0.0082 ophelp
       51  0.0073 libpulsecommon-0.9.21.so
       48  0.0069 libecore-ver-svn-05.so.0.9.9
       47  0.0068 tr
       38  0.0055 libapt-pkg-libc6.10-6.so.4.8.0
       32  0.0046 _glib.so
       30  0.0043 gnome-settings-daemon
	    L1_INST:10000|
	  samples|      %|
	------------------
	       30 100.000 [vectors] (tgid:4409 range:0xffff0000-0xffff1000)
       29  0.0042 libORBit-2.so.0.1.0
       29  0.0042 rsyslogd
	    L1_INST:10000|
	  samples|      %|
	------------------
	       23 79.3103 rsyslogd
	        6 20.6897 [vectors] (tgid:3164 range:0xffff0000-0xffff1000)
       25  0.0036 libpyglib-2.0-python2.6.so.0.0.0
       23  0.0033 libgdk-x11-2.0.so.0.2000.1
       22  0.0032 libpulse.so.0.12.2
       21  0.0030 avahi-daemon
	    L1_INST:10000|
	  samples|      %|
	------------------
	       21 100.000 [vectors] (tgid:3189 range:0xffff0000-0xffff1000)
       21  0.0030 ntpd
       20  0.0029 libdbus-glib-1.so.2.1.0
       17  0.0024 netbook-launcher-efl
	    L1_INST:10000|
	  samples|      %|
	------------------
	       16 94.1176 [vectors] (tgid:4432 range:0xffff0000-0xffff1000)
	        1  5.8824 netbook-launcher-efl
       16  0.0023 apt-get
	    L1_INST:10000|
	  samples|      %|
	------------------
	       14 87.5000 [vectors] (tgid:12605 range:0xffff0000-0xffff1000)
	        2 12.5000 apt-get
       13  0.0019 libgvfscommon.so.0.0.0
       12  0.0017 libpangoft2-1.0.so.0.2800.0
       10  0.0014 indicator-me-service
	    L1_INST:10000|
	  samples|      %|
	------------------
	       10 100.000 [vectors] (tgid:4615 range:0xffff0000-0xffff1000)
       10  0.0014 libz160.so
        9  0.0013 dash
        9  0.0013 sudo
	    L1_INST:10000|
	  samples|      %|
	------------------
	        7 77.7778 sudo
	        2 22.2222 [vectors] (tgid:16513 range:0xffff0000-0xffff1000)
        8  0.0011 grep
        7  0.0010 libm-2.11.1.so
        7  0.0010 libpam.so.0.82.2
        6 8.6e-04 sleep
	    L1_INST:10000|
	  samples|      %|
	------------------
	        6 100.000 [vectors] (tgid:16658 range:0xffff0000-0xffff1000)
        6 8.6e-04 clock-applet
	    L1_INST:10000|
	  samples|      %|
	------------------
	        6 100.000 [vectors] (tgid:4533 range:0xffff0000-0xffff1000)
        6 8.6e-04 libgtk-x11-2.0.so.0.2000.1
        5 7.2e-04 libgcc_s.so.1
        5 7.2e-04 libpango-1.0.so.0.2800.0
        5 7.2e-04 gdm-binary
	    L1_INST:10000|
	  samples|      %|
	------------------
	        5 100.000 [vectors] (tgid:3377 range:0xffff0000-0xffff1000)
        4 5.7e-04 libdl-2.11.1.so
        4 5.7e-04 libpopt.so.0.0.0
        3 4.3e-04 gconv-modules.cache
        3 4.3e-04 libecore_evas-ver-svn-05.so.0.9.9
        3 4.3e-04 libecore_x-ver-svn-05.so.0.9.9
        3 4.3e-04 gconfd-2
	    L1_INST:10000|
	  samples|      %|
	------------------
	        3 100.000 [vectors] (tgid:4400 range:0xffff0000-0xffff1000)
        3 4.3e-04 libexa.so
        2 2.9e-04 libgvfsdbus.so
        2 2.9e-04 libXau.so.6.0.0
        2 2.9e-04 libgconf-2.so.4.1.5
        2 2.9e-04 libgthread-2.0.so.0.2400.1
        2 2.9e-04 libpixman-1.so.0.16.4
        2 2.9e-04 libpulse-mainloop-glib.so.0.0.4
        2 2.9e-04 libfb.so
        1 1.4e-04 cat
        1 1.4e-04 libnss_compat-2.11.1.so
        1 1.4e-04 librt-2.11.1.so
        1 1.4e-04 libselinux.so.1
        1 1.4e-04 pam_limits.so
        1 1.4e-04 gnome-power-manager
	    L1_INST:10000|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4440 range:0xffff0000-0xffff1000)
        1 1.4e-04 id
        1 1.4e-04 libmedia-keys.so
        1 1.4e-04 libcairo.so.2.10800.10
        1 1.4e-04 libevas-ver-svn-05.so.0.9.9
        1 1.4e-04 libpanel-applet-2.so.0.2.67
        1 1.4e-04 libpangocairo-1.0.so.0.2800.0
        1 1.4e-04 LC_CTYPE
        1 1.4e-04 imuxsock.so
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_INST events (Any L1 instruction cache access, excluding CP15 cache accesses) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
69489    10.4674  seti_boinc               cosl
67848    10.2202  seti_boinc               t1_16
62914     9.4769  seti_boinc               sinl
57998     8.7364  seti_boinc               n1_32
32044     4.8269  seti_boinc               n1_16
30165     4.5439  seti_boinc               n1_64
29905     4.5047  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
28119     4.2357  seti_boinc               rotate_sqrtn_table
23315     3.5120  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
20606     3.1039  seti_boinc               q1_4
17478     2.6328  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
15771     2.3756  seti_boinc               t1_4
15190     2.2881  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
14551     2.1919  seti_boinc               GaussFit(float*, int, int)
12751     1.9207  seti_boinc               __ieee754_log
12286     1.8507  seti_boinc               t1_64
11784     1.7751  seti_boinc               find_triplets(float const*, int, float, int, int)
11656     1.7558  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
11365     1.7119  seti_boinc               floor
10493     1.5806  seti_boinc               __ieee754_pow
10188     1.5347  seti_boinc               apply
9198      1.3855  seti_boinc               fftwf_cpy2d_pair
8582      1.2927  seti_boinc               t1_32
6886      1.0373  seti_boinc               lcgf(double, double)
6714      1.0114  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
6651      1.0019  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
5602      0.8438  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
5525      0.8322  seti_boinc               t1_8
5364      0.8080  seti_boinc               __exp1
4430      0.6673  seti_boinc               find_pulse(float const*, int, float, int, int)
3751      0.5650  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
3500      0.5272  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
3460      0.5212  seti_boinc               _int_malloc
3299      0.4969  seti_boinc               powl
2934      0.4420  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
2415      0.3638  seti_boinc               sw_sum5_t31(float**, PoTPlan*)
2044      0.3079  seti_boinc               sincos
1449      0.2183  seti_boinc               _int_free
1228      0.1850  seti_boinc               logl
1153      0.1737  seti_boinc               fraction_done(double, double)
1076      0.1621  seti_boinc               malloc
966       0.1455  seti_boinc               csloww1
881       0.1327  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
776       0.1169  seti_boinc               __divsi3
752       0.1133  seti_boinc               checkpoint(unsigned char)
693       0.1044  seti_boinc               TripletProgressUnits()
655       0.0987  seti_boinc               free
591       0.0890  [vectors] (tgid:10375 range:0xffff0000-0xffff1000) [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
541       0.0815  seti_boinc               isnanl
462       0.0696  seti_boinc               PulseProgressUnits(double, int)
416       0.0627  seti_boinc               time_to_ra_dec(double, double*, double*)
341       0.0514  seti_boinc               malloc_consolidate
322       0.0485  seti_boinc               operator new(unsigned int)
293       0.0441  seti_boinc               apply_dit
287       0.0432  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
264       0.0398  seti_boinc               finite
263       0.0396  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
232       0.0349  seti_boinc               apply
228       0.0343  seti_boinc               apply
225       0.0339  seti_boinc               GaussianProgressUnits()
224       0.0337  seti_boinc               __dubcos
221       0.0333  seti_boinc               gaussian::gaussian()
214       0.0322  seti_boinc               __udivsi3
188       0.0283  seti_boinc               workunit_grp::workunit_grp()
187       0.0282  seti_boinc               __dubsin
179       0.0270  seti_boinc               cnvt_bin_hz(int, int)
155       0.0233  seti_boinc               calc_detection_freq(double, double, double)
145       0.0218  seti_boinc               apply
130       0.0196  seti_boinc               analysis_config::analysis_config()
126       0.0190  seti_boinc               receiver_config::receiver_config()
114       0.0172  seti_boinc               memset
112       0.0169  seti_boinc               apply
107       0.0161  seti_boinc               memcpy
103       0.0155  seti_boinc               splitter_config::splitter_config()
98        0.0148  seti_boinc               apply_dif
96        0.0145  seti_boinc               MFILE::~MFILE()
95        0.0143  seti_boinc               T.9826
82        0.0124  seti_boinc               csloww
81        0.0122  seti_boinc               workunit_header::workunit_header()
78        0.0117  seti_boinc               result::result()
71        0.0107  seti_boinc               operator delete(void*)
66        0.0099  seti_boinc               recorder_config::recorder_config()
65        0.0098  seti_boinc               MFILE::MFILE()
57        0.0086  seti_boinc               memmove
54        0.0081  seti_boinc               subband_description_t::subband_description_t()
54        0.0081  seti_boinc               tape::tape()
46        0.0069  seti_boinc               GAUSS_INFO::GAUSS_INFO()
45        0.0068  seti_boinc               data_description_t::data_description_t()
38        0.0057  seti_boinc               T.9822
32        0.0048  seti_boinc               T.9831
30        0.0045  seti_boinc               boinc_time_to_checkpoint
28        0.0042  seti_boinc               T.9827
23        0.0035  seti_boinc               __aeabi_read_tp
23        0.0035  seti_boinc               fftwf_cpy2d_pair_co
20        0.0030  seti_boinc               __docos
10        0.0015  seti_boinc               boinc_sleep(double)
8         0.0012  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
8         0.0012  seti_boinc               spike::spike()
8         0.0012  seti_boinc               timer_handler()
7         0.0011  seti_boinc               seti_analyze(ANALYSIS_STATE&)
6        9.0e-04  seti_boinc               __ieee754_log10
6        9.0e-04  seti_boinc               fmodl
6        9.0e-04  seti_boinc               log10l
6        9.0e-04  seti_boinc               worker_signal_handler(int)
5        7.5e-04  seti_boinc               SpikeProgressUnits(int)
5        7.5e-04  seti_boinc               __ieee754_fmod
5        7.5e-04  seti_boinc               __libc_disable_asynccancel
5        7.5e-04  seti_boinc               dtime()
4        6.0e-04  seti_boinc               gettimeofday
3        4.5e-04  seti_boinc               __default_sa_restorer_v2
3        4.5e-04  seti_boinc               fftwf_execute_dft
3        4.5e-04  seti_boinc               nanosleep
2        3.0e-04  seti_boinc               ____libc_disable_asynccancel_veneer
2        3.0e-04  seti_boinc               __libc_enable_asynccancel
2        3.0e-04  seti_boinc               boinc_fraction_done
2        3.0e-04  seti_boinc               getrusage
2        3.0e-04  seti_boinc               isinfl
2        3.0e-04  seti_boinc               usleep
1        1.5e-04  seti_boinc               SPIKE_INFO::SPIKE_INFO()
1        1.5e-04  seti_boinc               timer_thread(void*)
 
 
Sat Aug 20 01:44:49 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
L1_DATA_MISS:1...|
  samples|      %|
------------------
      426 83.2031 seti_boinc
       21  4.1016 libc-2.11.1.so
       19  3.7109 python2.6
       17  3.3203 libapt-pkg-libc6.10-6.so.4.8.0
        9  1.7578 libglib-2.0.so.0.2400.1
        5  0.9766 bash
        5  0.9766 ld-2.11.1.so
        3  0.5859 libpthread-2.11.1.so
        1  0.1953 Xorg
        1  0.1953 updatedb.mlocate
        1  0.1953 libmedia-keys.so
        1  0.1953 libX11.so.6.3.0
        1  0.1953 libavahi-core.so.6.0.1
        1  0.1953 libgdk-x11-2.0.so.0.2000.1
        1  0.1953 rsyslogd
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_DATA_MISS events (L1 data cache miss as a result of the hashing algorithm) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
60       14.0845  fftwf_cpy2d_pair
51       11.9718  n1_32
40        9.3897  v_GetPowerSpectrum(float (*) [2], float*, int)
37        8.6854  GetFixedPoT(float*, int, int, float*, int, int)
30        7.0423  analyze_pot(float*, int, ChirpFftPair_t&)
28        6.5728  n1_64
25        5.8685  t1_16
25        5.8685  t1_64
24        5.6338  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
16        3.7559  sinl
14        3.2864  apply
14        3.2864  rotate_sqrtn_table
10        2.3474  q1_4
10        2.3474  t1_32
8         1.8779  FindSpikes(float*, int, int, SETI_WU_INFO&)
6         1.4085  cosl
6         1.4085  fraction_done(double, double)
4         0.9390  _int_malloc
3         0.7042  __exp1
2         0.4695  apply_dit
2         0.4695  free
2         0.4695  t1_8
1         0.2347  __ieee754_log
1         0.2347  boinc_fraction_done
1         0.2347  csloww
1         0.2347  csloww1
1         0.2347  floor
1         0.2347  malloc
1         0.2347  n1_16
1         0.2347  sincos
1         0.2347  sw_sum5_t31(float**, PoTPlan*)
 
 
Sat Aug 20 01:48:46 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_FAILED events (Branch prediction misprediction) with a unit mask of 0x00 (No unit mask) count 10000
PC_BRANCH_FAIL...|
  samples|      %|
------------------
     4549 79.2509 seti_boinc
      465  8.1010 libc-2.11.1.so
      233  4.0592 libxapian.so.15.6.9
      116  2.0209 python2.6
	PC_BRANCH_FAIL...|
	  samples|      %|
	------------------
	      115 99.1379 python2.6
	        1  0.8621 [vectors] (tgid:18116 range:0xffff0000-0xffff1000)
      108  1.8815 libz.so.1.2.3.3
      107  1.8641 ld-2.11.1.so
       56  0.9756 libstdc++.so.6.0.13
       43  0.7491 bash
       20  0.3484 libglib-2.0.so.0.2400.1
       16  0.2787 libapt-pkg-libc6.10-6.so.4.8.0
        7  0.1220 modprobe
        2  0.0348 libgcc_s.so.1
        2  0.0348 sudo
        2  0.0348 libavahi-common.so.3.5.1
        2  0.0348 libgio-2.0.so.0.2400.1
        1  0.0174 Xorg
        1  0.0174 gawk
        1  0.0174 nautilus
        1  0.0174 ophelp
        1  0.0174 libX11.so.6.3.0
        1  0.0174 libavahi-core.so.6.0.1
        1  0.0174 libecore-ver-svn-05.so.0.9.9
        1  0.0174 libgobject-2.0.so.0.2400.1
        1  0.0174 libpulsecommon-0.9.21.so
        1  0.0174 libpyglib-2.0-python2.6.so.0.0.0
        1  0.0174 gdm-binary
	PC_BRANCH_FAIL...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:3377 range:0xffff0000-0xffff1000)
        1  0.0174 rsyslogd
	PC_BRANCH_FAIL...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:3164 range:0xffff0000-0xffff1000)
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_FAILED events (Branch prediction misprediction) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
1774     38.9976  cosl
1303     28.6437  sinl
629      13.8272  f_GetTrueMean(float*, int, float, int, int)
143       3.1435  find_triplets(float const*, int, float, int, int)
86        1.8905  __ieee754_log
82        1.8026  analyze_pot(float*, int, ChirpFftPair_t&)
79        1.7366  _int_malloc
71        1.5608  GaussFit(float*, int, int)
47        1.0332  lcgf(double, double)
29        0.6375  sw_sum4_t31(float**, PoTPlan*)
28        0.6155  GetFixedPoT(float*, int, int, float*, int, int)
24        0.5276  find_pulse(float const*, int, float, int, int)
24        0.5276  sw_sum3_t31(float**, PoTPlan*)
21        0.4616  float_to_uchar(float*, unsigned char*, long, float)
18        0.3957  apply_dit
15        0.3297  apply
15        0.3297  f_GetChiSq(float*, int, int, float, float, float*, float*)
14        0.3078  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
14        0.3078  __divsi3
13        0.2858  csloww1
12        0.2638  time_to_ra_dec(double, double*, double*)
11        0.2418  apply
11        0.2418  apply_dif
9         0.1978  _int_free
9         0.1978  apply
9         0.1978  checkpoint(unsigned char)
8         0.1759  malloc_consolidate
7         0.1539  FindSpikes(float*, int, int, SETI_WU_INFO&)
6         0.1319  apply
5         0.1099  cnvt_bin_hz(int, int)
4         0.0879  logl
3         0.0659  __dubsin
3         0.0659  __udivsi3
3         0.0659  f_GetPeak(float*, int, int, float, float, float*)
3         0.0659  free
3         0.0659  n1_32
2         0.0440  __dubcos
2         0.0440  q1_4
2         0.0440  t1_4
1         0.0220  __docos
1         0.0220  __ieee754_pow
1         0.0220  csloww
1         0.0220  fftwf_cpy2d_pair
1         0.0220  n1_64
1         0.0220  t1_16
1         0.0220  t1_8
1         0.0220  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
 
 
Sat Aug 20 01:52:44 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_TAKEN events (Any predicted branch that is taken) with a unit mask of 0x00 (No unit mask) count 10000
PC_BRANCH_TAKE...|
  samples|      %|
------------------
   178780 91.2506 seti_boinc
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	   178568 99.8814 seti_boinc
	      212  0.1186 [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
     7505  3.8306 libc-2.11.1.so
     2754  1.4057 libxapian.so.15.6.9
     1530  0.7809 python2.6
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	     1227 80.1961 python2.6
	      285 18.6275 [vectors] (tgid:18116 range:0xffff0000-0xffff1000)
	       18  1.1765 [vectors] (tgid:4694 range:0xffff0000-0xffff1000)
     1511  0.7712 libstdc++.so.6.0.13
      807  0.4119 oprofiled
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	      794 98.3891 oprofiled
	       13  1.6109 [vectors] (tgid:20691 range:0xffff0000-0xffff1000)
      754  0.3848 bash
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	      694 92.0424 bash
	       60  7.9576 [vectors] (tgid:20964 range:0xffff0000-0xffff1000)
      516  0.2634 libz.so.1.2.3.3
      396  0.2021 ld-2.11.1.so
      333  0.1700 libglib-2.0.so.0.2400.1
      280  0.1429 libapt-pkg-libc6.10-6.so.4.8.0
      185  0.0944 libpthread-2.11.1.so
      152  0.0776 modprobe
       65  0.0332 libdbus-1.so.3.4.0
       31  0.0158 Xorg
       29  0.0148 libgobject-2.0.so.0.2400.1
       28  0.0143 libavahi-common.so.3.5.1
       17  0.0087 gawk
       15  0.0077 tr
       14  0.0071 libgvfscommon.so.0.0.0
       13  0.0066 libORBit-2.so.0.1.0
       12  0.0061 libgio-2.0.so.0.2400.1
       11  0.0056 nautilus
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	       11 100.000 [vectors] (tgid:4439 range:0xffff0000-0xffff1000)
       11  0.0056 libX11.so.6.3.0
       11  0.0056 libpulsecommon-0.9.21.so
       11  0.0056 apt_pkg.so
       11  0.0056 ntpd
       10  0.0051 rsyslogd
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        6 60.0000 rsyslogd
	        4 40.0000 [vectors] (tgid:3164 range:0xffff0000-0xffff1000)
        9  0.0046 libpangoft2-1.0.so.0.2800.0
        9  0.0046 _xapian.so
        8  0.0041 libpam.so.0.82.2
        8  0.0041 libavahi-core.so.6.0.1
        8  0.0041 libpulse.so.0.12.2
        8  0.0041 libxcb.so.1.1.0
        7  0.0036 ophelp
        7  0.0036 sudo
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        4 57.1429 sudo
	        3 42.8571 [vectors] (tgid:20964 range:0xffff0000-0xffff1000)
        7  0.0036 libecore-ver-svn-05.so.0.9.9
        6  0.0031 gnome-settings-daemon
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        6 100.000 [vectors] (tgid:4409 range:0xffff0000-0xffff1000)
        6  0.0031 indicator-me-service
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        6 100.000 [vectors] (tgid:4615 range:0xffff0000-0xffff1000)
        6  0.0031 libz160.so
        5  0.0026 libdbus-glib-1.so.2.1.0
        4  0.0020 netbook-launcher-efl
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        4 100.000 [vectors] (tgid:4432 range:0xffff0000-0xffff1000)
        4  0.0020 libgdk-x11-2.0.so.0.2000.1
        3  0.0015 dash
        3  0.0015 libgcc_s.so.1
        3  0.0015 libecore_evas-ver-svn-05.so.0.9.9
        3  0.0015 _glib.so
        2  0.0010 grep
        2  0.0010 gconfd-2
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        2 100.000 [vectors] (tgid:4400 range:0xffff0000-0xffff1000)
        2  0.0010 libpyglib-2.0-python2.6.so.0.0.0
        2  0.0010 libfb.so
        1 5.1e-04 libnss_compat-2.11.1.so
        1 5.1e-04 clock-applet
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4533 range:0xffff0000-0xffff1000)
        1 5.1e-04 libcairo.so.2.10800.10
        1 5.1e-04 libecore_x-ver-svn-05.so.0.9.9
        1 5.1e-04 libgconf-2.so.4.1.5
        1 5.1e-04 libgtk-x11-2.0.so.0.2000.1
        1 5.1e-04 libpango-1.0.so.0.2800.0
        1 5.1e-04 avahi-daemon
	PC_BRANCH_TAKE...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:3189 range:0xffff0000-0xffff1000)
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted PC_BRANCH_TAKEN events (Any predicted branch that is taken) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
27407    15.3300  seti_boinc               v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
26310    14.7164  seti_boinc               cosl
25049    14.0111  seti_boinc               sinl
12745     7.1289  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
9910      5.5431  seti_boinc               rotate_sqrtn_table
9556      5.3451  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
8333      4.6610  seti_boinc               sincos
6329      3.5401  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
4961      2.7749  seti_boinc               GaussFit(float*, int, int)
4787      2.6776  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
4463      2.4964  seti_boinc               fftwf_cpy2d_pair
3925      2.1954  seti_boinc               floor
3380      1.8906  seti_boinc               apply
3332      1.8637  seti_boinc               find_triplets(float const*, int, float, int, int)
2263      1.2658  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
2063      1.1539  seti_boinc               __ieee754_log
2012      1.1254  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
1618      0.9050  seti_boinc               powl
1547      0.8653  seti_boinc               find_pulse(float const*, int, float, int, int)
1450      0.8111  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
1362      0.7618  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
1270      0.7104  seti_boinc               lcgf(double, double)
1126      0.6298  seti_boinc               t1_4
1077      0.6024  seti_boinc               sw_sum3_t31(float**, PoTPlan*)
1008      0.5638  seti_boinc               __ieee754_pow
878       0.4911  seti_boinc               _int_malloc
854       0.4777  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
692       0.3871  seti_boinc               sw_sum4_t31(float**, PoTPlan*)
667       0.3731  seti_boinc               logl
538       0.3009  seti_boinc               sw_sum5_t31(float**, PoTPlan*)
511       0.2858  seti_boinc               __exp1
465       0.2601  seti_boinc               n1_16
448       0.2506  seti_boinc               t1_16
424       0.2372  seti_boinc               _int_free
392       0.2193  seti_boinc               free
327       0.1829  seti_boinc               malloc
315       0.1762  seti_boinc               q1_4
310       0.1734  seti_boinc               fraction_done(double, double)
298       0.1667  seti_boinc               isnanl
283       0.1583  seti_boinc               csloww1
274       0.1533  seti_boinc               TripletProgressUnits()
252       0.1410  seti_boinc               __divsi3
246       0.1376  seti_boinc               time_to_ra_dec(double, double*, double*)
212       0.1186  [vectors] (tgid:10375 range:0xffff0000-0xffff1000) [vectors] (tgid:10375 range:0xffff0000-0xffff1000)
212       0.1186  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
205       0.1147  seti_boinc               checkpoint(unsigned char)
199       0.1113  seti_boinc               n1_32
183       0.1024  seti_boinc               PulseProgressUnits(double, int)
147       0.0822  seti_boinc               apply
138       0.0772  seti_boinc               malloc_consolidate
126       0.0705  seti_boinc               apply_dit
122       0.0682  seti_boinc               operator new(unsigned int)
109       0.0610  seti_boinc               t1_8
95        0.0531  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
90        0.0503  seti_boinc               __udivsi3
76        0.0425  seti_boinc               apply
76        0.0425  seti_boinc               memset
73        0.0408  seti_boinc               boinc_fraction_done
73        0.0408  seti_boinc               operator delete(void*)
70        0.0392  seti_boinc               receiver_config::receiver_config()
69        0.0386  seti_boinc               workunit_grp::workunit_grp()
68        0.0380  seti_boinc               apply_dif
65        0.0364  seti_boinc               gaussian::gaussian()
64        0.0358  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
60        0.0336  seti_boinc               cnvt_bin_hz(int, int)
58        0.0324  seti_boinc               n1_64
57        0.0319  seti_boinc               apply
53        0.0296  seti_boinc               T.9826
46        0.0257  seti_boinc               analysis_config::analysis_config()
38        0.0213  seti_boinc               GAUSS_INFO::GAUSS_INFO()
36        0.0201  seti_boinc               boinc_time_to_checkpoint
35        0.0196  seti_boinc               MFILE::MFILE()
33        0.0185  seti_boinc               T.9822
32        0.0179  seti_boinc               MFILE::~MFILE()
31        0.0173  seti_boinc               calc_detection_freq(double, double, double)
30        0.0168  seti_boinc               recorder_config::recorder_config()
27        0.0151  seti_boinc               workunit_header::workunit_header()
26        0.0145  seti_boinc               finite
26        0.0145  seti_boinc               result::result()
23        0.0129  seti_boinc               GaussianProgressUnits()
23        0.0129  seti_boinc               data_description_t::data_description_t()
21        0.0117  seti_boinc               __dubcos
21        0.0117  seti_boinc               apply
20        0.0112  seti_boinc               __dubsin
20        0.0112  seti_boinc               memmove
19        0.0106  seti_boinc               memcpy
19        0.0106  seti_boinc               splitter_config::splitter_config()
16        0.0089  seti_boinc               csloww
16        0.0089  seti_boinc               t1_32
14        0.0078  seti_boinc               T.9831
10        0.0056  seti_boinc               T.9827
8         0.0045  seti_boinc               tape::tape()
6         0.0034  seti_boinc               t1_64
5         0.0028  seti_boinc               fftwf_cpy2d_pair_co
5         0.0028  seti_boinc               subband_description_t::subband_description_t()
4         0.0022  seti_boinc               __aeabi_read_tp
2         0.0011  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
2         0.0011  seti_boinc               SpikeProgressUnits(int)
2         0.0011  seti_boinc               __docos
2         0.0011  seti_boinc               seti_analyze(ANALYSIS_STATE&)
1        5.6e-04  seti_boinc               __mpn_divrem
1        5.6e-04  seti_boinc               __mpn_mul_1
1        5.6e-04  seti_boinc               gettimeofday
1        5.6e-04  seti_boinc               uselocale
1        5.6e-04  seti_boinc               x_csv_encode_char(unsigned char const*, unsigned int)
 
 
Sat Aug 20 01:56:42 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_NEON_DATA events (NEON data access that hits L1 cache) with a unit mask of 0x00 (No unit mask) count 10000
L1_NEON_DATA:1...|
  samples|      %|
------------------
   763213 99.9984 seti_boinc
        9  0.0012 python2.6
        1 1.3e-04 libc-2.11.1.so
        1 1.3e-04 libcairo.so.2.10800.10
        1 1.3e-04 libpangocairo-1.0.so.0.2800.0
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted L1_NEON_DATA events (NEON data access that hits L1 cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
127449   16.6990  n1_32
125267   16.4131  t1_16
82038    10.7490  cosl
76706    10.0504  sinl
59637     7.8139  n1_16
54624     7.1571  n1_64
34432     4.5115  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
32119     4.2084  q1_4
20024     2.6236  rotate_sqrtn_table
15014     1.9672  t1_4
12923     1.6932  f_GetPeak(float*, int, int, float, float, float*)
12257     1.6060  FindSpikes(float*, int, int, SETI_WU_INFO&)
12217     1.6007  v_GetPowerSpectrum(float (*) [2], float*, int)
11122     1.4573  f_GetTrueMean(float*, int, float, int, int)
10100     1.3234  sincos
9922      1.3000  t1_64
8612      1.1284  fftwf_cpy2d_pair
8351      1.0942  t1_32
7465      0.9781  GaussFit(float*, int, int)
6182      0.8100  __ieee754_log
5227      0.6849  apply
3969      0.5200  __ieee754_pow
3496      0.4581  floor
2953      0.3869  t1_8
2874      0.3766  find_triplets(float const*, int, float, int, int)
2327      0.3049  __exp1
2150      0.2817  analyze_pot(float*, int, ChirpFftPair_t&)
1682      0.2204  f_GetChiSq(float*, int, int, float, float, float*, float*)
1642      0.2151  GetFixedPoT(float*, int, int, float*, int, int)
1233      0.1616  logl
1155      0.1513  sw_sum3_t31(float**, PoTPlan*)
1023      0.1340  lcgf(double, double)
936       0.1226  csloww1
808       0.1059  sw_sum5_t31(float**, PoTPlan*)
755       0.0989  sw_sum4_t31(float**, PoTPlan*)
736       0.0964  float_to_uchar(float*, unsigned char*, long, float)
680       0.0891  find_pulse(float const*, int, float, int, int)
430       0.0563  powl
412       0.0540  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
368       0.0482  isnanl
301       0.0394  TripletProgressUnits()
205       0.0269  fraction_done(double, double)
190       0.0249  time_to_ra_dec(double, double*, double*)
185       0.0242  apply
152       0.0199  apply
138       0.0181  PulseProgressUnits(double, int)
99        0.0130  __dubsin
86        0.0113  cnvt_bin_hz(int, int)
83        0.0109  calc_detection_freq(double, double, double)
73        0.0096  csloww
58        0.0076  __dubcos
46        0.0060  GaussianProgressUnits()
35        0.0046  apply
34        0.0045  apply_dit
34        0.0045  checkpoint(unsigned char)
28        0.0037  GAUSS_INFO::GAUSS_INFO()
25        0.0033  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
19        0.0025  apply_dif
14        0.0018  __udivsi3
14        0.0018  workunit_header::workunit_header()
12        0.0016  fftwf_cpy2d_pair_co
12        0.0016  recorder_config::recorder_config()
12        0.0016  splitter_config::splitter_config()
9         0.0012  tape::tape()
8         0.0010  __docos
7        9.2e-04  workunit_grp::workunit_grp()
3        3.9e-04  SpikeProgressUnits(int)
3        3.9e-04  dtime()
2        2.6e-04  __divsi3
2        2.6e-04  __ieee754_log10
2        2.6e-04  apply
1        1.3e-04  boinc_sleep(double)
1        1.3e-04  fftwf_execute_dft
1        1.3e-04  seti_analyze(ANALYSIS_STATE&)
1        1.3e-04  timer_handler()
1        1.3e-04  timer_thread(void*)

 
Sat Aug 20 04:04:11 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 10000
CYCLES_INST_ST...|
  samples|      %|
------------------
    47983 33.7376 seti_boinc
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	    47433 98.8538 seti_boinc
	      550  1.1462 [vectors] (tgid:4690 range:0xffff0000-0xffff1000)
    23043 16.2019 python2.6
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	    22595 98.0558 python2.6
	      448  1.9442 [vectors] (tgid:4663 range:0xffff0000-0xffff1000)
    21981 15.4552 libc-2.11.1.so
    12536  8.8143 libglib-2.0.so.0.2400.1
     6597  4.6385 bash
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	     6556 99.3785 bash
	       21  0.3183 [vectors] (tgid:5492 range:0xffff0000-0xffff1000)
	       20  0.3032 [vectors] (tgid:5217 range:0xffff0000-0xffff1000)
     5111  3.5936 ld-2.11.1.so
     4106  2.8870 libpthread-2.11.1.so
     2330  1.6383 libdbus-1.so.3.4.0
     1701  1.1960 Xorg
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	     1690 99.3533 Xorg
	       11  0.6467 [vectors] (tgid:3933 range:0xffff0000-0xffff1000)
     1294  0.9098 libX11.so.6.3.0
     1236  0.8691 oprofiled
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	     1199 97.0065 oprofiled
	       37  2.9935 [vectors] (tgid:5214 range:0xffff0000-0xffff1000)
     1135  0.7980 libgio-2.0.so.0.2400.1
     1053  0.7404 libgobject-2.0.so.0.2400.1
      982  0.6905 libxcb.so.1.1.0
      948  0.6666 _glib.so
      929  0.6532 libecore-ver-svn-05.so.0.9.9
      875  0.6152 libpulsecommon-0.9.21.so
      645  0.4535 libavahi-common.so.3.5.1
      553  0.3888 libavahi-core.so.6.0.1
      527  0.3705 libpyglib-2.0-python2.6.so.0.0.0
      510  0.3586 libpulse.so.0.12.2
      465  0.3269 gawk
      424  0.2981 nautilus
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      304 71.6981 nautilus
	      120 28.3019 [vectors] (tgid:4438 range:0xffff0000-0xffff1000)
      390  0.2742 rsyslogd
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      374 95.8974 rsyslogd
	       16  4.1026 [vectors] (tgid:3170 range:0xffff0000-0xffff1000)
      386  0.2714 libdbus-glib-1.so.2.1.0
      346  0.2433 libgthread-2.0.so.0.2400.1
      341  0.2398 libgdk-x11-2.0.so.0.2000.1
      328  0.2306 modprobe
      231  0.1624 libgvfscommon.so.0.0.0
      230  0.1617 libm-2.11.1.so
      186  0.1308 ntpd
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      183 98.3871 ntpd
	        3  1.6129 [vectors] (tgid:4394 range:0xffff0000-0xffff1000)
      182  0.1280 tr
      138  0.0970 avahi-daemon
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      117 84.7826 [vectors] (tgid:3199 range:0xffff0000-0xffff1000)
	       21 15.2174 avahi-daemon
      136  0.0956 libORBit-2.so.0.1.0
      130  0.0914 netbook-launcher-efl
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       91 70.0000 [vectors] (tgid:4431 range:0xffff0000-0xffff1000)
	       39 30.0000 netbook-launcher-efl
      121  0.0851 dbus-daemon
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      119 98.3471 dbus-daemon
	        2  1.6529 [vectors] (tgid:4368 range:0xffff0000-0xffff1000)
      117  0.0823 gnome-settings-daemon
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      111 94.8718 [vectors] (tgid:4408 range:0xffff0000-0xffff1000)
	        6  5.1282 gnome-settings-daemon
       99  0.0696 libgtk-x11-2.0.so.0.2000.1
       96  0.0675 libecore_evas-ver-svn-05.so.0.9.9
       92  0.0647 libpulse-mainloop-glib.so.0.0.4
       83  0.0584 grep
       81  0.0570 libecore_x-ver-svn-05.so.0.9.9
       80  0.0562 libmedia-keys.so
       77  0.0541 libusbmuxd.so.1.0.0
       75  0.0527 libpango-1.0.so.0.2800.0
       75  0.0527 gdm-binary
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       40 53.3333 gdm-binary
	       35 46.6667 [vectors] (tgid:3390 range:0xffff0000-0xffff1000)
       71  0.0499 libdl-2.11.1.so
       71  0.0499 libcairo.so.2.10800.10
       67  0.0471 librt-2.11.1.so
       60  0.0422 ophelp
       58  0.0408 libexa.so
       57  0.0401 sudo
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       42 73.6842 sudo
	       10 17.5439 [vectors] (tgid:5217 range:0xffff0000-0xffff1000)
	        5  8.7719 [vectors] (tgid:5492 range:0xffff0000-0xffff1000)
       47  0.0330 dash
       45  0.0316 indicator-me-service
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       44 97.7778 [vectors] (tgid:4612 range:0xffff0000-0xffff1000)
	        1  2.2222 indicator-me-service
       39  0.0274 libgcc_s.so.1
       39  0.0274 libXau.so.6.0.0
       36  0.0253 libpangoft2-1.0.so.0.2800.0
       35  0.0246 libz160.so
       33  0.0232 clock-applet
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       23 69.6970 [vectors] (tgid:4544 range:0xffff0000-0xffff1000)
	       10 30.3030 clock-applet
       32  0.0225 libevas-ver-svn-05.so.0.9.9
       30  0.0211 libgvfsdbus.so
       28  0.0197 libpam.so.0.82.2
       27  0.0190 libfb.so
       23  0.0162 libncurses.so.5.7
       22  0.0155 libudev.so.0.6.1
       21  0.0148 imx_drv.so
       20  0.0141 libpopt.so.0.0.0
       19  0.0134 libgconf-2.so.4.1.5
       18  0.0127 libpixman-1.so.0.16.4
       16  0.0112 imuxsock.so
       16  0.0112 libglx.so
       15  0.0105 libnss_compat-2.11.1.so
       15  0.0105 libgnome-keyring.so.0.1.1
       14  0.0098 libpangocairo-1.0.so.0.2800.0
       13  0.0091 gnome-session
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       12 92.3077 gnome-session
	        1  7.6923 [vectors] (tgid:4238 range:0xffff0000-0xffff1000)
       13  0.0091 seq
       12  0.0084 gvfsd-metadata
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       10 83.3333 gvfsd-metadata
	        2 16.6667 [vectors] (tgid:4608 range:0xffff0000-0xffff1000)
       11  0.0077 libselinux.so.1
       10  0.0070 cat
       10  0.0070 ls
       10  0.0070 libhousekeeping.so
       10  0.0070 gconfd-2
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        5 50.0000 gconfd-2
	        5 50.0000 [vectors] (tgid:4399 range:0xffff0000-0xffff1000)
       10  0.0070 libpanel-applet-2.so.0.2.67
        9  0.0063 ssh-agent
        9  0.0063 libfreetype.so.6.3.22
        8  0.0056 pam_limits.so
        8  0.0056 indicator-applet-session
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        8 100.000 [vectors] (tgid:4540 range:0xffff0000-0xffff1000)
        8  0.0056 indicator-application-service
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        6 75.0000 [vectors] (tgid:4620 range:0xffff0000-0xffff1000)
	        2 25.0000 indicator-application-service
        8  0.0056 libXrender.so.1.3.0
        8  0.0056 libgsl-fsl.so.1
        7  0.0049 gnome-power-manager
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        6 85.7143 gnome-power-manager
	        1 14.2857 [vectors] (tgid:4441 range:0xffff0000-0xffff1000)
        6  0.0042 libXext.so.6.4.0
        6  0.0042 LC_CTYPE
        5  0.0035 libeggdbus-1.so.0.0.0
        5  0.0035 librecord.so
        4  0.0028 sleep
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        2 50.0000 sleep
	        2 50.0000 [vectors] (tgid:5364 range:0xffff0000-0xffff1000)
        4  0.0028 ld.so.cache
        4  0.0028 libgcrypt.so.11.5.2
        4  0.0028 dirname
        4  0.0028 libmurrine.so
        4  0.0028 cron
        3  0.0021 mkdir
        3  0.0021 rm
        3  0.0021 libnss_files-2.11.1.so
        3  0.0021 id
        3  0.0021 libgioremote-volume-monitor.so
        3  0.0021 gvfsd
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        2 66.6667 gvfsd
	        1 33.3333 [vectors] (tgid:4410 range:0xffff0000-0xffff1000)
        3  0.0021 libpolkit-backend-1.so.0.0.0
        3  0.0021 _dbus_bindings.so
        3  0.0021 console-kit-daemon
        2  0.0014 libnss_nis-2.11.1.so
        2  0.0014 gnome-screensaver
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        2 100.000 [vectors] (tgid:4560 range:0xffff0000-0xffff1000)
        2  0.0014 nm-applet
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        2 100.000 [vectors] (tgid:4435 range:0xffff0000-0xffff1000)
        2  0.0014 gconv-modules.cache
        2  0.0014 libbonoboui-2.so.0.0.0
        2  0.0014 libgdk_pixbuf-2.0.so.0.2000.1
        1 7.0e-04 libcrypt-2.11.1.so
        1 7.0e-04 libnsl-2.11.1.so
        1 7.0e-04 pam_deny.so
        1 7.0e-04 pam_permit.so
        1 7.0e-04 gnome-panel
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4437 range:0xffff0000-0xffff1000)
        1 7.0e-04 libgiogconf.so
        1 7.0e-04 gvfs-afc-volume-monitor
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4426 range:0xffff0000-0xffff1000)
        1 7.0e-04 indicator-applet
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4541 range:0xffff0000-0xffff1000)
        1 7.0e-04 libgconfbackend-xml.so
        1 7.0e-04 libgmodule-2.0.so.0.2400.1
        1 7.0e-04 LC_COLLATE
        1 7.0e-04 LC_PAPER
        1 7.0e-04 LC_TELEPHONE
        1 7.0e-04 pango-basic-fc.so
        1 7.0e-04 polkitd
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4440 range:0xffff0000-0xffff1000)
        1 7.0e-04 imklog.so
        1 7.0e-04 libextmod.so
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
8632     17.9897  seti_boinc               top_sum2(float**, PoTPlan*)
4099      8.5426  seti_boinc               find_pulse(float const*, int, float, int, int)
3368      7.0192  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
2796      5.8271  seti_boinc               _int_malloc
2619      5.4582  seti_boinc               top_sum4(float**, PoTPlan*)
2319      4.8330  seti_boinc               top_sum3(float**, PoTPlan*)
1597      3.3283  seti_boinc               top_sum5(float**, PoTPlan*)
1591      3.3158  seti_boinc               __divsi3
1550      3.2303  seti_boinc               _int_free
1294      2.6968  seti_boinc               n1_64
958       1.9965  seti_boinc               malloc
778       1.6214  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
768       1.6006  seti_boinc               t_funct(int, int, int)
708       1.4755  seti_boinc               __ieee754_log
636       1.3255  seti_boinc               time_to_ra_dec(double, double*, double*)
581       1.2108  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
573       1.1942  seti_boinc               free
550       1.1462  [vectors] (tgid:4690 range:0xffff0000-0xffff1000) [vectors] (tgid:4690 range:0xffff0000-0xffff1000)
480       1.0004  seti_boinc               pulse::pulse()
454       0.9462  seti_boinc               q1_8
434       0.9045  seti_boinc               malloc_consolidate
375       0.7815  seti_boinc               t1_32
362       0.7544  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
344       0.7169  seti_boinc               powl
344       0.7169  seti_boinc               timer_handler()
333       0.6940  seti_boinc               n1_32
330       0.6877  seti_boinc               memset
327       0.6815  seti_boinc               t1_16
276       0.5752  seti_boinc               operator new(unsigned int)
266       0.5544  seti_boinc               PULSE_INFO::PULSE_INFO()
258       0.5377  seti_boinc               cnvt_bin_hz(int, int)
257       0.5356  seti_boinc               receiver_config::receiver_config()
256       0.5335  seti_boinc               operator delete(void*)
223       0.4647  seti_boinc               __udivsi3
213       0.4439  seti_boinc               workunit_grp::workunit_grp()
204       0.4252  seti_boinc               splitter_config::splitter_config()
198       0.4126  seti_boinc               analysis_config::analysis_config()
197       0.4106  seti_boinc               memcpy
195       0.4064  seti_boinc               __ieee754_fmod
195       0.4064  seti_boinc               subband_description_t::subband_description_t()
193       0.4022  seti_boinc               data_description_t::data_description_t()
193       0.4022  seti_boinc               v_BaseLineSmooth(float (*) [2], int, int, int)
192       0.4001  seti_boinc               result::result()
190       0.3960  seti_boinc               __libc_disable_asynccancel
190       0.3960  seti_boinc               boinc_sleep(double)
185       0.3856  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
176       0.3668  seti_boinc               floorf
173       0.3605  seti_boinc               __aeabi_read_tp
169       0.3522  seti_boinc               SpikeProgressUnits(int)
160       0.3335  seti_boinc               PULSE_INFO::~PULSE_INFO()
155       0.3230  seti_boinc               workunit_header::workunit_header()
149       0.3105  seti_boinc               nanosleep
147       0.3064  seti_boinc               find_triplets(float const*, int, float, int, int)
133       0.2772  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
129       0.2688  seti_boinc               calc_detection_freq(double, double, double)
117       0.2438  seti_boinc               fftwf_malloc
110       0.2292  seti_boinc               T.9822
108       0.2251  seti_boinc               ____libc_disable_asynccancel_veneer
108       0.2251  seti_boinc               recorder_config::recorder_config()
104       0.2167  seti_boinc               tape::tape()
99        0.2063  seti_boinc               usleep
94        0.1959  seti_boinc               fftwf_kernel_malloc
91        0.1897  seti_boinc               __ieee754_log10
90        0.1876  seti_boinc               __exp1
88        0.1834  seti_boinc               __default_sa_restorer_v2
88        0.1834  seti_boinc               fmodl
84        0.1751  seti_boinc               seti_analyze(ANALYSIS_STATE&)
76        0.1584  seti_boinc               fftwf_md5putc
75        0.1563  seti_boinc               n1_8
73        0.1521  seti_boinc               __libc_enable_asynccancel
71        0.1480  seti_boinc               search0
71        0.1480  seti_boinc               worker_signal_handler(int)
70        0.1459  seti_boinc               gettimeofday
68        0.1417  seti_boinc               __ieee754_pow
68        0.1417  seti_boinc               t1_8
65        0.1355  seti_boinc               T.9826
61        0.1271  seti_boinc               dtime()
60        0.1250  seti_boinc               fraction_done(double, double)
59        0.1230  seti_boinc               q1_4
57        0.1188  seti_boinc               memmove
53        0.1105  seti_boinc               getrusage
48        0.1000  seti_boinc               T.9827
48        0.1000  seti_boinc               mkplan
44        0.0917  seti_boinc               timer_thread(void*)
42        0.0875  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
42        0.0875  seti_boinc               isinfl
41        0.0854  seti_boinc               invert_lcgf(float, float, float)
38        0.0792  seti_boinc               lcgf(double, double)
37        0.0771  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
37        0.0771  seti_boinc               free_a(void*)
36        0.0750  seti_boinc               t1_4
34        0.0709  seti_boinc               mkplan
32        0.0667  seti_boinc               logl
31        0.0646  seti_boinc               fftwf_kernel_free
29        0.0604  seti_boinc               GetPulsePoTLen(long, int*, int*)
29        0.0604  seti_boinc               apply
28        0.0584  seti_boinc               ____libc_enable_asynccancel_veneer
27        0.0563  seti_boinc               fftwf_md5putb
23        0.0479  seti_boinc               msort_with_tmp
22        0.0458  seti_boinc               fftwf_isqrt
22        0.0458  seti_boinc               isnanl
21        0.0438  seti_boinc               apply_dit
19        0.0396  seti_boinc               GaussianProgressUnits()
19        0.0396  seti_boinc               fftwf_ct_applicable
19        0.0396  seti_boinc               hgrow
19        0.0396  seti_boinc               mkcldw
18        0.0375  seti_boinc               fftwf_free
17        0.0354  seti_boinc               apply
17        0.0354  seti_boinc               fftwf_tensor_compress_contiguous
16        0.0333  seti_boinc               malloc_a(unsigned int, unsigned int)
15        0.0313  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
15        0.0313  seti_boinc               fftwf_plan_destroy_internal
15        0.0313  seti_boinc               htab_insert
13        0.0271  seti_boinc               __aeabi_idivmod
13        0.0271  seti_boinc               apply
13        0.0271  seti_boinc               fftwf_md5int
13        0.0271  seti_boinc               fftwf_tensor_tornk1
12        0.0250  seti_boinc               fftwf_ifree
12        0.0250  seti_boinc               fftwf_mktensor
11        0.0229  seti_boinc               GetProgressUnitSize(int, int)
11        0.0229  seti_boinc               fftwf_pickdim
10        0.0208  seti_boinc               mkplan
9         0.0188  seti_boinc               T.9831
9         0.0188  seti_boinc               __aeabi_uidivmod
9         0.0188  seti_boinc               applicable
8         0.0167  seti_boinc               boinc_worker_thread_cpu_time
8         0.0167  seti_boinc               fftwf_choose_radix
8         0.0167  seti_boinc               fftwf_execute_dft
7         0.0146  seti_boinc               TripletProgressUnits()
7         0.0146  seti_boinc               apply
7         0.0146  seti_boinc               boinc_fraction_done
7         0.0146  seti_boinc               boinc_info
7         0.0146  seti_boinc               fftwf_iabs
7         0.0146  seti_boinc               fftwf_malloc_plain
7         0.0146  seti_boinc               hash
7         0.0146  seti_boinc               log10l
6         0.0125  seti_boinc               fftwf_mkplan_d
6         0.0125  seti_boinc               fftwf_tensor_destroy
6         0.0125  seti_boinc               fftwf_tensor_md5
6         0.0125  seti_boinc               mkplan
6         0.0125  seti_boinc               mkplan
6         0.0125  seti_boinc               qsort_r
6         0.0125  seti_boinc               spike::spike()
5         0.0104  seti_boinc               fftwf_md5unsigned
5         0.0104  seti_boinc               fftwf_tensor_compress
5         0.0104  seti_boinc               mkplan
5         0.0104  seti_boinc               mkplan
5         0.0104  seti_boinc               okp
4         0.0083  seti_boinc               SPIKE_INFO::SPIKE_INFO()
4         0.0083  seti_boinc               analysis_config::operator=(analysis_config const&)
4         0.0083  seti_boinc               apply_dif
4         0.0083  seti_boinc               fftwf_alignment_of
4         0.0083  seti_boinc               fftwf_ct_uglyp
4         0.0083  seti_boinc               fftwf_dft_solve
4         0.0083  seti_boinc               fftwf_dimcmp
4         0.0083  seti_boinc               fftwf_execute
4         0.0083  seti_boinc               fftwf_first_divisor
4         0.0083  seti_boinc               fftwf_mkproblem_dft
4         0.0083  seti_boinc               fftwf_tensor_equal
4         0.0083  seti_boinc               fftwf_tensor_sz
4         0.0083  seti_boinc               mkcldw
4         0.0083  seti_boinc               mkplan
4         0.0083  seti_boinc               mkplan
4         0.0083  seti_boinc               mkplan
4         0.0083  seti_boinc               mkplan
4         0.0083  seti_boinc               mkplan
4         0.0083  seti_boinc               mkplan
4         0.0083  seti_boinc               okp
3         0.0063  seti_boinc               GaussFit(float*, int, int)
3         0.0063  seti_boinc               PulseProgressUnits(double, int)
3         0.0063  seti_boinc               applicable_ip_sq_tiled
3         0.0063  seti_boinc               fftwf_iestimate_cost
3         0.0063  seti_boinc               fftwf_md5INT
3         0.0063  seti_boinc               fftwf_md5puts
3         0.0063  seti_boinc               fftwf_mkproblem_rdft
3         0.0063  seti_boinc               fftwf_ops_madd
3         0.0063  seti_boinc               fftwf_ops_madd2
3         0.0063  seti_boinc               fftwf_tensor_destroy2
3         0.0063  seti_boinc               fftwf_tensor_inplace_strides
3         0.0063  seti_boinc               fftwf_tensor_inplace_strides2
3         0.0063  seti_boinc               mkcldw
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               mkplan
3         0.0063  seti_boinc               qsort
3         0.0063  seti_boinc               receiver_config::operator=(receiver_config const&)
2         0.0042  seti_boinc               applicable_ip_sq
2         0.0042  seti_boinc               applicable_tiled
2         0.0042  seti_boinc               checkpoint(unsigned char)
2         0.0042  seti_boinc               data_description_t::operator=(data_description_t const&)
2         0.0042  seti_boinc               destroy
2         0.0042  seti_boinc               fftwf_mkplan
2         0.0042  seti_boinc               fftwf_mkplan_dft
2         0.0042  seti_boinc               fftwf_mkplan_f_d
2         0.0042  seti_boinc               fftwf_mkproblem
2         0.0042  seti_boinc               fftwf_mkproblem_rdft_1
2         0.0042  seti_boinc               fftwf_mktensor_1d
2         0.0042  seti_boinc               fftwf_nbuf_redundant
2         0.0042  seti_boinc               fftwf_ops_zero
2         0.0042  seti_boinc               fftwf_problem_destroy
2         0.0042  seti_boinc               fftwf_tensor_append
2         0.0042  seti_boinc               fftwf_tensor_copy
2         0.0042  seti_boinc               fftwf_tensor_inplace_locations
2         0.0042  seti_boinc               hash
2         0.0042  seti_boinc               mkplan
2         0.0042  seti_boinc               mkplan
1         0.0021  seti_boinc               ChirpProgressUnits()
1         0.0021  seti_boinc               MFILE::MFILE()
1         0.0021  seti_boinc               MFILE::~MFILE()
1         0.0021  seti_boinc               SPIKE_INFO::operator=(SPIKE_INFO const&)
1         0.0021  seti_boinc               __dubsin
1         0.0021  seti_boinc               __ieee754_exp
1         0.0021  seti_boinc               applicable_iter
1         0.0021  seti_boinc               awake
1         0.0021  seti_boinc               cosl
1         0.0021  seti_boinc               destroy
1         0.0021  seti_boinc               destroy
1         0.0021  seti_boinc               destroy
1         0.0021  seti_boinc               destroy
1         0.0021  seti_boinc               fftwf_ifree0
1         0.0021  seti_boinc               fftwf_imax
1         0.0021  seti_boinc               fftwf_imin
1         0.0021  seti_boinc               fftwf_md5end
1         0.0021  seti_boinc               fftwf_measure_execution_time
1         0.0021  seti_boinc               fftwf_mkplan_rdft
1         0.0021  seti_boinc               fftwf_mktensor_2d
1         0.0021  seti_boinc               fftwf_tensor_copy_except
1         0.0021  seti_boinc               fftwf_tensor_copy_inplace
1         0.0021  seti_boinc               fftwf_tensor_min_ostride
1         0.0021  seti_boinc               mkcld_before
1         0.0021  seti_boinc               mkcldw
1         0.0021  seti_boinc               mkplan
1         0.0021  seti_boinc               mkplan
1         0.0021  seti_boinc               mkplan
1         0.0021  seti_boinc               mkplan
1         0.0021  seti_boinc               mkplan
1         0.0021  seti_boinc               mkplan
1         0.0021  seti_boinc               recorder_config::operator=(recorder_config const&)
1         0.0021  seti_boinc               result::operator=(result const&)
1         0.0021  seti_boinc               sqlblob<unsigned char>::operator=(sqlblob<unsigned char> const&)
1         0.0021  seti_boinc               workunit_grp::operator=(workunit_grp const&)
 
 
Sat Aug 20 04:08:12 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 10000
CYCLES_INST_ST...|
  samples|      %|
------------------
    47536 34.5435 seti_boinc
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	    47042 98.9608 seti_boinc
	      494  1.0392 [vectors] (tgid:4690 range:0xffff0000-0xffff1000)
    22113 16.0691 python2.6
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	    21666 97.9786 python2.6
	      447  2.0214 [vectors] (tgid:4663 range:0xffff0000-0xffff1000)
    21054 15.2995 libc-2.11.1.so
    11660  8.4731 libglib-2.0.so.0.2400.1
     6576  4.7787 bash
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	     6533 99.3461 bash
	       25  0.3802 [vectors] (tgid:6864 range:0xffff0000-0xffff1000)
	       18  0.2737 [vectors] (tgid:6588 range:0xffff0000-0xffff1000)
     4774  3.4692 ld-2.11.1.so
     3745  2.7214 libpthread-2.11.1.so
     2184  1.5871 libdbus-1.so.3.4.0
     1730  1.2572 Xorg
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	     1719 99.3642 Xorg
	       11  0.6358 [vectors] (tgid:3933 range:0xffff0000-0xffff1000)
     1233  0.8960 libX11.so.6.3.0
     1066  0.7746 libgio-2.0.so.0.2400.1
     1052  0.7645 oprofiled
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	     1031 98.0038 oprofiled
	       21  1.9962 [vectors] (tgid:6585 range:0xffff0000-0xffff1000)
      998  0.7252 libxcb.so.1.1.0
      917  0.6664 libgobject-2.0.so.0.2400.1
      917  0.6664 _glib.so
      901  0.6547 libecore-ver-svn-05.so.0.9.9
      829  0.6024 libavahi-common.so.3.5.1
      827  0.6010 libpulsecommon-0.9.21.so
      618  0.4491 libavahi-core.so.6.0.1
      549  0.3989 libpulse.so.0.12.2
      512  0.3721 libpyglib-2.0-python2.6.so.0.0.0
      445  0.3234 gawk
      411  0.2987 nautilus
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      294 71.5328 nautilus
	      117 28.4672 [vectors] (tgid:4438 range:0xffff0000-0xffff1000)
      361  0.2623 rsyslogd
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      334 92.5208 rsyslogd
	       27  7.4792 [vectors] (tgid:3170 range:0xffff0000-0xffff1000)
      358  0.2602 libdbus-glib-1.so.2.1.0
      335  0.2434 libgdk-x11-2.0.so.0.2000.1
      318  0.2311 libgthread-2.0.so.0.2400.1
      294  0.2136 modprobe
      262  0.1904 libgvfscommon.so.0.0.0
      202  0.1468 ntpd
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      198 98.0198 ntpd
	        4  1.9802 [vectors] (tgid:4394 range:0xffff0000-0xffff1000)
      193  0.1402 tr
      187  0.1359 libm-2.11.1.so
      170  0.1235 avahi-daemon
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	      156 91.7647 [vectors] (tgid:3199 range:0xffff0000-0xffff1000)
	       14  8.2353 avahi-daemon
      138  0.1003 netbook-launcher-efl
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       81 58.6957 [vectors] (tgid:4431 range:0xffff0000-0xffff1000)
	       57 41.3043 netbook-launcher-efl
      123  0.0894 libgtk-x11-2.0.so.0.2000.1
      102  0.0741 gnome-settings-daemon
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       98 96.0784 [vectors] (tgid:4408 range:0xffff0000-0xffff1000)
	        4  3.9216 gnome-settings-daemon
      102  0.0741 libORBit-2.so.0.1.0
       90  0.0654 grep
       85  0.0618 libpango-1.0.so.0.2800.0
       84  0.0610 libcairo.so.2.10800.10
       83  0.0603 libecore_evas-ver-svn-05.so.0.9.9
       80  0.0581 libmedia-keys.so
       80  0.0581 libpulse-mainloop-glib.so.0.0.4
       78  0.0567 libecore_x-ver-svn-05.so.0.9.9
       73  0.0530 librt-2.11.1.so
       73  0.0530 libexa.so
       67  0.0487 gdm-binary
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       37 55.2239 [vectors] (tgid:3390 range:0xffff0000-0xffff1000)
	       30 44.7761 gdm-binary
       66  0.0480 libdl-2.11.1.so
       57  0.0414 ophelp
       54  0.0392 libgcc_s.so.1
       48  0.0349 dash
       47  0.0342 libusbmuxd.so.1.0.0
       43  0.0312 libz160.so
       42  0.0305 libncurses.so.5.7
       40  0.0291 libevas-ver-svn-05.so.0.9.9
       39  0.0283 libXau.so.6.0.0
       38  0.0276 sudo
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       29 76.3158 sudo
	        5 13.1579 [vectors] (tgid:6588 range:0xffff0000-0xffff1000)
	        4 10.5263 [vectors] (tgid:6864 range:0xffff0000-0xffff1000)
       37  0.0269 libpangoft2-1.0.so.0.2800.0
       34  0.0247 indicator-me-service
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       34 100.000 [vectors] (tgid:4612 range:0xffff0000-0xffff1000)
       29  0.0211 libgvfsdbus.so
       28  0.0203 libpam.so.0.82.2
       25  0.0182 clock-applet
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	       18 72.0000 [vectors] (tgid:4544 range:0xffff0000-0xffff1000)
	        7 28.0000 clock-applet
       25  0.0182 imuxsock.so
       23  0.0167 seq
       22  0.0160 libfreetype.so.6.3.22
       22  0.0160 libfb.so
       21  0.0153 libpixman-1.so.0.16.4
       20  0.0145 imx_drv.so
       19  0.0138 libglx.so
       17  0.0124 libpopt.so.0.0.0
       16  0.0116 libgnome-keyring.so.0.1.1
       13  0.0094 libselinux.so.1
       12  0.0087 libudev.so.0.6.1
       12  0.0087 libXext.so.6.4.0
       11  0.0080 cat
       11  0.0080 ssh-agent
       11  0.0080 gconfd-2
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        6 54.5455 gconfd-2
	        5 45.4545 [vectors] (tgid:4399 range:0xffff0000-0xffff1000)
       10  0.0073 libXrender.so.1.3.0
       10  0.0073 libpangocairo-1.0.so.0.2800.0
        9  0.0065 libgcrypt.so.11.5.2
        9  0.0065 id
        9  0.0065 libgsl-fsl.so.1
        8  0.0058 ls
        8  0.0058 gnome-power-manager
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        6 75.0000 gnome-power-manager
	        2 25.0000 [vectors] (tgid:4441 range:0xffff0000-0xffff1000)
        7  0.0051 mkdir
        7  0.0051 indicator-applet-session
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        7 100.000 [vectors] (tgid:4540 range:0xffff0000-0xffff1000)
        6  0.0044 librecord.so
        5  0.0036 sleep
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        3 60.0000 sleep
	        2 40.0000 [vectors] (tgid:6733 range:0xffff0000-0xffff1000)
        5  0.0036 LC_CTYPE
        4  0.0029 libnss_compat-2.11.1.so
        4  0.0029 libhousekeeping.so
        4  0.0029 libpanel-applet-2.so.0.2.67
        4  0.0029 libextmod.so
        4  0.0029 cron
        3  0.0022 pam_limits.so
        3  0.0022 gconv-modules.cache
        2  0.0015 rm
        2  0.0015 libnsl-2.11.1.so
        2  0.0015 libnss_files-2.11.1.so
        2  0.0015 expr
        2  0.0015 gvfs-afc-volume-monitor
	CYCLES_INST_ST...|
	  samples|      %|
	------------------
	        2 100.000 [vectors] (tgid:4426 range:0xffff0000-0xffff1000)
        2  0.0015 libfontconfig.so.1.4.4
        2  0.0015 libgconf-2.so.4.1.5
        1 7.3e-04 libcrypt-2.11.1.so
        1 7.3e-04 libnss_nis-2.11.1.so
        1 7.3e-04 pam_ck_connector.so
        1 7.3e-04 pam_gnome_keyring.so
        1 7.3e-04 dirname
        1 7.3e-04 libmurrine.so
        1 7.3e-04 libbonoboui-2.so.0.0.0
        1 7.3e-04 libck-connector.so.0.0.0
        1 7.3e-04 LC_MEASUREMENT
        1 7.3e-04 pango-basic-fc.so
        1 7.3e-04 _heapq.so
        1 7.3e-04 imklog.so
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_INST_STALL events (Cycles where no instruction available) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
10269    21.6026  seti_boinc               top_sum2(float**, PoTPlan*)
4370      9.1930  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
4236      8.9111  seti_boinc               find_pulse(float const*, int, float, int, int)
3072      6.4625  seti_boinc               _int_malloc
2744      5.7725  seti_boinc               top_sum3(float**, PoTPlan*)
2388      5.0236  seti_boinc               top_sum4(float**, PoTPlan*)
1845      3.8813  seti_boinc               __divsi3
1756      3.6940  seti_boinc               top_sum5(float**, PoTPlan*)
1575      3.3133  seti_boinc               _int_free
965       2.0300  seti_boinc               t_funct(int, int, int)
951       2.0006  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
901       1.8954  seti_boinc               malloc
635       1.3358  seti_boinc               malloc_consolidate
606       1.2748  seti_boinc               time_to_ra_dec(double, double*, double*)
603       1.2685  seti_boinc               free
494       1.0392  [vectors] (tgid:4690 range:0xffff0000-0xffff1000) [vectors] (tgid:4690 range:0xffff0000-0xffff1000)
440       0.9256  seti_boinc               memset
439       0.9235  seti_boinc               __ieee754_log
434       0.9130  seti_boinc               pulse::pulse()
414       0.8709  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
384       0.8078  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
314       0.6606  seti_boinc               PULSE_INFO::PULSE_INFO()
295       0.6206  seti_boinc               receiver_config::receiver_config()
277       0.5827  seti_boinc               operator new(unsigned int)
270       0.5680  seti_boinc               timer_handler()
261       0.5491  seti_boinc               cnvt_bin_hz(int, int)
260       0.5470  seti_boinc               workunit_grp::workunit_grp()
249       0.5238  seti_boinc               operator delete(void*)
247       0.5196  seti_boinc               find_triplets(float const*, int, float, int, int)
247       0.5196  seti_boinc               memcpy
227       0.4775  seti_boinc               powl
214       0.4502  seti_boinc               result::result()
213       0.4481  seti_boinc               floorf
212       0.4460  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
199       0.4186  seti_boinc               PULSE_INFO::~PULSE_INFO()
192       0.4039  seti_boinc               workunit_header::workunit_header()
187       0.3934  seti_boinc               __aeabi_read_tp
186       0.3913  seti_boinc               splitter_config::splitter_config()
185       0.3892  seti_boinc               analysis_config::analysis_config()
180       0.3787  seti_boinc               __libc_disable_asynccancel
166       0.3492  seti_boinc               nanosleep
155       0.3261  seti_boinc               subband_description_t::subband_description_t()
154       0.3240  seti_boinc               __ieee754_fmod
154       0.3240  seti_boinc               recorder_config::recorder_config()
150       0.3156  seti_boinc               calc_detection_freq(double, double, double)
147       0.3092  seti_boinc               data_description_t::data_description_t()
142       0.2987  seti_boinc               SpikeProgressUnits(int)
135       0.2840  seti_boinc               boinc_sleep(double)
132       0.2777  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
131       0.2756  seti_boinc               fftwf_malloc
131       0.2756  seti_boinc               tape::tape()
119       0.2503  seti_boinc               n1_16
112       0.2356  seti_boinc               fftwf_kernel_malloc
103       0.2167  seti_boinc               ____libc_disable_asynccancel_veneer
101       0.2125  seti_boinc               T.9822
85        0.1788  seti_boinc               __libc_enable_asynccancel
83        0.1746  seti_boinc               usleep
82        0.1725  seti_boinc               T.9826
82        0.1725  seti_boinc               __ieee754_pow
76        0.1599  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
70        0.1473  seti_boinc               __default_sa_restorer_v2
69        0.1452  seti_boinc               __exp1
69        0.1452  seti_boinc               worker_signal_handler(int)
67        0.1409  seti_boinc               fmodl
66        0.1388  seti_boinc               seti_analyze(ANALYSIS_STATE&)
63        0.1325  seti_boinc               T.9827
63        0.1325  seti_boinc               memmove
55        0.1157  seti_boinc               getrusage
54        0.1136  seti_boinc               gettimeofday
50        0.1052  seti_boinc               dtime()
49        0.1031  seti_boinc               timer_thread(void*)
41        0.0863  seti_boinc               __ieee754_log10
41        0.0863  seti_boinc               free_a(void*)
36        0.0757  seti_boinc               isinfl
33        0.0694  seti_boinc               malloc_a(unsigned int, unsigned int)
30        0.0631  seti_boinc               fftwf_kernel_free
28        0.0589  seti_boinc               fraction_done(double, double)
26        0.0547  seti_boinc               fftwf_free
23        0.0484  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
23        0.0484  seti_boinc               ____libc_enable_asynccancel_veneer
22        0.0463  seti_boinc               isnanl
17        0.0358  seti_boinc               lcgf(double, double)
16        0.0337  seti_boinc               logl
12        0.0252  seti_boinc               T.9831
11        0.0231  seti_boinc               spike::spike()
10        0.0210  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
10        0.0210  seti_boinc               invert_lcgf(float, float, float)
8         0.0168  seti_boinc               TripletProgressUnits()
8         0.0168  seti_boinc               boinc_fraction_done
7         0.0147  seti_boinc               boinc_info
7         0.0147  seti_boinc               log10l
6         0.0126  seti_boinc               checkpoint(unsigned char)
6         0.0126  seti_boinc               vfprintf
5         0.0105  seti_boinc               PulseProgressUnits(double, int)
4         0.0084  seti_boinc               ___printf_fp
4         0.0084  seti_boinc               apply
4         0.0084  seti_boinc               boinc_worker_thread_cpu_time
3         0.0063  seti_boinc               SPIKE_INFO::SPIKE_INFO()
2         0.0042  seti_boinc               analysis_config::operator=(analysis_config const&)
2         0.0042  seti_boinc               boinc_time_to_checkpoint
2         0.0042  seti_boinc               fwrite
2         0.0042  seti_boinc               pulse::print_xml(int, int, int, char const*) const
2         0.0042  seti_boinc               spike::print_xml(int, int, int, char const*) const
2         0.0042  seti_boinc               workunit_grp::operator=(workunit_grp const&)
1         0.0021  seti_boinc               GaussFit(float*, int, int)
1         0.0021  seti_boinc               GaussianProgressUnits()
1         0.0021  seti_boinc               Llastword
1         0.0021  seti_boinc               _IO_default_xsputn
1         0.0021  seti_boinc               _IO_link_in
1         0.0021  seti_boinc               _IO_no_init
1         0.0021  seti_boinc               _IO_setb
1         0.0021  seti_boinc               __cxxabiv1::__si_class_type_info::__do_dyncast(int, __cxxabiv1::__class_type_info::__sub_kind, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info::__dyncast_result&) const
1         0.0021  seti_boinc               __mpn_divrem
1         0.0021  seti_boinc               __mpn_mul_1
1         0.0021  seti_boinc               __udivsi3
1         0.0021  seti_boinc               _int_realloc
1         0.0021  seti_boinc               fftwf_execute_dft
1         0.0021  seti_boinc               finite
1         0.0021  seti_boinc               gaussian::print_xml(int, int, int, char const*) const
1         0.0021  seti_boinc               hack_digit.11765
1         0.0021  seti_boinc               pulse::operator=(pulse const&)
1         0.0021  seti_boinc               receiver_config::operator=(receiver_config const&)
1         0.0021  seti_boinc               result::operator=(result const&)
1         0.0021  seti_boinc               std::basic_ostream<char, std::char_traits<char> >& std::__ostream_insert<char, std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*, int)
1         0.0021  seti_boinc               std::ctype<char> const& std::use_facet<std::ctype<char> >(std::locale const&)
1         0.0021  seti_boinc               std::ios_base::_M_init()
1         0.0021  seti_boinc               std::locale::operator=(std::locale const&)
1         0.0021  seti_boinc               std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::do_put(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, long) const
1         0.0021  seti_boinc               std::ostream& std::ostream::_M_insert<double>(double)
1         0.0021  seti_boinc               std::ostream::flush()
1         0.0021  seti_boinc               std::string::_Rep::_M_destroy(std::allocator<char> const&)
1         0.0021  seti_boinc               std::string::_Rep::_S_create(unsigned int, unsigned int, std::allocator<char> const&)
1         0.0021  seti_boinc               strchrnul
1         0.0021  seti_boinc               strcpy
1         0.0021  seti_boinc               strlen
1         0.0021  seti_boinc               write
 
 
Sat Aug 20 04:12:14 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_INST events (Number of instructions issued in a cycle) with a unit mask of 0x00 (No unit mask) count 10000
CYCLES_INST:10000|
  samples|      %|
------------------
  5275711 94.3842 seti_boinc
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	  5272558 99.9402 seti_boinc
	     3153  0.0598 [vectors] (tgid:4690 range:0xffff0000-0xffff1000)
   185074  3.3110 oprofiled
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	   184747 99.8233 oprofiled
	      327  0.1767 [vectors] (tgid:7957 range:0xffff0000-0xffff1000)
    59675  1.0676 libc-2.11.1.so
    16748  0.2996 python2.6
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	    16166 96.5250 python2.6
	      582  3.4750 [vectors] (tgid:4663 range:0xffff0000-0xffff1000)
    11440  0.2047 bash
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	    10506 91.8357 bash
	      471  4.1171 [vectors] (tgid:8233 range:0xffff0000-0xffff1000)
	      463  4.0472 [vectors] (tgid:7960 range:0xffff0000-0xffff1000)
     8754  0.1566 ld-2.11.1.so
     8676  0.1552 libavahi-common.so.3.5.1
     7798  0.1395 libglib-2.0.so.0.2400.1
     4167  0.0745 libpthread-2.11.1.so
     1400  0.0250 libavahi-core.so.6.0.1
     1317  0.0236 modprobe
     1146  0.0205 libdbus-1.so.3.4.0
     1024  0.0183 Xorg
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	     1013 98.9258 Xorg
	       11  1.0742 [vectors] (tgid:3933 range:0xffff0000-0xffff1000)
      740  0.0132 avahi-daemon
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	      732 98.9189 [vectors] (tgid:3199 range:0xffff0000-0xffff1000)
	        8  1.0811 avahi-daemon
      536  0.0096 libgobject-2.0.so.0.2400.1
      445  0.0080 libX11.so.6.3.0
      404  0.0072 libxcb.so.1.1.0
      381  0.0068 libgio-2.0.so.0.2400.1
      375  0.0067 nautilus
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	      235 62.6667 [vectors] (tgid:4438 range:0xffff0000-0xffff1000)
	      140 37.3333 nautilus
      306  0.0055 libecore-ver-svn-05.so.0.9.9
      229  0.0041 libpulsecommon-0.9.21.so
      220  0.0039 ophelp
      218  0.0039 gawk
      206  0.0037 _glib.so
      203  0.0036 rsyslogd
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	      153 75.3695 rsyslogd
	       50 24.6305 [vectors] (tgid:3170 range:0xffff0000-0xffff1000)
      183  0.0033 gnome-settings-daemon
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	      183 100.000 [vectors] (tgid:4408 range:0xffff0000-0xffff1000)
      171  0.0031 libpyglib-2.0-python2.6.so.0.0.0
      160  0.0029 netbook-launcher-efl
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	      159 99.3750 [vectors] (tgid:4431 range:0xffff0000-0xffff1000)
	        1  0.6250 netbook-launcher-efl
      151  0.0027 tr
      139  0.0025 libpulse.so.0.12.2
      126  0.0023 libpangoft2-1.0.so.0.2800.0
      113  0.0020 libORBit-2.so.0.1.0
      109  0.0020 libdbus-glib-1.so.2.1.0
       97  0.0017 ntpd
       88  0.0016 libgthread-2.0.so.0.2400.1
       85  0.0015 sudo
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	       57 67.0588 sudo
	       19 22.3529 [vectors] (tgid:7960 range:0xffff0000-0xffff1000)
	        9 10.5882 [vectors] (tgid:8233 range:0xffff0000-0xffff1000)
       83  0.0015 libpam.so.0.82.2
       83  0.0015 libgdk-x11-2.0.so.0.2000.1
       74  0.0013 libgvfscommon.so.0.0.0
       63  0.0011 indicator-me-service
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	       63 100.000 [vectors] (tgid:4612 range:0xffff0000-0xffff1000)
       61  0.0011 libz160.so
       53 9.5e-04 dash
       50 8.9e-04 gdm-binary
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	       50 100.000 [vectors] (tgid:3390 range:0xffff0000-0xffff1000)
       44 7.9e-04 libgtk-x11-2.0.so.0.2000.1
       43 7.7e-04 libecore_evas-ver-svn-05.so.0.9.9
       38 6.8e-04 libpango-1.0.so.0.2800.0
       32 5.7e-04 libexa.so
       31 5.5e-04 libcairo.so.2.10800.10
       27 4.8e-04 grep
       27 4.8e-04 libgcc_s.so.1
       22 3.9e-04 libm-2.11.1.so
       22 3.9e-04 clock-applet
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	       20 90.9091 [vectors] (tgid:4544 range:0xffff0000-0xffff1000)
	        2  9.0909 clock-applet
       20 3.6e-04 gconfd-2
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	       17 85.0000 [vectors] (tgid:4399 range:0xffff0000-0xffff1000)
	        3 15.0000 gconfd-2
       20 3.6e-04 libfb.so
       18 3.2e-04 libecore_x-ver-svn-05.so.0.9.9
       17 3.0e-04 libpulse-mainloop-glib.so.0.0.4
       12 2.1e-04 indicator-applet-session
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	       12 100.000 [vectors] (tgid:4540 range:0xffff0000-0xffff1000)
       10 1.8e-04 libdl-2.11.1.so
        9 1.6e-04 libXau.so.6.0.0
        9 1.6e-04 libevas-ver-svn-05.so.0.9.9
        8 1.4e-04 librt-2.11.1.so
        7 1.3e-04 sleep
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	        5 71.4286 [vectors] (tgid:8105 range:0xffff0000-0xffff1000)
	        2 28.5714 sleep
        7 1.3e-04 libgvfsdbus.so
        7 1.3e-04 LC_CTYPE
        7 1.3e-04 imuxsock.so
        6 1.1e-04 ls
        6 1.1e-04 libnss_compat-2.11.1.so
        6 1.1e-04 libselinux.so.1
        6 1.1e-04 libmedia-keys.so
        5 8.9e-05 libncurses.so.5.7
        5 8.9e-05 gconv-modules.cache
        5 8.9e-05 libusbmuxd.so.1.0.0
        5 8.9e-05 imx_drv.so
        4 7.2e-05 libpopt.so.0.0.0
        4 7.2e-05 pam_limits.so
        4 7.2e-05 libXrender.so.1.3.0
        4 7.2e-05 libgconf-2.so.4.1.5
        4 7.2e-05 pango-basic-fc.so
        3 5.4e-05 ld.so.cache
        3 5.4e-05 libnss_files-2.11.1.so
        3 5.4e-05 seq
        3 5.4e-05 libpangocairo-1.0.so.0.2800.0
        3 5.4e-05 LC_COLLATE
        2 3.6e-05 libmurrine.so
        2 3.6e-05 libgsl-fsl.so.1
        2 3.6e-05 libpixman-1.so.0.16.4
        1 1.8e-05 libudev.so.0.6.1
        1 1.8e-05 pam_deny.so
        1 1.8e-05 gnome-power-manager
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4441 range:0xffff0000-0xffff1000)
        1 1.8e-05 ssh-agent
        1 1.8e-05 gvfs-afc-volume-monitor
	CYCLES_INST:10000|
	  samples|      %|
	------------------
	        1 100.000 [vectors] (tgid:4426 range:0xffff0000-0xffff1000)
        1 1.8e-05 libXext.so.6.4.0
        1 1.8e-05 libbonoboui-2.so.0.0.0
        1 1.8e-05 libpanel-applet-2.so.0.2.67
        1 1.8e-05 libextmod.so
        1 1.8e-05 libglx.so
        1 1.8e-05 cron
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_INST events (Number of instructions issued in a cycle) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        image name               symbol name
1916784  36.3148  seti_boinc               top_sum2(float**, PoTPlan*)
1105376  20.9421  seti_boinc               top_sum3(float**, PoTPlan*)
942885   17.8636  seti_boinc               top_sum4(float**, PoTPlan*)
808995   15.3270  seti_boinc               top_sum5(float**, PoTPlan*)
115457    2.1874  seti_boinc               sw_sum2_t31(float**, PoTPlan*)
103967    1.9697  seti_boinc               t_funct(int, int, int)
90839     1.7210  seti_boinc               find_pulse(float const*, int, float, int, int)
41640     0.7889  seti_boinc               __divsi3
14059     0.2664  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
13304     0.2521  seti_boinc               _int_malloc
12331     0.2336  seti_boinc               n1_64
9917      0.1879  seti_boinc               n1_32
8842      0.1675  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
7881      0.1493  seti_boinc               __ieee754_log
7740      0.1466  seti_boinc               find_triplets(float const*, int, float, int, int)
7400      0.1402  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
7135      0.1352  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
6602      0.1251  seti_boinc               memset
5394      0.1022  seti_boinc               _int_free
5090      0.0964  seti_boinc               malloc
3388      0.0642  seti_boinc               time_to_ra_dec(double, double*, double*)
3266      0.0619  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
3222      0.0610  seti_boinc               free
3158      0.0598  [vectors] (tgid:4690 range:0xffff0000-0xffff1000) [vectors] (tgid:4690 range:0xffff0000-0xffff1000)
2548      0.0483  seti_boinc               malloc_consolidate
2015      0.0382  seti_boinc               __ieee754_pow
1951      0.0370  seti_boinc               workunit_grp::workunit_grp()
1784      0.0338  seti_boinc               operator new(unsigned int)
1634      0.0310  seti_boinc               analysis_config::analysis_config()
1308      0.0248  seti_boinc               splitter_config::splitter_config()
1159      0.0220  seti_boinc               pulse::pulse()
1116      0.0211  seti_boinc               data_description_t::data_description_t()
1072      0.0203  seti_boinc               __exp1
1056      0.0200  seti_boinc               calc_detection_freq(double, double, double)
1023      0.0194  seti_boinc               lcgf(double, double)
1021      0.0193  seti_boinc               tape::tape()
1013      0.0192  seti_boinc               receiver_config::receiver_config()
996       0.0189  seti_boinc               result::result()
973       0.0184  seti_boinc               workunit_header::workunit_header()
926       0.0175  seti_boinc               cnvt_bin_hz(int, int)
904       0.0171  seti_boinc               operator delete(void*)
753       0.0143  seti_boinc               PULSE_INFO::~PULSE_INFO()
716       0.0136  seti_boinc               __ieee754_log10
618       0.0117  seti_boinc               logl
575       0.0109  seti_boinc               recorder_config::recorder_config()
563       0.0107  seti_boinc               powl
551       0.0104  seti_boinc               T.9826
534       0.0101  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
529       0.0100  seti_boinc               spike::spike()
495       0.0094  seti_boinc               subband_description_t::subband_description_t()
472       0.0089  seti_boinc               PULSE_INFO::PULSE_INFO()
443       0.0084  seti_boinc               seti_analyze(ANALYSIS_STATE&)
390       0.0074  seti_boinc               T.9822
345       0.0065  seti_boinc               isnanl
342       0.0065  seti_boinc               log10l
314       0.0059  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
261       0.0049  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
261       0.0049  seti_boinc               T.9827
215       0.0041  seti_boinc               SpikeProgressUnits(int)
205       0.0039  seti_boinc               fftwf_malloc
202       0.0038  seti_boinc               fraction_done(double, double)
193       0.0037  seti_boinc               floorf
182       0.0034  seti_boinc               fftwf_execute_dft
165       0.0031  seti_boinc               memcpy
150       0.0028  seti_boinc               T.9831
150       0.0028  seti_boinc               __aeabi_read_tp
142       0.0027  seti_boinc               fftwf_free
141       0.0027  seti_boinc               SPIKE_INFO::SPIKE_INFO()
133       0.0025  seti_boinc               apply
131       0.0025  seti_boinc               free_a(void*)
130       0.0025  seti_boinc               fftwf_kernel_malloc
119       0.0023  seti_boinc               malloc_a(unsigned int, unsigned int)
99        0.0019  seti_boinc               fftwf_kernel_free
83        0.0016  seti_boinc               boinc_fraction_done
66        0.0013  seti_boinc               invert_lcgf(float, float, float)
54        0.0010  seti_boinc               memmove
36       6.8e-04  seti_boinc               timer_handler()
30       5.7e-04  seti_boinc               nanosleep
26       4.9e-04  seti_boinc               worker_signal_handler(int)
23       4.4e-04  seti_boinc               dtime()
22       4.2e-04  seti_boinc               fmodl
18       3.4e-04  seti_boinc               boinc_sleep(double)
17       3.2e-04  seti_boinc               GaussFit(float*, int, int)
16       3.0e-04  seti_boinc               __ieee754_fmod
15       2.8e-04  seti_boinc               __default_sa_restorer_v2
14       2.7e-04  seti_boinc               __libc_disable_asynccancel
14       2.7e-04  seti_boinc               __libc_enable_asynccancel
11       2.1e-04  seti_boinc               getrusage
11       2.1e-04  seti_boinc               timer_thread(void*)
8        1.5e-04  seti_boinc               ___printf_fp
7        1.3e-04  seti_boinc               isinfl
6        1.1e-04  seti_boinc               gettimeofday
6        1.1e-04  seti_boinc               hack_digit.11765
5        9.5e-05  seti_boinc               TripletProgressUnits()
5        9.5e-05  seti_boinc               __mpn_mul_1
5        9.5e-05  seti_boinc               __udivsi3
4        7.6e-05  seti_boinc               PulseProgressUnits(double, int)
4        7.6e-05  seti_boinc               finite
3        5.7e-05  seti_boinc               ____libc_enable_asynccancel_veneer
2        3.8e-05  seti_boinc               __mpn_divrem
2        3.8e-05  seti_boinc               _wordcopy_fwd_aligned
2        3.8e-05  seti_boinc               boinc_worker_thread_cpu_time
2        3.8e-05  seti_boinc               checkpoint(unsigned char)
2        3.8e-05  seti_boinc               std::basic_streambuf<char, std::char_traits<char> >::xsputn(char const*, int)
2        3.8e-05  seti_boinc               std::string::assign(std::string const&)
2        3.8e-05  seti_boinc               strchrnul
2        3.8e-05  seti_boinc               strncpy
2        3.8e-05  seti_boinc               uselocale
2        3.8e-05  seti_boinc               usleep
1        1.9e-05  seti_boinc               Laligned
1        1.9e-05  seti_boinc               MFILE::~MFILE()
1        1.9e-05  seti_boinc               _IO_default_xsputn
1        1.9e-05  seti_boinc               _IO_old_init
1        1.9e-05  seti_boinc               ____libc_disable_asynccancel_veneer
1        1.9e-05  seti_boinc               __mpn_lshift
1        1.9e-05  seti_boinc               boinc_time_to_checkpoint
1        1.9e-05  seti_boinc               floor
1        1.9e-05  seti_boinc               int std::__int_to_char<char, unsigned long>(char*, unsigned long, char const*, std::_Ios_Fmtflags, bool)
1        1.9e-05  seti_boinc               std::__num_base::_S_format_float(std::ios_base const&, char*, char)
1        1.9e-05  seti_boinc               std::basic_string<char, std::char_traits<char>, std::allocator<char> >::basic_string(char const*, unsigned int, std::allocator<char> const&)
1        1.9e-05  seti_boinc               std::locale::~locale()
1        1.9e-05  seti_boinc               std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::do_put(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, long) const
1        1.9e-05  seti_boinc               std::ostream& std::ostream::_M_insert<double>(double)
1        1.9e-05  seti_boinc               std::ostream::sentry::sentry(std::ostream&)
1        1.9e-05  seti_boinc               strlen
1        1.9e-05  seti_boinc               vfprintf
1        1.9e-05  seti_boinc               x_csv_encode_char(unsigned char const*, unsigned int)
1        1.9e-05  seti_boinc               xml_indent(int)
 
 
Sat Aug 20 04:16:15 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_NEON_DATA_STALL events (Number of cycles the processor waits on MRC data from NEON) with a unit mask of 0x00 (No unit mask) count 10000
CYCLES_NEON_DA...|
  samples|      %|
------------------
  7958874 99.9984 seti_boinc
       90  0.0011 python2.6
       18 2.3e-04 libc-2.11.1.so
        9 1.1e-04 libecore-ver-svn-05.so.0.9.9
        4 5.0e-05 libcairo.so.2.10800.10
        2 2.5e-05 libavahi-core.so.6.0.1
        1 1.3e-05 ld-2.11.1.so
        1 1.3e-05 libavahi-common.so.3.5.1
        1 1.3e-05 ntpd
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_NEON_DATA_STALL events (Number of cycles the processor waits on MRC data from NEON) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
1171904  14.7245  top_sum2(float**, PoTPlan*)
920559   11.5664  cosl
880936   11.0686  sinl
716597    9.0037  top_sum3(float**, PoTPlan*)
637068    8.0045  sw_sum2_t31(float**, PoTPlan*)
527489    6.6277  top_sum4(float**, PoTPlan*)
389161    4.8896  top_sum5(float**, PoTPlan*)
315574    3.9651  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
205135    2.5774  v_GetPowerSpectrum(float (*) [2], float*, int)
199688    2.5090  q1_4
198927    2.4994  t1_4
145108    1.8232  lcgf(double, double)
141053    1.7723  f_GetChiSq(float*, int, int, float, float, float*, float*)
114056    1.4331  GaussFit(float*, int, int)
104251    1.3099  find_pulse(float const*, int, float, int, int)
101257    1.2723  FindSpikes(float*, int, int, SETI_WU_INFO&)
90275     1.1343  __ieee754_log
87277     1.0966  analyze_pot(float*, int, ChirpFftPair_t&)
83669     1.0513  floor
77784     0.9773  sw_sum4_t31(float**, PoTPlan*)
74494     0.9360  t1_16
69447     0.8726  sw_sum5_t31(float**, PoTPlan*)
69115     0.8684  GetFixedPoT(float*, int, int, float*, int, int)
68165     0.8565  sincos
60714     0.7628  sw_sum3_t31(float**, PoTPlan*)
60484     0.7600  n1_32
50683     0.6368  f_GetPeak(float*, int, int, float, float, float*)
50343     0.6325  find_triplets(float const*, int, float, int, int)
47279     0.5940  f_GetTrueMean(float*, int, float, int, int)
46083     0.5790  n1_16
45411     0.5706  __ieee754_pow
44484     0.5589  __exp1
38742     0.4868  t1_8
30001     0.3770  float_to_uchar(float*, unsigned char*, long, float)
18951     0.2381  n1_64
11477     0.1442  t1_64
11309     0.1421  csloww1
7350      0.0923  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
5668      0.0712  fraction_done(double, double)
5667      0.0712  logl
5120      0.0643  t1_32
5037      0.0633  time_to_ra_dec(double, double*, double*)
4438      0.0558  powl
3593      0.0451  t_funct(int, int, int)
3523      0.0443  PulseProgressUnits(double, int)
3326      0.0418  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
1573      0.0198  __dubsin
1468      0.0184  __dubcos
1216      0.0153  calc_detection_freq(double, double, double)
946       0.0119  csloww
810       0.0102  cnvt_bin_hz(int, int)
737       0.0093  boinc_fraction_done
684       0.0086  finite
656       0.0082  TripletProgressUnits()
402       0.0051  isnanl
315       0.0040  seti_analyze(ANALYSIS_STATE&)
290       0.0036  SpikeProgressUnits(int)
238       0.0030  apply
171       0.0021  GaussianProgressUnits()
111       0.0014  log10l
103       0.0013  __ieee754_log10
91        0.0011  invert_lcgf(float, float, float)
72       9.0e-04  __docos
59       7.4e-04  floorf
41       5.2e-04  GAUSS_INFO::~GAUSS_INFO()
41       5.2e-04  dtime()
38       4.8e-04  apply
33       4.1e-04  apply
21       2.6e-04  SPIKE_INFO::~SPIKE_INFO()
17       2.1e-04  boinc_sleep(double)
16       2.0e-04  apply_dit
10       1.3e-04  fftwf_execute_dft
10       1.3e-04  fmodl
9        1.1e-04  boinc_worker_thread_cpu_time
5        6.3e-05  pulse::pulse()
5        6.3e-05  result::result()
5        6.3e-05  usleep
4        5.0e-05  PULSE_INFO::PULSE_INFO()
2        2.5e-05  operator delete(void*)
2        2.5e-05  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
1        1.3e-05  GetPulsePoTLen(long, int*, int*)
 
 
Sat Aug 20 04:20:12 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_NEON_INST_STALL events (Number of cycles the processor waits on NEON instruction queue or NEON load queue) with a unit mask of 0x00 (No unit mask) count 10000
CYCLES_NEON_IN...|
  samples|      %|
------------------
  2615686 100.000 seti_boinc
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted CYCLES_NEON_INST_STALL events (Number of cycles the processor waits on NEON instruction queue or NEON load queue) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
641898   24.5403  t1_16
535473   20.4716  n1_32
374948   14.3346  rotate_sqrtn_table
237258    9.0706  n1_64
207160    7.9199  n1_16
105416    4.0301  f_GetPeak(float*, int, int, float, float, float*)
72659     2.7778  t1_8
70583     2.6985  f_GetTrueMean(float*, int, float, int, int)
47575     1.8188  sinl
45454     1.7377  t1_64
42154     1.6116  t1_4
38358     1.4665  apply
37242     1.4238  t1_32
32994     1.2614  __ieee754_pow
28927     1.1059  FindSpikes(float*, int, int, SETI_WU_INFO&)
22900     0.8755  cosl
21424     0.8191  f_GetChiSq(float*, int, int, float, float, float*, float*)
13232     0.5059  GaussFit(float*, int, int)
8697      0.3325  csloww1
6991      0.2673  q1_4
6979      0.2668  find_triplets(float const*, int, float, int, int)
6272      0.2398  lcgf(double, double)
4542      0.1736  find_pulse(float const*, int, float, int, int)
2976      0.1138  __exp1
1480      0.0566  __dubsin
1413      0.0540  __dubcos
540       0.0206  csloww
113       0.0043  sw_sum5_t31(float**, PoTPlan*)
18       6.9e-04  sw_sum4_t31(float**, PoTPlan*)
10       3.8e-04  __ieee754_log
 
 
Sat Aug 20 04:24:10 CST 2011
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted NEON_CYCLES events (Number of cycles NEON and integer processors are not idle) with a unit mask of 0x00 (No unit mask) count 10000
NEON_CYCLES:10000|
  samples|      %|
------------------
  6375055 99.9981 seti_boinc
       69  0.0011 python2.6
       27 4.2e-04 libc-2.11.1.so
        6 9.4e-05 libecore-ver-svn-05.so.0.9.9
        6 9.4e-05 libecore_evas-ver-svn-05.so.0.9.9
        4 6.3e-05 libcairo.so.2.10800.10
        3 4.7e-05 ld-2.11.1.so
        2 3.1e-05 ntpd
        1 1.6e-05 libavahi-common.so.3.5.1
        1 1.6e-05 libpangocairo-1.0.so.0.2800.0
        1 1.6e-05 libpulse.so.0.12.2
 
CPU: ARM V7 PMNC, speed 0 MHz (estimated)
Counted NEON_CYCLES events (Number of cycles NEON and integer processors are not idle) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
1106404  17.3552  cosl
1101414  17.2769  sinl
709129   11.1235  t1_16
523757    8.2157  n1_32
314186    4.9284  n1_16
262026    4.1102  t1_4
246829    3.8718  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
185435    2.9088  n1_64
184402    2.8926  q1_4
144178    2.2616  f_GetChiSq(float*, int, int, float, float, float*, float*)
138033    2.1652  apply
124824    1.9580  rotate_sqrtn_table
114629    1.7981  FindSpikes(float*, int, int, SETI_WU_INFO&)
109388    1.7159  f_GetPeak(float*, int, int, float, float, float*)
83080     1.3032  f_GetTrueMean(float*, int, float, int, int)
78362     1.2292  __ieee754_log
72276     1.1337  t1_32
71965     1.1289  v_GetPowerSpectrum(float (*) [2], float*, int)
71811     1.1264  analyze_pot(float*, int, ChirpFftPair_t&)
71605     1.1232  GetFixedPoT(float*, int, int, float*, int, int)
70771     1.1101  GaussFit(float*, int, int)
68531     1.0750  lcgf(double, double)
65540     1.0281  sincos
53763     0.8433  __ieee754_pow
52963     0.8308  floor
47877     0.7510  __exp1
47091     0.7387  t1_64
33630     0.5275  fftwf_cpy2d_pair
30887     0.4845  sw_sum3_t31(float**, PoTPlan*)
28513     0.4473  t1_8
25539     0.4006  find_triplets(float const*, int, float, int, int)
24159     0.3790  sw_sum4_t31(float**, PoTPlan*)
18785     0.2947  sw_sum5_t31(float**, PoTPlan*)
18006     0.2824  sw_sum2_t31(float**, PoTPlan*)
17655     0.2769  find_pulse(float const*, int, float, int, int)
14308     0.2244  csloww1
7146      0.1121  float_to_uchar(float*, unsigned char*, long, float)
5143      0.0807  logl
4580      0.0718  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
3602      0.0565  powl
3429      0.0538  fraction_done(double, double)
2584      0.0405  time_to_ra_dec(double, double*, double*)
2580      0.0405  __dubsin
2422      0.0380  __dubcos
2303      0.0361  PulseProgressUnits(double, int)
1901      0.0298  TripletProgressUnits()
1467      0.0230  csloww
1018      0.0160  calc_detection_freq(double, double, double)
829       0.0130  isnanl
566       0.0089  GaussianProgressUnits()
537       0.0084  finite
455       0.0071  cnvt_bin_hz(int, int)
340       0.0053  boinc_fraction_done
274       0.0043  apply
257       0.0040  apply
213       0.0033  tape::tape()
178       0.0028  splitter_config::splitter_config()
163       0.0026  workunit_header::workunit_header()
140       0.0022  apply
121       0.0019  recorder_config::recorder_config()
109       0.0017  __docos
108       0.0017  apply_dit
107       0.0017  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
100       0.0016  __udivsi3
83        0.0013  checkpoint(unsigned char)
71        0.0011  GAUSS_INFO::GAUSS_INFO()
69        0.0011  apply_dif
68        0.0011  workunit_grp::workunit_grp()
54       8.5e-04  seti_analyze(ANALYSIS_STATE&)
53       8.3e-04  gaussian::gaussian()
36       5.6e-04  SpikeProgressUnits(int)
36       5.6e-04  apply
33       5.2e-04  fftwf_cpy2d_pair_co
29       4.5e-04  __divsi3
26       4.1e-04  GAUSS_INFO::~GAUSS_INFO()
20       3.1e-04  __ieee754_log10
10       1.6e-04  boinc_sleep(double)
10       1.6e-04  dtime()
8        1.3e-04  subband_description_t::subband_description_t()
6        9.4e-05  log10l
4        6.3e-05  fmodl
3        4.7e-05  boinc_worker_thread_cpu_time
3        4.7e-05  fftwf_execute_dft
3        4.7e-05  gettimeofday
2        3.1e-05  invert_lcgf(float, float, float)
2        3.1e-05  timer_thread(void*)
1        1.6e-05  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
1        1.6e-05  SPIKE_INFO::~SPIKE_INFO()
1        1.6e-05  result::result()
```