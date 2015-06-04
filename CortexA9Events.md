# Events supported by Oprofile on the Cortex-A9 #

```
$ sudo opcontrol --list-events

See Cortex-A9 Technical Reference Manual
Cortex A9 DDI (ARM DDI 0388E, revision r2p0)
PMNC_SW_INCR: (counter: 1, 2, 3, 4, 5, 6)
	Software increment of PMNC registers (min count: 500) 
IFETCH_MISS: (counter: 1, 2, 3, 4, 5, 6)
	Instruction fetch misses from cache or normal cacheable memory (min count: 500) 
ITLB_MISS: (counter: 1, 2, 3, 4, 5, 6)
	Instruction fetch misses from TLB (min count: 500) 
DCACHE_REFILL: (counter: 1, 2, 3, 4, 5, 6)
	Data R/W operation that causes a refill from cache or normal cacheable memory (min count: 
        500) 
DCACHE_ACCESS: (counter: 1, 2, 3, 4, 5, 6)
	Data R/W from cache (min count: 500) 
DTLB_REFILL: (counter: 1, 2, 3, 4, 5, 6)
	Data R/W that causes a TLB refill (min count: 500) 
DREAD: (counter: 1, 2, 3, 4, 5, 6)
	Data read architecturally executed (note: architecturally executed = for instructions that 
        are unconditional or that pass the condition code) (min count: 500) 
DWRITE: (counter: 1, 2, 3, 4, 5, 6)
	Data write architecturally executed (min count: 500) 
INSTR_EXECUTED: (counter: 1, 2, 3, 4, 5, 6)
	All executed instructions (min count: 500) 
EXC_TAKEN: (counter: 1, 2, 3, 4, 5, 6)
	Exception taken (min count: 500) 
EXC_EXECUTED: (counter: 1, 2, 3, 4, 5, 6)
	Exception return architecturally executed (min count: 500) 
CID_WRITE: (counter: 1, 2, 3, 4, 5, 6)
	Instruction that writes to the Context ID Register architecturally executed (min count: 
        500) 
PC_WRITE: (counter: 1, 2, 3, 4, 5, 6)
	SW change of PC, architecturally executed (not by exceptions) (min count: 500) 
PC_IMM_BRANCH: (counter: 1, 2, 3, 4, 5, 6)
	Immediate branch instruction executed (taken or not) (min count: 500) 
PC_PROC_RETURN: (counter: 1, 2, 3, 4, 5, 6)
	Procedure return architecturally executed (not by exceptions) (min count: 500) 
UNALIGNED_ACCESS: (counter: 1, 2, 3, 4, 5, 6)
	Unaligned access architecturally executed (min count: 500) 
PC_BRANCH_MIS_PRED: (counter: 1, 2, 3, 4, 5, 6)
	Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction (min 
        count: 500) 
PC_BRANCH_MIS_USED: (counter: 1, 2, 3, 4, 5, 6)
	Branch or change in program flow that could have been predicted (min count: 500) 
CPU_CYCLES: (counter: 0)
	Number of CPU cycles (min count: 500) 
JAVA_BC_EXEC: (counter: 1, 2, 3, 4, 5, 6)
	Number of Java bytecodes decoded, including speculative ones (min count: 500) 
JAVA_SFTBC_EXEC: (counter: 1, 2, 3, 4, 5, 6)
	Number of software Java bytecodes decoded, including speculative ones (min count: 500) 
JAVA_BB_EXEC: (counter: 1, 2, 3, 4, 5, 6)
	Number of Jazelle taken branches executed, including those flushed due to a previous 
        load/store which aborts late (min count: 500) 
CO_LF_MISS: (counter: 1, 2, 3, 4, 5, 6)
	Number of coherent linefill requests which miss in all other CPUs, meaning that the request 
        is sent to external memory (min count: 500) 
CO_LF_HIT: (counter: 1, 2, 3, 4, 5, 6)
	Number of coherent linefill requests which hit in another CPU, meaning that the linefill 
        data is fetched directly from the relevant cache (min count: 500) 
IC_DEP_STALL: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is ready to accept new instructions but does not receive any 
        because of the instruction side not being able to provide any and the instruction cache is 
        currently performing at least one linefill (min count: 500) 
DC_DEP_STALL: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU has some instructions that it cannot issue to any pipeline and 
        the LSU has at least one pending linefill request but no pending TLB requests (min count: 
        500) 
STREX_PASS: (counter: 1, 2, 3, 4, 5, 6)
	Number of STREX instructions architecturally executed and passed (min count: 500) 
STREX_FAILS: (counter: 1, 2, 3, 4, 5, 6)
	Number of STREX instructions architecturally executed and failed (min count: 500) 
DATA_EVICT: (counter: 1, 2, 3, 4, 5, 6)
	Number of eviction requests due to a linefill in the data cache (min count: 500) 
ISS_NO_DISP: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where the issue stage does not dispatch any instruction (min count: 500) 
ISS_EMPTY: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where the issue stage is empty (min count: 500) 
INS_RENAME: (counter: 1, 2, 3, 4, 5, 6)
	Number of instructions going through the Register Renaming stage (min count: 500) 
PRD_FN_RET: (counter: 1, 2, 3, 4, 5, 6)
	Number of procedure returns whose condition codes do not fail, excluding all exception 
        returns (min count: 500) 
INS_MAIN_EXEC: (counter: 1, 2, 3, 4, 5, 6)
	Number of instructions being executed in main execution pipeline of the CPU, the multiply 
        pipeline and the ALU pipeline (min count: 500) 
INS_SND_EXEC: (counter: 1, 2, 3, 4, 5, 6)
	Number of instructions being executed in the second execution pipeline (ALU) of the CPU 
        (min count: 500) 
INS_LSU: (counter: 1, 2, 3, 4, 5, 6)
	Number of instructions being executed in the Load/Store unit (min count: 500) 
INS_FP_RR: (counter: 1, 2, 3, 4, 5, 6)
	Number of floating-point instructions going through the Register Rename stage (min count: 
        500) 
INS_NEON_RR: (counter: 1, 2, 3, 4, 5, 6)
	Number of NEON instructions going through the Register Rename stage (min count: 500) 
STALL_PLD: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled because PLD slots are all full (min count: 500) 
STALL_WRITE: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled because data side is full and executing writes to 
        external memory (min count: 500) 
STALL_INS_TLB: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled because of main TLB misses on requests issued by the 
        instruction side (min count: 500) 
STALL_DATA_TLB: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled because of main TLB misses on requests issued by the 
        data side (min count: 500) 
STALL_INS_UTLB: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled because of micro TLB misses on the instruction side 
        (min count: 500) 
STALL_DATA_ULTB: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled because of micro TLB misses on the data side (min 
        count: 500) 
STALL_DMB: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles where CPU is stalled due to executed of a DMB memory barrier (min count: 
        500) 
CLK_INT_EN: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles during which the integer core clock is enabled (min count: 500) 
CLK_DE_EN: (counter: 1, 2, 3, 4, 5, 6)
	Number of cycles during which the Data Engine clock is enabled (min count: 500) 
INS_ISB: (counter: 1, 2, 3, 4, 5, 6)
	Number of ISB instructions architecturally executed (min count: 500) 
INS_DSB: (counter: 1, 2, 3, 4, 5, 6)
	Number of DSB instructions architecturally executed (min count: 500) 
INS_DMB: (counter: 1, 2, 3, 4, 5, 6)
	Number of DMB instructions speculatively executed (min count: 500) 
EXT_IRQ: (counter: 1, 2, 3, 4, 5, 6)
	Number of external interrupts executed by the processor (min count: 500) 
PLE_CL_REQ_CMP: (counter: 1, 2, 3, 4, 5, 6)
	PLE cache line request completed (min count: 500) 
PLE_CL_REQ_SKP: (counter: 1, 2, 3, 4, 5, 6)
	PLE cache line request skipped (min count: 500) 
PLE_FIFO_FLSH: (counter: 1, 2, 3, 4, 5, 6)
	PLE FIFO flush (min count: 500) 
PLE_REQ_COMP: (counter: 1, 2, 3, 4, 5, 6)
	PLE request completed (min count: 500) 
PLE_FIFO_OF: (counter: 1, 2, 3, 4, 5, 6)
	PLE FIFO overflow (min count: 500) 
PLE_REQ_PRG: (counter: 1, 2, 3, 4, 5, 6)
	PLE request programmed (min count: 500) 

```

# SETI script used to capture events #

```
#!/bin/bash
# ARM Cortex A9 Oprofile Script
SleepSeconds=532 #on real run
date
#rm state.sah
#sudo opcontrol --shutdown
#./seti_boinc --standalone &

# Running Timer Mode
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=CPU_CYCLES:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
echo "profiling for $SleepSeconds seconds"
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=CO_LF_MISS:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=IC_DEP_STALL:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=DC_DEP_STALL:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=CO_LF_HIT:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt


# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=STALL_INS_TLB:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt




# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=PC_BRANCH_MIS_PRED:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt

# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=PC_BRANCH_MIS_USED:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
date

# Running next event
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=STALL_DATA_TLB:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> ARM_Versatile_Oprofile.txt
opreport >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt
opreport -l /home/user41/seti_boinc/client/seti_boinc >> ARM_Versatile_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> ARM_Versatile_Oprofile.txt
echo " " >> ARM_Versatile_Oprofile.txt



```

```
Wed Sep 14 15:44:48 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 10000
 CPU_CYCLES:10000|
  samples|      %|
------------------
 24781468 82.2385 seti_boinc
  4086166 13.5601 no-vmlinux
  1177955  3.9091 oprofiled
	 CPU_CYCLES:10000|
	  samples|      %|
	------------------
	  1177926 99.9975 oprofiled
	       29  0.0025 [vectors] (tgid:4439 range:0xffff0000-0xffff1000)
    42441  0.1408 libc-2.13.so
    17166  0.0570 bash
	 CPU_CYCLES:10000|
	  samples|      %|
	------------------
	    17165 99.9942 bash
	        1  0.0058 anon (tgid:4596 range:0x400ce000-0x400cf000)
    10322  0.0343 ld-2.13.so
     2017  0.0067 libglib-2.0.so.0.2800.6
     1579  0.0052 libpixman-1.so.0.20.2
     1477  0.0049 thttpd
     1406  0.0047 Xorg
     1131  0.0038 libpthread-2.13.so
      990  0.0033 ntpd
	 CPU_CYCLES:10000|
	  samples|      %|
	------------------
	      978 98.7879 ntpd
	       12  1.2121 [vectors] (tgid:3192 range:0xffff0000-0xffff1000)
      978  0.0032 libcairo.so.2.11000.2
      919  0.0030 libdl-2.13.so
      910  0.0030 libpangoft2-1.0.so.0.2800.4
      807  0.0027 libgobject-2.0.so.0.2800.6
      541  0.0018 libgdk-x11-2.0.so.0.2400.4
      496  0.0016 libgtk-x11-2.0.so.0.2400.4
      361  0.0012 sshd
      332  0.0011 tr
      295 9.8e-04 libX11.so.6.3.0
      290 9.6e-04 libpango-1.0.so.0.2800.4
      278 9.2e-04 libdbus-1.so.3.5.4
      267 8.9e-04 libxcb.so.1.1.0
      266 8.8e-04 ophelp
      259 8.6e-04 libcrypto.so.0.9.8
      256 8.5e-04 libavahi-common.so.3.5.3
      235 7.8e-04 mawk
      163 5.4e-04 libm-2.13.so
      129 4.3e-04 locale-archive
      125 4.1e-04 libfb.so
      115 3.8e-04 librt-2.13.so
      110 3.7e-04 libgio-2.0.so.0.2800.6
      109 3.6e-04 rsyslogd
      108 3.6e-04 sudo
	 CPU_CYCLES:10000|
	  samples|      %|
	------------------
	      105 97.2222 sudo
	        3  2.7778 [heap] (tgid:4591 range:0x2d000-0x53000)
      101 3.4e-04 libavahi-core.so.7.0.2
       98 3.3e-04 grep
       98 3.3e-04 ld.so.cache
       96 3.2e-04 dash
       95 3.2e-04 libORBit-2.so.0.1.0
       61 2.0e-04 libncurses.so.5.7
       58 1.9e-04 libgthread-2.0.so.0.2800.6
       44 1.5e-04 metacity
       37 1.2e-04 libpangocairo-1.0.so.0.2800.4
       32 1.1e-04 gconfd-2
       31 1.0e-04 libshadow.so
       30 1.0e-04 libXrender.so.1.3.0
       29 9.6e-05 libpam.so.0.82.3
       29 9.6e-05 rtkit-daemon
       27 9.0e-05 gdm-simple-greeter
       27 9.0e-05 libgconf-2.so.4.1.5
       24 8.0e-05 libgvfscommon.so.0.0.0
       23 7.6e-05 libnss_compat-2.13.so
       22 7.3e-05 init
       21 7.0e-05 libdbus-glib-1.so.2.1.0
       17 5.6e-05 libselinux.so.1
       16 5.3e-05 libXext.so.6.4.0
       16 5.3e-05 pango-basic-fc.so
       14 4.6e-05 seq
       13 4.3e-05 libpopt.so.0.0.0
       11 3.7e-05 libudev.so.0.11.1
       11 3.7e-05 libextmod.so
       10 3.3e-05 ls
        9 3.0e-05 libresolv-2.13.so
        8 2.7e-05 cron
        6 2.0e-05 cat
        6 2.0e-05 libnih.so.1.0.0
        6 2.0e-05 libmurrine.so
        6 2.0e-05 fbdev_drv.so
        5 1.7e-05 libnsl-2.13.so
        5 1.7e-05 imuxsock.so
        4 1.3e-05 mv
        4 1.3e-05 gnome-settings-daemon
	 CPU_CYCLES:10000|
	  samples|      %|
	------------------
	        4 100.000 [vectors] (tgid:3335 range:0xffff0000-0xffff1000)
        4 1.3e-05 libstartup-notification-1.so.0.0.0
        3 1.0e-05 libdbe.so
        2 6.6e-06 date
        2 6.6e-06 mkdir
        2 6.6e-06 rm
        2 6.6e-06 libgcc_s.so.1
        2 6.6e-06 libnss_dns-2.13.so
        2 6.6e-06 libnss_files-2.13.so
        2 6.6e-06 libnss_nis-2.13.so
        2 6.6e-06 dirname
        2 6.6e-06 gnome-power-manager
        2 6.6e-06 id
        2 6.6e-06 opjitconv
        2 6.6e-06 NetworkManager
        1 3.3e-06 sleep
        1 3.3e-06 expr
        1 3.3e-06 libXcursor.so.1.0.2
        1 3.3e-06 imklog.so
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CPU_CYCLES events (Number of CPU cycles) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
8503681  32.7166  top_sum2(float**, PoTPlan*)
5897750  22.6907  top_sum3(float**, PoTPlan*)
4841951  18.6287  top_sum4(float**, PoTPlan*)
4208220  16.1905  top_sum5(float**, PoTPlan*)
514452    1.9793  sw_sum2_t31(float**, PoTPlan*)
468863    1.8039  find_pulse(float const*, int, float, int, int)
265023    1.0196  t_funct(int, int, int)
156432    0.6018  analyze_pot(float*, int, ChirpFftPair_t&)
115300    0.4436  cftmdl(int, int, float*, float*)
93343     0.3591  GetFixedPoT(float*, int, int, float*, int, int)
62963     0.2422  cft1st(int, float*, float*)
49235     0.1894  find_triplets(float const*, int, float, int, int)
45854     0.1764  bitrv2(int, int*, float*)
45753     0.1760  cosl
39987     0.1538  v_GetPowerSpectrum(float (*) [2], float*, int)
39884     0.1534  _int_malloc
39819     0.1532  malloc
39075     0.1503  sinl
35972     0.1384  free
35550     0.1368  __ieee754_log
34017     0.1309  FindSpikes(float*, int, int, SETI_WU_INFO&)
31175     0.1199  sw_sum5_t31(float**, PoTPlan*)
31006     0.1193  memcpy
30835     0.1186  sw_sum4_t31(float**, PoTPlan*)
30392     0.1169  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
27453     0.1056  .divsi3_skip_div0_test
24840     0.0956  sw_sum3_t31(float**, PoTPlan*)
22589     0.0869  cftfsub(int, float*, float*)
20559     0.0791  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
18947     0.0729  lcgf(double, double)
16538     0.0636  GaussFit(float*, int, int)
15822     0.0609  _int_free
15185     0.0584  f_GetChiSq(float*, int, int, float, float, float*, float*)
13782     0.0530  malloc_consolidate
13587     0.0523  floor
12381     0.0476  f_GetTrueMean(float*, int, float, int, int)
11961     0.0460  time_to_ra_dec(double, double*, double*)
9496      0.0365  f_GetPeak(float*, int, int, float, float, float*)
8500      0.0327  sincos
7818      0.0301  memset
5232      0.0201  logl
5103      0.0196  workunit_grp::workunit_grp()
5088      0.0196  memalign
4651      0.0179  pulse::pulse()
3798      0.0146  calc_detection_freq(double, double, double)
3719      0.0143  analysis_config::analysis_config()
3517      0.0135  operator new(unsigned int)
3439      0.0132  float_to_uchar(float*, unsigned char*, long, float)
3408      0.0131  __divsi3
3194      0.0123  operator delete(void*)
3160      0.0122  isnanl
3070      0.0118  _int_memalign
2958      0.0114  seti_analyze(ANALYSIS_STATE&)
2556      0.0098  result::result()
2542      0.0098  receiver_config::receiver_config()
2118      0.0081  data_description_t::data_description_t()
1876      0.0072  workunit_header::workunit_header()
1759      0.0068  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
1687      0.0065  tape::tape()
1679      0.0065  cnvt_bin_hz(int, int)
1650      0.0063  __ieee754_log10
1575      0.0061  splitter_config::splitter_config()
1485      0.0057  spike::spike()
1422      0.0055  PULSE_INFO::~PULSE_INFO()
1386      0.0053  fraction_done(double, double)
1216      0.0047  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
1204      0.0046  recorder_config::recorder_config()
1157      0.0045  subband_description_t::subband_description_t()
1113      0.0043  __udivsi3
1042      0.0040  PULSE_INFO::PULSE_INFO()
1009      0.0039  PulseProgressUnits(double, int)
1004      0.0039  SPIKE_INFO::~SPIKE_INFO()
938       0.0036  checkpoint(unsigned char)
902       0.0035  log10l
832       0.0032  floorf
767       0.0030  __aeabi_uidivmod
757       0.0029  calloc_a(unsigned int, unsigned int, unsigned int)
750       0.0029  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
650       0.0025  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
642       0.0025  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
605       0.0023  timer_handler()
601       0.0023  TripletProgressUnits()
587       0.0023  csloww1
508       0.0020  cdft(int, int, float (*) [2], int*, float*)
468       0.0018  SpikeProgressUnits(int)
425       0.0016  __kernel_cosf
418       0.0016  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
372       0.0014  nanosleep
350       0.0013  SPIKE_INFO::SPIKE_INFO()
338       0.0013  boinc_fraction_done
338       0.0013  invert_lcgf(float, float, float)
276       0.0011  __default_sa_restorer_v2
247      9.5e-04  __ieee754_fmod
222      8.5e-04  boinc_sleep(double)
221      8.5e-04  gaussian::gaussian()
210      8.1e-04  makewt(int, int*, float*)
209      8.0e-04  timer_thread(void*)
202      7.8e-04  boinc_time_to_checkpoint
197      7.6e-04  worker_signal_handler(int)
191      7.3e-04  fmodl
190      7.3e-04  __dubsin
187      7.2e-04  __libc_disable_asynccancel
183      7.0e-04  usleep
177      6.8e-04  malloc_a(unsigned int, unsigned int)
173      6.7e-04  getrusage
163      6.3e-04  gettimeofday
161      6.2e-04  __libc_enable_asynccancel
155      6.0e-04  dtime()
154      5.9e-04  GAUSS_INFO::~GAUSS_INFO()
148      5.7e-04  sincosf
146      5.6e-04  MFILE::MFILE()
146      5.6e-04  __dubcos
127      4.9e-04  free_a(void*)
125      4.8e-04  __kernel_sinf
109      4.2e-04  MFILE::~MFILE()
80       3.1e-04  ____libc_disable_asynccancel_veneer
77       3.0e-04  ____libc_enable_asynccancel_veneer
73       2.8e-04  isinfl
71       2.7e-04  GaussianProgressUnits()
57       2.2e-04  csloww
54       2.1e-04  GAUSS_INFO::GAUSS_INFO()
19       7.3e-05  boinc_info
14       5.4e-05  __docos
7        2.7e-05  ___printf_fp
7        2.7e-05  hack_digit.11570
5        1.9e-05  plan_PulsePoT(PoTPlan*, int, float*, int*)
5        1.9e-05  std::basic_streambuf<char, std::char_traits<char> >::xsputn(char const*, int)
5        1.9e-05  vfprintf
3        1.2e-05  __strcpy_chk
3        1.2e-05  analysis_config::operator=(analysis_config const&)
3        1.2e-05  boinc_ops_cumulative
3        1.2e-05  result::operator=(result const&)
3        1.2e-05  tape::operator=(tape const&)
3        1.2e-05  workunit_header::operator=(workunit_header const&)
3        1.2e-05  x_csv_encode_char(unsigned char const*, unsigned int)
2        7.7e-06  Laligned
2        7.7e-06  Llastword
2        7.7e-06  _IO_default_xsputn
2        7.7e-06  __mpn_mul_1
2        7.7e-06  gaussian::operator=(gaussian const&)
2        7.7e-06  pulse::operator=(pulse const&)
2        7.7e-06  recorder_config::operator=(recorder_config const&)
2        7.7e-06  std::basic_ostream<char, std::char_traits<char> >& std::__ostream_insert<char, std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*, int)
2        7.7e-06  std::string::assign(std::string const&)
1        3.8e-06  _IO_doallocbuf
1        3.8e-06  _IO_new_file_close_it
1        3.8e-06  _IO_new_file_sync
1        3.8e-06  _IO_new_file_write
1        3.8e-06  __cxxabiv1::__si_class_type_info::__do_dyncast(int, __cxxabiv1::__class_type_info::__sub_kind, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info::__dyncast_result&) const
1        3.8e-06  __mpn_extract_double
1        3.8e-06  bool std::has_facet<std::ctype<char> >(std::locale const&)
1        3.8e-06  cosf
1        3.8e-06  fcntl
1        3.8e-06  fflush
1        3.8e-06  fsync
1        3.8e-06  mempcpy
1        3.8e-06  pulse::print_xml(int, int, int, char const*) const
1        3.8e-06  receiver_config::operator=(receiver_config const&)
1        3.8e-06  spike::operator=(spike const&)
1        3.8e-06  spike::print_xml(int, int, int, char const*) const
1        3.8e-06  splitter_config::operator=(splitter_config const&)
1        3.8e-06  std::__convert_from_v(__locale_struct* const&, char*, int, char const*, ...)
1        3.8e-06  std::basic_stringbuf<char, std::char_traits<char>, std::allocator<char> >::overflow(int)
1        3.8e-06  std::ios_base::_M_init()
1        3.8e-06  std::ios_base::ios_base()
1        3.8e-06  std::ostream& std::ostream::_M_insert<double>(double)
1        3.8e-06  std::ostreambuf_iterator<char, std::char_traits<char> > std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::_M_insert_int<long long>(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, long long) const
1        3.8e-06  std::ostreambuf_iterator<char, std::char_traits<char> > std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::_M_insert_int<long>(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, long) const
1        3.8e-06  std::string::_M_replace_safe(unsigned int, unsigned int, char const*, unsigned int)
1        3.8e-06  std::string::_Rep::_S_create(unsigned int, unsigned int, std::allocator<char> const&)
1        3.8e-06  strchrnul
1        3.8e-06  strcpy
1        3.8e-06  strncpy
1        3.8e-06  vsnprintf
1        3.8e-06  xml_indent(int)
 
 
Wed Sep 14 15:56:12 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_MISS events (Number of coherent linefill requests which miss in all other CPUs, meaning that the request is sent to external memory) with a unit mask of 0x00 (No unit mask) count 10000
 CO_LF_MISS:10000|
  samples|      %|
------------------
   172967 99.2136 seti_boinc
     1062  0.6092 no-vmlinux
      126  0.0723 libc-2.13.so
       60  0.0344 ld-2.13.so
       56  0.0321 bash
       12  0.0069 thttpd
       11  0.0063 Xorg
        9  0.0052 oprofiled
        7  0.0040 libglib-2.0.so.0.2800.6
        7  0.0040 locale-archive
        3  0.0017 libcairo.so.2.11000.2
        2  0.0011 libX11.so.6.3.0
        2  0.0011 libgtk-x11-2.0.so.0.2400.4
        2  0.0011 libpixman-1.so.0.20.2
        1 5.7e-04 libdl-2.13.so
        1 5.7e-04 libpthread-2.13.so
        1 5.7e-04 libselinux.so.1
        1 5.7e-04 init
        1 5.7e-04 ophelp
        1 5.7e-04 libgobject-2.0.so.0.2800.6
        1 5.7e-04 libpangoft2-1.0.so.0.2800.4
        1 5.7e-04 libxcb.so.1.1.0
        1 5.7e-04 gdm-simple-greeter
        1 5.7e-04 libextmod.so
        1 5.7e-04 ntpd
        1 5.7e-04 rsyslogd
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_MISS events (Number of coherent linefill requests which miss in all other CPUs, meaning that the request is sent to external memory) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
66902    38.6791  cftmdl(int, int, float*, float*)
22980    13.2858  bitrv2(int, int*, float*)
11505     6.6516  v_GetPowerSpectrum(float (*) [2], float*, int)
11376     6.5770  cft1st(int, float*, float*)
10200     5.8971  GetFixedPoT(float*, int, int, float*, int, int)
9673      5.5924  memcpy
9146      5.2877  FindSpikes(float*, int, int, SETI_WU_INFO&)
8874      5.1305  cftfsub(int, float*, float*)
8852      5.1177  analyze_pot(float*, int, ChirpFftPair_t&)
5349      3.0925  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
5237      3.0277  floor
1375      0.7949  sinl
270       0.1561  cosl
166       0.0960  __ieee754_log
147       0.0850  GaussFit(float*, int, int)
90        0.0520  find_triplets(float const*, int, float, int, int)
75        0.0434  __dubcos
67        0.0387  _int_malloc
67        0.0387  csloww1
64        0.0370  malloc
59        0.0341  __dubsin
45        0.0260  time_to_ra_dec(double, double*, double*)
40        0.0231  sincos
35        0.0202  checkpoint(unsigned char)
35        0.0202  workunit_grp::workunit_grp()
31        0.0179  f_GetChiSq(float*, int, int, float, float, float*, float*)
19        0.0110  _int_free
17        0.0098  free
16        0.0093  csloww
16        0.0093  f_GetPeak(float*, int, int, float, float, float*)
15        0.0087  analysis_config::analysis_config()
13        0.0075  SPIKE_INFO::~SPIKE_INFO()
13        0.0075  seti_analyze(ANALYSIS_STATE&)
13        0.0075  tape::tape()
12        0.0069  cnvt_bin_hz(int, int)
11        0.0064  malloc_consolidate
10        0.0058  result::result()
10        0.0058  sw_sum2_t31(float**, PoTPlan*)
10        0.0058  sw_sum4_t31(float**, PoTPlan*)
9         0.0052  find_pulse(float const*, int, float, int, int)
9         0.0052  spike::spike()
9         0.0052  sw_sum3_t31(float**, PoTPlan*)
8         0.0046  .divsi3_skip_div0_test
8         0.0046  calc_detection_freq(double, double, double)
8         0.0046  splitter_config::splitter_config()
8         0.0046  workunit_header::workunit_header()
6         0.0035  __divsi3
6         0.0035  f_GetTrueMean(float*, int, float, int, int)
6         0.0035  fraction_done(double, double)
6         0.0035  operator new(unsigned int)
5         0.0029  __udivsi3
5         0.0029  lcgf(double, double)
5         0.0029  operator delete(void*)
4         0.0023  data_description_t::data_description_t()
3         0.0017  sw_sum5_t31(float**, PoTPlan*)
2         0.0012  SPIKE_INFO::SPIKE_INFO()
2         0.0012  __ieee754_log10
2         0.0012  cdft(int, int, float (*) [2], int*, float*)
2         0.0012  float_to_uchar(float*, unsigned char*, long, float)
2         0.0012  logl
2         0.0012  subband_description_t::subband_description_t()
1        5.8e-04  ChirpProgressUnits()
1        5.8e-04  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
1        5.8e-04  GAUSS_INFO::GAUSS_INFO()
1        5.8e-04  MFILE::MFILE()
1        5.8e-04  MFILE::~MFILE()
1        5.8e-04  PulseProgressUnits(double, int)
1        5.8e-04  SpikeProgressUnits(int)
1        5.8e-04  TripletProgressUnits()
1        5.8e-04  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
1        5.8e-04  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
1        5.8e-04  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
1        5.8e-04  __default_sa_restorer_v2
1        5.8e-04  receiver_config::receiver_config()
1        5.8e-04  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
1        5.8e-04  timer_handler()
 
 
Wed Sep 14 16:06:52 PDT 2011
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted IC_DEP_STALL events (Number of cycles where CPU is ready to accept new instructions but does not receive any because of the instruction side not being able to provide any and the instruction cache is currently performing at least one linefill) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
3222     11.2649  sinl
2410      8.4260  cosl
1949      6.8142  cftmdl(int, int, float*, float*)
1807      6.3177  __dubsin
1354      4.7339  __dubcos
1160      4.0557  cft1st(int, float*, float*)
842       2.9439  csloww1
738       2.5802  _int_malloc
736       2.5732  __ieee754_log
706       2.4684  _int_free
585       2.0453  malloc
557       1.9474  bitrv2(int, int*, float*)
526       1.8390  workunit_grp::workunit_grp()
485       1.6957  FindSpikes(float*, int, int, SETI_WU_INFO&)
475       1.6607  csloww
445       1.5558  timer_handler()
358       1.2517  cftfsub(int, float*, float*)
351       1.2272  sincos
336       1.1747  free
320       1.1188  seti_analyze(ANALYSIS_STATE&)
300       1.0489  v_GetPowerSpectrum(float (*) [2], float*, int)
291       1.0174  receiver_config::receiver_config()
288       1.0069  time_to_ra_dec(double, double*, double*)
284       0.9929  floor
262       0.9160  analyze_pot(float*, int, ChirpFftPair_t&)
262       0.9160  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
223       0.7797  isnanl
222       0.7762  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
222       0.7762  checkpoint(unsigned char)
218       0.7622  operator new(unsigned int)
214       0.7482  __docos
198       0.6923  .divsi3_skip_div0_test
192       0.6713  nanosleep
190       0.6643  tape::tape()
186       0.6503  __ieee754_fmod
185       0.6468  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
178       0.6223  __ieee754_log10
177       0.6188  spike::spike()
175       0.6118  calc_detection_freq(double, double, double)
172       0.6014  SPIKE_INFO::SPIKE_INFO()
169       0.5909  GaussFit(float*, int, int)
168       0.5874  usleep
167       0.5839  memcpy
158       0.5524  analysis_config::analysis_config()
152       0.5314  data_description_t::data_description_t()
151       0.5279  cnvt_bin_hz(int, int)
146       0.5105  result::result()
129       0.4510  splitter_config::splitter_config()
124       0.4335  GetFixedPoT(float*, int, int, float*, int, int)
116       0.4056  malloc_consolidate
115       0.4021  logl
114       0.3986  getrusage
113       0.3951  __default_sa_restorer_v2
110       0.3846  log10l
109       0.3811  dtime()
107       0.3741  __libc_enable_asynccancel
106       0.3706  fraction_done(double, double)
106       0.3706  worker_signal_handler(int)
103       0.3601  boinc_sleep(double)
102       0.3566  cdft(int, int, float (*) [2], int*, float*)
102       0.3566  workunit_header::workunit_header()
101       0.3531  gaussian::gaussian()
92        0.3217  ____libc_disable_asynccancel_veneer
92        0.3217  f_GetTrueMean(float*, int, float, int, int)
91        0.3182  __divsi3
90        0.3147  lcgf(double, double)
89        0.3112  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
86        0.3007  timer_thread(void*)
78        0.2727  fmodl
78        0.2727  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
76        0.2657  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
75        0.2622  __libc_disable_asynccancel
72        0.2517  gettimeofday
66        0.2308  boinc_fraction_done
63        0.2203  f_GetPeak(float*, int, int, float, float, float*)
62        0.2168  f_GetChiSq(float*, int, int, float, float, float*, float*)
62        0.2168  isinfl
61        0.2133  recorder_config::recorder_config()
59        0.2063  __udivsi3
56        0.1958  MFILE::~MFILE()
56        0.1958  ____libc_enable_asynccancel_veneer
55        0.1923  operator delete(void*)
46        0.1608  memset
45        0.1573  find_pulse(float const*, int, float, int, int)
45        0.1573  float_to_uchar(float*, unsigned char*, long, float)
41        0.1433  boinc_time_to_checkpoint
39        0.1364  GaussianProgressUnits()
39        0.1364  MFILE::MFILE()
39        0.1364  subband_description_t::subband_description_t()
34        0.1189  GAUSS_INFO::GAUSS_INFO()
33        0.1154  sw_sum5_t31(float**, PoTPlan*)
30        0.1049  SPIKE_INFO::~SPIKE_INFO()
30        0.1049  SpikeProgressUnits(int)
18        0.0629  find_triplets(float const*, int, float, int, int)
17        0.0594  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
17        0.0594  sw_sum4_t31(float**, PoTPlan*)
16        0.0559  anonymous symbol from section .text
13        0.0455  GetPulsePoTLen(long, int*, int*)
12        0.0420  sw_sum3_t31(float**, PoTPlan*)
8         0.0280  boinc_ops_cumulative
7         0.0245  GAUSS_INFO::~GAUSS_INFO()
7         0.0245  sw_sum2_t31(float**, PoTPlan*)
6         0.0210  ChirpProgressUnits()
6         0.0210  boinc_info
5         0.0175  result_group_start()
4         0.0140  PulseProgressUnits(double, int)
3         0.0105  TripletProgressUnits()
2         0.0070  ___printf_fp
2         0.0070  memalign
1         0.0035  _IO_file_close
1         0.0035  __cxxabiv1::__vmi_class_type_info::__do_dyncast(int, __cxxabiv1::__class_type_info::__sub_kind, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info::__dyncast_result&) const
1         0.0035  __dynamic_cast
1         0.0035  __mpn_lshift
1         0.0035  _int_memalign
1         0.0035  invert_lcgf(float, float, float)
1         0.0035  plan_PulsePoT(PoTPlan*, int, float*, int*)
1         0.0035  std::basic_string<char, std::char_traits<char>, std::allocator<char> >::basic_string(unsigned int, char, std::allocator<char> const&)
1         0.0035  t_funct(int, int, int)
1         0.0035  vfprintf
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted IC_DEP_STALL events (Number of cycles where CPU is ready to accept new instructions but does not receive any because of the instruction side not being able to provide any and the instruction cache is currently performing at least one linefill) with a unit mask of 0x00 (No unit mask) count 10000
IC_DEP_STALL:1...|
  samples|      %|
------------------
   146018 79.7429 no-vmlinux
    28602 15.6200 seti_boinc
     2496  1.3631 bash
     1936  1.0573 libc-2.13.so
     1023  0.5587 ld-2.13.so
      384  0.2097 libglib-2.0.so.0.2800.6
      232  0.1267 Xorg
      201  0.1098 ntpd
	IC_DEP_STALL:1...|
	  samples|      %|
	------------------
	      190 94.5274 ntpd
	       11  5.4726 [vectors] (tgid:3192 range:0xffff0000-0xffff1000)
      181  0.0988 libcairo.so.2.11000.2
      157  0.0857 libgobject-2.0.so.0.2800.6
      148  0.0808 libpthread-2.13.so
      140  0.0765 libgdk-x11-2.0.so.0.2400.4
      120  0.0655 oprofiled
      115  0.0628 sshd
      106  0.0579 libgtk-x11-2.0.so.0.2400.4
       94  0.0513 libX11.so.6.3.0
       88  0.0481 libpango-1.0.so.0.2800.4
       79  0.0431 libcrypto.so.0.9.8
       73  0.0399 libpixman-1.so.0.20.2
       71  0.0388 libdbus-1.so.3.5.4
       67  0.0366 libxcb.so.1.1.0
       64  0.0350 mawk
       49  0.0268 librt-2.13.so
       49  0.0268 libavahi-core.so.7.0.2
       46  0.0251 libgio-2.0.so.0.2800.6
       41  0.0224 libavahi-common.so.3.5.3
       36  0.0197 rsyslogd
       35  0.0191 libpangoft2-1.0.so.0.2800.4
       34  0.0186 tr
       31  0.0169 libm-2.13.so
       28  0.0153 libncurses.so.5.7
       28  0.0153 thttpd
       21  0.0115 grep
       21  0.0115 locale-archive
       20  0.0109 libgthread-2.0.so.0.2800.6
       18  0.0098 libdl-2.13.so
       18  0.0098 sudo
       18  0.0098 libORBit-2.so.0.1.0
       18  0.0098 libfb.so
       17  0.0093 libgvfscommon.so.0.0.0
       16  0.0087 libXrender.so.1.3.0
       16  0.0087 gdm-simple-greeter
       15  0.0082 ophelp
       13  0.0071 libdbus-glib-1.so.2.1.0
       12  0.0066 dash
       12  0.0066 metacity
       12  0.0066 libXext.so.6.4.0
       11  0.0060 libpangocairo-1.0.so.0.2800.4
       11  0.0060 rtkit-daemon
        7  0.0038 gconfd-2
        6  0.0033 libpopt.so.0.0.0
        6  0.0033 seq
        6  0.0033 libshadow.so
        5  0.0027 cat
        3  0.0016 libnss_compat-2.13.so
        3  0.0016 libmurrine.so
        3  0.0016 libgconf-2.so.4.1.5
        3  0.0016 cron
        2  0.0011 mkdir
        2  0.0011 rm
        2  0.0011 libresolv-2.13.so
        2  0.0011 libselinux.so.1
        2  0.0011 libnih.so.1.0.0
        2  0.0011 gnome-power-manager
        2  0.0011 pango-basic-fc.so
        2  0.0011 gnome-settings-daemon
	IC_DEP_STALL:1...|
	  samples|      %|
	------------------
	        2 100.000 [vectors] (tgid:3335 range:0xffff0000-0xffff1000)
        2  0.0011 libstartup-notification-1.so.0.0.0
        2  0.0011 avahi-daemon
        1 5.5e-04 libnsl-2.13.so
        1 5.5e-04 libnss_dns-2.13.so
        1 5.5e-04 dirname
        1 5.5e-04 expr
        1 5.5e-04 id
        1 5.5e-04 fbdev_drv.so
        1 5.5e-04 libextmod.so
        1 5.5e-04 NetworkManager
 
 
Wed Sep 14 16:21:42 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted IC_DEP_STALL events (Number of cycles where CPU is ready to accept new instructions but does not receive any because of the instruction side not being able to provide any and the instruction cache is currently performing at least one linefill) with a unit mask of 0x00 (No unit mask) count 10000
IC_DEP_STALL:1...|
  samples|      %|
------------------
   196090 79.5868 no-vmlinux
    40813 16.5647 seti_boinc
     2326  0.9441 bash
     2145  0.8706 libc-2.13.so
      984  0.3994 ld-2.13.so
      611  0.2480 libglib-2.0.so.0.2800.6
      339  0.1376 Xorg
      294  0.1193 ntpd
	IC_DEP_STALL:1...|
	  samples|      %|
	------------------
	      284 96.5986 ntpd
	       10  3.4014 [vectors] (tgid:3192 range:0xffff0000-0xffff1000)
      260  0.1055 libcairo.so.2.11000.2
      222  0.0901 libpthread-2.13.so
      217  0.0881 libgdk-x11-2.0.so.0.2400.4
      199  0.0808 libgobject-2.0.so.0.2800.6
      184  0.0747 libgtk-x11-2.0.so.0.2400.4
      156  0.0633 libX11.so.6.3.0
      120  0.0487 oprofiled
	IC_DEP_STALL:1...|
	  samples|      %|
	------------------
	      119 99.1667 oprofiled
	        1  0.8333 [vectors] (tgid:8330 range:0xffff0000-0xffff1000)
      119  0.0483 libpango-1.0.so.0.2800.4
      110  0.0446 libxcb.so.1.1.0
      109  0.0442 libdbus-1.so.3.5.4
       91  0.0369 libpixman-1.so.0.20.2
       60  0.0244 sshd
       57  0.0231 mawk
       55  0.0223 rsyslogd
       52  0.0211 libavahi-core.so.7.0.2
       51  0.0207 libpangoft2-1.0.so.0.2800.4
       50  0.0203 thttpd
       46  0.0187 librt-2.13.so
       42  0.0170 libcrypto.so.0.9.8
       38  0.0154 libavahi-common.so.3.5.3
       38  0.0154 libfb.so
       37  0.0150 libm-2.13.so
       37  0.0150 tr
       35  0.0142 libgio-2.0.so.0.2800.6
       28  0.0114 sudo
       27  0.0110 libgthread-2.0.so.0.2800.6
       22  0.0089 grep
       21  0.0085 libgvfscommon.so.0.0.0
       20  0.0081 libncurses.so.5.7
       19  0.0077 libdl-2.13.so
       19  0.0077 libXrender.so.1.3.0
       19  0.0077 libORBit-2.so.0.1.0
       19  0.0077 rtkit-daemon
       18  0.0073 metacity
       16  0.0065 gdm-simple-greeter
       11  0.0045 libpangocairo-1.0.so.0.2800.4
       11  0.0045 gconfd-2
       10  0.0041 dash
       10  0.0041 libdbus-glib-1.so.2.1.0
        9  0.0037 libpam.so.0.82.3
        9  0.0037 libresolv-2.13.so
        9  0.0037 ophelp
        9  0.0037 libshadow.so
        7  0.0028 libmurrine.so
        6  0.0024 libpopt.so.0.0.0
        6  0.0024 locale-archive
        5  0.0020 libXext.so.6.4.0
        5  0.0020 gnome-settings-daemon
	IC_DEP_STALL:1...|
	  samples|      %|
	------------------
	        5 100.000 [vectors] (tgid:3335 range:0xffff0000-0xffff1000)
        5  0.0020 libgconf-2.so.4.1.5
        4  0.0016 libnss_dns-2.13.so
        4  0.0016 libextmod.so
        4  0.0016 cron
        3  0.0012 cat
        3  0.0012 ls
        3  0.0012 libnss_compat-2.13.so
        3  0.0012 libnss_nis-2.13.so
        3  0.0012 libselinux.so.1
        3  0.0012 gnome-power-manager
        3  0.0012 seq
        2 8.1e-04 rm
        2 8.1e-04 libnsl-2.13.so
        2 8.1e-04 libudev.so.0.11.1
        2 8.1e-04 id
        2 8.1e-04 pango-basic-fc.so
        2 8.1e-04 libstartup-notification-1.so.0.0.0
        2 8.1e-04 imuxsock.so
        1 4.1e-04 ld.so.cache
        1 4.1e-04 libacl.so.1.1.0
        1 4.1e-04 libgcc_s.so.1
        1 4.1e-04 libnss_files-2.13.so
        1 4.1e-04 pam_unix.so
        1 4.1e-04 libnih.so.1.0.0
        1 4.1e-04 init
        1 4.1e-04 dirname
        1 4.1e-04 expr
        1 4.1e-04 gnome-screensaver
        1 4.1e-04 avahi-daemon
Wed Sep 14 16:21:50 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted IC_DEP_STALL events (Number of cycles where CPU is ready to accept new instructions but does not receive any because of the instruction side not being able to provide any and the instruction cache is currently performing at least one linefill) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
5631     13.7971  sinl
4211     10.3178  cosl
2634      6.4538  cftmdl(int, int, float*, float*)
2587      6.3387  __dubsin
1901      4.6578  __dubcos
1725      4.2266  cft1st(int, float*, float*)
1258      3.0824  csloww1
872       2.1366  _int_free
848       2.0778  _int_malloc
836       2.0484  __ieee754_log
800       1.9602  bitrv2(int, int*, float*)
755       1.8499  csloww
741       1.8156  malloc
666       1.6318  workunit_grp::workunit_grp()
657       1.6098  timer_handler()
641       1.5706  FindSpikes(float*, int, int, SETI_WU_INFO&)
630       1.5436  sincos
527       1.2913  floor
502       1.2300  seti_analyze(ANALYSIS_STATE&)
458       1.1222  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
451       1.1050  free
443       1.0854  v_GetPowerSpectrum(float (*) [2], float*, int)
413       1.0119  cftfsub(int, float*, float*)
363       0.8894  time_to_ra_dec(double, double*, double*)
347       0.8502  analyze_pot(float*, int, ChirpFftPair_t&)
322       0.7890  receiver_config::receiver_config()
303       0.7424  isnanl
297       0.7277  nanosleep
288       0.7057  __docos
287       0.7032  operator new(unsigned int)
282       0.6910  checkpoint(unsigned char)
282       0.6910  spike::spike()
271       0.6640  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
259       0.6346  calc_detection_freq(double, double, double)
250       0.6125  __ieee754_fmod
242       0.5929  tape::tape()
238       0.5831  __ieee754_log10
236       0.5782  memcpy
234       0.5733  .divsi3_skip_div0_test
221       0.5415  SPIKE_INFO::SPIKE_INFO()
220       0.5390  data_description_t::data_description_t()
213       0.5219  usleep
200       0.4900  cnvt_bin_hz(int, int)
179       0.4386  boinc_sleep(double)
175       0.4288  analysis_config::analysis_config()
174       0.4263  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
169       0.4141  __default_sa_restorer_v2
167       0.4092  dtime()
167       0.4092  malloc_consolidate
165       0.4043  splitter_config::splitter_config()
160       0.3920  cdft(int, int, float (*) [2], int*, float*)
160       0.3920  getrusage
154       0.3773  logl
154       0.3773  timer_thread(void*)
149       0.3651  ____libc_disable_asynccancel_veneer
143       0.3504  __libc_enable_asynccancel
139       0.3406  fraction_done(double, double)
133       0.3259  result::result()
132       0.3234  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
131       0.3210  gaussian::gaussian()
127       0.3112  workunit_header::workunit_header()
125       0.3063  log10l
118       0.2891  worker_signal_handler(int)
110       0.2695  boinc_fraction_done
108       0.2646  GetFixedPoT(float*, int, int, float*, int, int)
103       0.2524  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
103       0.2524  __divsi3
101       0.2475  fmodl
96        0.2352  GaussFit(float*, int, int)
95        0.2328  find_pulse(float const*, int, float, int, int)
93        0.2279  __libc_disable_asynccancel
91        0.2230  gettimeofday
76        0.1862  recorder_config::recorder_config()
74        0.1813  ____libc_enable_asynccancel_veneer
74        0.1813  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
71        0.1740  isinfl
70        0.1715  subband_description_t::subband_description_t()
65        0.1593  MFILE::~MFILE()
62        0.1519  sw_sum5_t31(float**, PoTPlan*)
60        0.1470  __udivsi3
58        0.1421  operator delete(void*)
54        0.1323  f_GetTrueMean(float*, int, float, int, int)
49        0.1201  f_GetChiSq(float*, int, int, float, float, float*, float*)
49        0.1201  lcgf(double, double)
46        0.1127  SpikeProgressUnits(int)
46        0.1127  boinc_time_to_checkpoint
46        0.1127  sw_sum2_t31(float**, PoTPlan*)
42        0.1029  SPIKE_INFO::~SPIKE_INFO()
35        0.0858  memset
33        0.0809  sw_sum3_t31(float**, PoTPlan*)
30        0.0735  find_triplets(float const*, int, float, int, int)
29        0.0711  anonymous symbol from section .text
27        0.0662  MFILE::MFILE()
23        0.0564  float_to_uchar(float*, unsigned char*, long, float)
23        0.0564  sw_sum4_t31(float**, PoTPlan*)
22        0.0539  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
21        0.0515  GaussianProgressUnits()
19        0.0466  f_GetPeak(float*, int, int, float, float, float*)
17        0.0417  GAUSS_INFO::GAUSS_INFO()
15        0.0368  boinc_info
14        0.0343  GetPulsePoTLen(long, int*, int*)
12        0.0294  boinc_ops_cumulative
11        0.0270  top_sum4(float**, PoTPlan*)
10        0.0245  pulse::pulse()
10        0.0245  top_sum3(float**, PoTPlan*)
9         0.0221  result_group_start()
5         0.0123  memalign
4         0.0098  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
3         0.0074  ChirpProgressUnits()
2         0.0049  PulseProgressUnits(double, int)
2         0.0049  __aeabi_idivmod
2         0.0049  __aeabi_uidivmod
2         0.0049  calloc_a(unsigned int, unsigned int, unsigned int)
2         0.0049  vfprintf
1         0.0025  GAUSS_INFO::~GAUSS_INFO()
1         0.0025  Llastword
1         0.0025  PULSE_INFO::PULSE_INFO()
1         0.0025  TripletProgressUnits()
1         0.0025  _IO_link_in
1         0.0025  _IO_setb
1         0.0025  ___vsnprintf_chk
1         0.0025  __dbl_mp
1         0.0025  __mpn_lshift
1         0.0025  __mpn_mul_1
1         0.0025  fclose
1         0.0025  floorf
1         0.0025  free_a(void*)
1         0.0025  fsync
1         0.0025  invert_lcgf(float, float, float)
1         0.0025  plan_PulsePoT(PoTPlan*, int, float*, int*)
1         0.0025  std::basic_streambuf<char, std::char_traits<char> >::xsputn(char const*, int)
1         0.0025  std::ostream::flush()
1         0.0025  std::ostream::sentry::sentry(std::ostream&)
1         0.0025  std::ostreambuf_iterator<char, std::char_traits<char> > std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::_M_insert_float<double>(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, char, double) const
1         0.0025  std::ostreambuf_iterator<char, std::char_traits<char> > std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::_M_insert_int<long>(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, long) const
1         0.0025  std::string::_Rep::_M_clone(std::allocator<char> const&, unsigned int)
1         0.0025  std::string::swap(std::string&)
1         0.0025  strchr
1         0.0025  t_funct(int, int, int)
1         0.0025  x_csv_encode_char(unsigned char const*, unsigned int)
Wed Sep 14 16:22:08 PDT 2011
Wed Sep 14 16:22:11 PDT 2011
Wed Sep 14 16:32:55 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 10000
PC_BRANCH_MIS_...|
  samples|      %|
------------------
    30571 85.9726 seti_boinc
     4331 12.1798 no-vmlinux
      271  0.7621 libc-2.13.so
      166  0.4668 bash
       74  0.2081 ld-2.13.so
       18  0.0506 oprofiled
       16  0.0450 libglib-2.0.so.0.2800.6
       16  0.0450 libcairo.so.2.11000.2
       10  0.0281 libpixman-1.so.0.20.2
        8  0.0225 libgobject-2.0.so.0.2800.6
        6  0.0169 libpthread-2.13.so
        6  0.0169 libncurses.so.5.7
        6  0.0169 Xorg
        6  0.0169 libpangoft2-1.0.so.0.2800.4
        6  0.0169 libgdk-x11-2.0.so.0.2400.4
        5  0.0141 mawk
        5  0.0141 ophelp
        5  0.0141 libgtk-x11-2.0.so.0.2400.4
        5  0.0141 ntpd
	PC_BRANCH_MIS_...|
	  samples|      %|
	------------------
	        4 80.0000 ntpd
	        1 20.0000 [vectors] (tgid:3192 range:0xffff0000-0xffff1000)
        4  0.0112 libavahi-core.so.7.0.2
        3  0.0084 tr
        3  0.0084 sshd
        2  0.0056 libdbus-1.so.3.5.4
        2  0.0056 libdl-2.13.so
        2  0.0056 libavahi-common.so.3.5.3
        2  0.0056 libxcb.so.1.1.0
        2  0.0056 libfb.so
        1  0.0028 dash
        1  0.0028 libm-2.13.so
        1  0.0028 sudo
        1  0.0028 libX11.so.6.3.0
        1  0.0028 libXrender.so.1.3.0
        1  0.0028 libgthread-2.0.so.0.2800.6
        1  0.0028 libmurrine.so
        1  0.0028 libORBit-2.so.0.1.0
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted PC_BRANCH_MIS_PRED events (Branch mispredicted or not predicted. Counts pipeline flushes because of misprediction) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
5588     18.2788  sinl
4811     15.7371  cosl
4294     14.0460  sw_sum2_t31(float**, PoTPlan*)
1321      4.3211  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
1055      3.4510  sw_sum4_t31(float**, PoTPlan*)
920       3.0094  analyze_pot(float*, int, ChirpFftPair_t&)
913       2.9865  __ieee754_log
896       2.9309  find_pulse(float const*, int, float, int, int)
799       2.6136  free
763       2.4958  top_sum2(float**, PoTPlan*)
747       2.4435  f_GetTrueMean(float*, int, float, int, int)
741       2.4239  _int_malloc
700       2.2898  sw_sum3_t31(float**, PoTPlan*)
691       2.2603  sw_sum5_t31(float**, PoTPlan*)
532       1.7402  GaussFit(float*, int, int)
456       1.4916  csloww1
454       1.4851  top_sum3(float**, PoTPlan*)
340       1.1122  malloc
269       0.8799  lcgf(double, double)
266       0.8701  top_sum4(float**, PoTPlan*)
263       0.8603  floor
249       0.8145  sincos
244       0.7981  f_GetPeak(float*, int, int, float, float, float*)
216       0.7066  GetFixedPoT(float*, int, int, float*, int, int)
191       0.6248  malloc_consolidate
189       0.6182  find_triplets(float const*, int, float, int, int)
173       0.5659  time_to_ra_dec(double, double*, double*)
164       0.5365  checkpoint(unsigned char)
158       0.5168  top_sum5(float**, PoTPlan*)
156       0.5103  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
137       0.4481  bitrv2(int, int*, float*)
136       0.4449  logl
127       0.4154  cftmdl(int, int, float*, float*)
111       0.3631  workunit_grp::workunit_grp()
100       0.3271  f_GetChiSq(float*, int, int, float, float, float*, float*)
91        0.2977  __dubsin
89        0.2911  memset
73        0.2388  float_to_uchar(float*, unsigned char*, long, float)
69        0.2257  __dubcos
66        0.2159  csloww
66        0.2159  recorder_config::recorder_config()
65        0.2126  GaussianProgressUnits()
64        0.2093  FindSpikes(float*, int, int, SETI_WU_INFO&)
64        0.2093  _int_free
63        0.2061  .divsi3_skip_div0_test
48        0.1570  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
45        0.1472  receiver_config::receiver_config()
41        0.1341  t_funct(int, int, int)
39        0.1276  MFILE::~MFILE()
39        0.1276  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
33        0.1079  __docos
32        0.1047  __udivsi3
31        0.1014  boinc_time_to_checkpoint
28        0.0916  workunit_header::workunit_header()
26        0.0850  operator new(unsigned int)
26        0.0850  subband_description_t::subband_description_t()
21        0.0687  operator delete(void*)
21        0.0687  result::result()
21        0.0687  tape::tape()
19        0.0622  seti_analyze(ANALYSIS_STATE&)
16        0.0523  fraction_done(double, double)
15        0.0491  analysis_config::analysis_config()
13        0.0425  PulseProgressUnits(double, int)
13        0.0425  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
13        0.0425  __divsi3
13        0.0425  cnvt_bin_hz(int, int)
13        0.0425  v_GetPowerSpectrum(float (*) [2], float*, int)
12        0.0393  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
12        0.0393  isnanl
11        0.0360  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
11        0.0360  cftfsub(int, float*, float*)
8         0.0262  timer_handler()
7         0.0229  memcpy
6         0.0196  SpikeProgressUnits(int)
5         0.0164  boinc_sleep(double)
5         0.0164  cft1st(int, float*, float*)
4         0.0131  SPIKE_INFO::SPIKE_INFO()
3         0.0098  PULSE_INFO::PULSE_INFO()
3         0.0098  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
3         0.0098  __ieee754_log10
3         0.0098  data_description_t::data_description_t()
3         0.0098  gettimeofday
3         0.0098  malloc_a(unsigned int, unsigned int)
2         0.0065  __aeabi_uidivmod
2         0.0065  __ieee754_fmod
2         0.0065  dtime()
2         0.0065  memalign
1         0.0033  GAUSS_INFO::GAUSS_INFO()
1         0.0033  GAUSS_INFO::~GAUSS_INFO()
1         0.0033  MFILE::MFILE()
1         0.0033  SPIKE_INFO::~SPIKE_INFO()
1         0.0033  TripletProgressUnits()
1         0.0033  __libc_disable_asynccancel
1         0.0033  __mul
1         0.0033  _int_memalign
1         0.0033  cdft(int, int, float (*) [2], int*, float*)
1         0.0033  gaussian::gaussian()
1         0.0033  getrusage
1         0.0033  nanosleep
1         0.0033  pulse::pulse()
1         0.0033  splitter_config::splitter_config()
1         0.0033  strchrnul
1         0.0033  usleep
1         0.0033  vfprintf
1         0.0033  worker_signal_handler(int)
 
 
Wed Sep 14 16:44:32 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 10000
PC_BRANCH_MIS_...|
  samples|      %|
------------------
  1361630 96.4491 seti_boinc
    34624  2.4525 no-vmlinux
     7771  0.5504 oprofiled
     5183  0.3671 libc-2.13.so
     1324  0.0938 bash
      356  0.0252 ld-2.13.so
      122  0.0086 libpangoft2-1.0.so.0.2800.4
      108  0.0077 libpixman-1.so.0.20.2
       73  0.0052 libglib-2.0.so.0.2800.6
       63  0.0045 libpthread-2.13.so
       63  0.0045 libcairo.so.2.11000.2
       48  0.0034 tr
       47  0.0033 libgobject-2.0.so.0.2800.6
       44  0.0031 thttpd
       39  0.0028 Xorg
       37  0.0026 ntpd
       33  0.0023 libavahi-common.so.3.5.3
       26  0.0018 ophelp
       20  0.0014 libgdk-x11-2.0.so.0.2400.4
       16  0.0011 libgtk-x11-2.0.so.0.2400.4
       15  0.0011 libfb.so
       14 9.9e-04 libpango-1.0.so.0.2800.4
       12 8.5e-04 libncurses.so.5.7
        8 5.7e-04 dash
        8 5.7e-04 libavahi-core.so.7.0.2
        7 5.0e-04 grep
        7 5.0e-04 libX11.so.6.3.0
        7 5.0e-04 libxcb.so.1.1.0
        7 5.0e-04 libORBit-2.so.0.1.0
        5 3.5e-04 mawk
        5 3.5e-04 rsyslogd
        4 2.8e-04 libdbus-1.so.3.5.4
        4 2.8e-04 sudo
        4 2.8e-04 sshd
        3 2.1e-04 libnss_compat-2.13.so
        3 2.1e-04 libpangocairo-1.0.so.0.2800.4
        3 2.1e-04 locale-archive
        2 1.4e-04 libm-2.13.so
        2 1.4e-04 seq
        2 1.4e-04 fbdev_drv.so
        2 1.4e-04 libshadow.so
        1 7.1e-05 ls
        1 7.1e-05 libgcc_s.so.1
        1 7.1e-05 libresolv-2.13.so
        1 7.1e-05 libcrypto.so.0.9.8
        1 7.1e-05 libXext.so.6.4.0
        1 7.1e-05 libXrender.so.1.3.0
        1 7.1e-05 libgio-2.0.so.0.2800.6
        1 7.1e-05 libgthread-2.0.so.0.2800.6
        1 7.1e-05 pango-basic-fc.so
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted PC_BRANCH_MIS_USED events (Branch or change in program flow that could have been predicted) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
354525   25.2737  sinl
286986   20.4590  cosl
100389    7.1566  FindSpikes(float*, int, int, SETI_WU_INFO&)
87452     6.2344  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
78095     5.5673  sincos
74606     5.3186  floor
53364     3.8043  f_GetTrueMean(float*, int, float, int, int)
40173     2.8639  v_GetPowerSpectrum(float (*) [2], float*, int)
36160     2.5778  f_GetPeak(float*, int, int, float, float, float*)
30793     2.1952  GaussFit(float*, int, int)
20802     1.4830  cftmdl(int, int, float*, float*)
17878     1.2745  analyze_pot(float*, int, ChirpFftPair_t&)
17708     1.2624  GetFixedPoT(float*, int, int, float*, int, int)
17654     1.2585  find_triplets(float const*, int, float, int, int)
17491     1.2469  __ieee754_log
15338     1.0934  lcgf(double, double)
14750     1.0515  sw_sum2_t31(float**, PoTPlan*)
12510     0.8918  free
11833     0.8436  _int_malloc
11413     0.8136  cftfsub(int, float*, float*)
9974      0.7110  memcpy
9671      0.6894  float_to_uchar(float*, unsigned char*, long, float)
8751      0.6239  bitrv2(int, int*, float*)
7421      0.5290  malloc
6632      0.4728  find_pulse(float const*, int, float, int, int)
6464      0.4608  _int_free
6248      0.4454  sw_sum3_t31(float**, PoTPlan*)
5541      0.3950  f_GetChiSq(float*, int, int, float, float, float*, float*)
5405      0.3853  sw_sum4_t31(float**, PoTPlan*)
5067      0.3612  cft1st(int, float*, float*)
4737      0.3377  sw_sum5_t31(float**, PoTPlan*)
3311      0.2360  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
2847      0.2030  logl
2697      0.1923  time_to_ra_dec(double, double*, double*)
1418      0.1011  csloww1
1415      0.1009  malloc_consolidate
1221      0.0870  top_sum3(float**, PoTPlan*)
1124      0.0801  checkpoint(unsigned char)
1048      0.0747  fraction_done(double, double)
884       0.0630  .divsi3_skip_div0_test
769       0.0548  memset
745       0.0531  workunit_grp::workunit_grp()
727       0.0518  operator new(unsigned int)
721       0.0514  boinc_time_to_checkpoint
680       0.0485  PulseProgressUnits(double, int)
618       0.0441  analysis_config::analysis_config()
604       0.0431  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
586       0.0418  receiver_config::receiver_config()
478       0.0341  TripletProgressUnits()
431       0.0307  isnanl
342       0.0244  __dubsin
303       0.0216  GAUSS_INFO::GAUSS_INFO()
294       0.0210  __dubcos
273       0.0195  operator delete(void*)
267       0.0190  __divsi3
259       0.0185  result::result()
243       0.0173  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
234       0.0167  top_sum4(float**, PoTPlan*)
212       0.0151  gaussian::gaussian()
201       0.0143  data_description_t::data_description_t()
184       0.0131  splitter_config::splitter_config()
179       0.0128  tape::tape()
177       0.0126  GaussianProgressUnits()
171       0.0122  GAUSS_INFO::~GAUSS_INFO()
145       0.0103  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
131       0.0093  MFILE::MFILE()
104       0.0074  __udivsi3
96        0.0068  csloww
93        0.0066  MFILE::~MFILE()
89        0.0063  recorder_config::recorder_config()
85        0.0061  calc_detection_freq(double, double, double)
61        0.0043  subband_description_t::subband_description_t()
58        0.0041  workunit_header::workunit_header()
57        0.0041  cnvt_bin_hz(int, int)
55        0.0039  __docos
43        0.0031  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
33        0.0024  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
28        0.0020  seti_analyze(ANALYSIS_STATE&)
26        0.0019  SPIKE_INFO::~SPIKE_INFO()
16        0.0011  __mul
14       1.0e-03  log10l
8        5.7e-04  _int_memalign
7        5.0e-04  SpikeProgressUnits(int)
6        4.3e-04  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
6        4.3e-04  __default_sa_restorer_v2
6        4.3e-04  cdft(int, int, float (*) [2], int*, float*)
6        4.3e-04  gettimeofday
6        4.3e-04  spike::spike()
5        3.6e-04  __ieee754_log10
5        3.6e-04  memalign
4        2.9e-04  boinc_fraction_done
4        2.9e-04  usleep
3        2.1e-04  PULSE_INFO::~PULSE_INFO()
3        2.1e-04  calloc_a(unsigned int, unsigned int, unsigned int)
3        2.1e-04  isinfl
3        2.1e-04  plan_PulsePoT(PoTPlan*, int, float*, int*)
2        1.4e-04  PULSE_INFO::PULSE_INFO()
2        1.4e-04  __ieee754_fmod
2        1.4e-04  __libc_disable_asynccancel
2        1.4e-04  __libc_enable_asynccancel
2        1.4e-04  boinc_sleep(double)
2        1.4e-04  getrusage
2        1.4e-04  nanosleep
2        1.4e-04  pulse::pulse()
2        1.4e-04  timer_thread(void*)
2        1.4e-04  worker_signal_handler(int)
1        7.1e-05  SPIKE_INFO::SPIKE_INFO()
1        7.1e-05  ____libc_enable_asynccancel_veneer
1        7.1e-05  __aeabi_uidivmod
1        7.1e-05  __mpn_divrem
1        7.1e-05  __mpn_mul_1
1        7.1e-05  add_magnitudes
1        7.1e-05  fmodl
1        7.1e-05  hack_digit.11570
1        7.1e-05  invert_lcgf(float, float, float)
1        7.1e-05  malloc_a(unsigned int, unsigned int)
1        7.1e-05  memchr
1        7.1e-05  std::basic_streambuf<char, std::char_traits<char> >::xsputn(char const*, int)
1        7.1e-05  std::basic_string<char, std::char_traits<char>, std::allocator<char> >::~basic_string()
1        7.1e-05  std::basic_stringbuf<char, std::char_traits<char>, std::allocator<char> >::overflow(int)
1        7.1e-05  strncpy
1        7.1e-05  sub_magnitudes
1        7.1e-05  timer_handler()
 
 
Wed Sep 14 16:59:57 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_HIT events (Number of coherent linefill requests which hit in another CPU, meaning that the linefill data is fetched directly from the relevant cache) with a unit mask of 0x00 (No unit mask) count 10000
  CO_LF_HIT:10000|
  samples|      %|
------------------
      932 89.1013 no-vmlinux
      110 10.5163 seti_boinc
        3  0.2868 libc-2.13.so
        1  0.0956 locale-archive
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted CO_LF_HIT events (Number of coherent linefill requests which hit in another CPU, meaning that the linefill data is fetched directly from the relevant cache) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
17       15.4545  cftmdl(int, int, float*, float*)
16       14.5455  memcpy
9         8.1818  bitrv2(int, int*, float*)
9         8.1818  v_GetPowerSpectrum(float (*) [2], float*, int)
7         6.3636  floor
5         4.5455  find_triplets(float const*, int, float, int, int)
4         3.6364  cft1st(int, float*, float*)
4         3.6364  cftfsub(int, float*, float*)
4         3.6364  checkpoint(unsigned char)
4         3.6364  log10l
4         3.6364  seti_analyze(ANALYSIS_STATE&)
3         2.7273  FindSpikes(float*, int, int, SETI_WU_INFO&)
3         2.7273  GaussFit(float*, int, int)
2         1.8182  __default_sa_restorer_v2
2         1.8182  __dubcos
2         1.8182  __dubsin
2         1.8182  analyze_pot(float*, int, ChirpFftPair_t&)
2         1.8182  cosl
2         1.8182  sinl
1         0.9091  __udivsi3
1         0.9091  f_GetTrueMean(float*, int, float, int, int)
1         0.9091  isnanl
1         0.9091  logl
1         0.9091  malloc
1         0.9091  sw_sum2_t31(float**, PoTPlan*)
1         0.9091  worker_signal_handler(int)
1         0.9091  workunit_grp::workunit_grp()
1         0.9091  workunit_header::workunit_header()
 
 
Wed Sep 14 17:10:22 PDT 2011
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DC_DEP_STALL events (Number of cycles where CPU has some instructions that it cannot issue to any pipeline and the LSU has at least one pending linefill request but no pending TLB requests) with a unit mask of 0x00 (No unit mask) count 10000
DC_DEP_STALL:1...|
  samples|      %|
------------------
  6505243 98.4844 seti_boinc
    65561  0.9925 no-vmlinux
    24738  0.3745 oprofiled
     3848  0.0583 libc-2.13.so
     1952  0.0296 ld-2.13.so
     1196  0.0181 bash
      886  0.0134 thttpd
      331  0.0050 libglib-2.0.so.0.2800.6
      260  0.0039 Xorg
      226  0.0034 ntpd
      105  0.0016 libpthread-2.13.so
       98  0.0015 libgobject-2.0.so.0.2800.6
       97  0.0015 locale-archive
       68  0.0010 libgdk-x11-2.0.so.0.2400.4
       67  0.0010 libdbus-1.so.3.5.4
       57 8.6e-04 libpixman-1.so.0.20.2
       54 8.2e-04 libgtk-x11-2.0.so.0.2400.4
       49 7.4e-04 libavahi-core.so.7.0.2
       48 7.3e-04 libX11.so.6.3.0
       47 7.1e-04 libpangoft2-1.0.so.0.2800.4
       42 6.4e-04 libavahi-common.so.3.5.3
       35 5.3e-04 mawk
       33 5.0e-04 libcairo.so.2.11000.2
       32 4.8e-04 libpango-1.0.so.0.2800.4
       29 4.4e-04 libcrypto.so.0.9.8
       22 3.3e-04 sshd
       17 2.6e-04 tr
       16 2.4e-04 libxcb.so.1.1.0
       16 2.4e-04 rsyslogd
       14 2.1e-04 libORBit-2.so.0.1.0
       13 2.0e-04 libm-2.13.so
       12 1.8e-04 init
       12 1.8e-04 sudo
       12 1.8e-04 libgio-2.0.so.0.2800.6
       12 1.8e-04 libfb.so
       10 1.5e-04 libshadow.so
        9 1.4e-04 libgthread-2.0.so.0.2800.6
        9 1.4e-04 gconfd-2
        8 1.2e-04 libgconf-2.so.4.1.5
        7 1.1e-04 libdl-2.13.so
        7 1.1e-04 libXext.so.6.4.0
        6 9.1e-05 ophelp
        6 9.1e-05 gdm-simple-greeter
        5 7.6e-05 grep
        4 6.1e-05 dash
        4 6.1e-05 libncurses.so.5.7
        4 6.1e-05 metacity
        4 6.1e-05 libpangocairo-1.0.so.0.2800.4
        3 4.5e-05 libnss_compat-2.13.so
        2 3.0e-05 libpam.so.0.82.3
        2 3.0e-05 librt-2.13.so
        2 3.0e-05 libpopt.so.0.0.0
        2 3.0e-05 libXrender.so.1.3.0
        2 3.0e-05 rtkit-daemon
        2 3.0e-05 libextmod.so
        1 1.5e-05 cat
        1 1.5e-05 libnsl-2.13.so
        1 1.5e-05 libnss_dns-2.13.so
        1 1.5e-05 libutil-2.13.so
        1 1.5e-05 libz.so.1.2.3.4
        1 1.5e-05 libXcursor.so.1.0.2
        1 1.5e-05 fbdev_drv.so
        1 1.5e-05 libdbe.so
        1 1.5e-05 cron
 
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DC_DEP_STALL events (Number of cycles where CPU has some instructions that it cannot issue to any pipeline and the LSU has at least one pending linefill request but no pending TLB requests) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
1796685  26.8201  cftmdl(int, int, float*, float*)
1332029  19.8839  bitrv2(int, int*, float*)
771401   11.5151  cft1st(int, float*, float*)
632966    9.4486  v_GetPowerSpectrum(float (*) [2], float*, int)
460979    6.8813  cftfsub(int, float*, float*)
448429    6.6939  GetFixedPoT(float*, int, int, float*, int, int)
401625    5.9953  v_ChirpData(float (*) [2], float (*) [2], int, double, int, double)
374727    5.5938  FindSpikes(float*, int, int, SETI_WU_INFO&)
308336    4.6027  analyze_pot(float*, int, ChirpFftPair_t&)
72344     1.0799  floor
27136     0.4051  memcpy
22159     0.3308  sinl
19403     0.2896  find_triplets(float const*, int, float, int, int)
5525      0.0825  cosl
5111      0.0763  GaussFit(float*, int, int)
3822      0.0571  __ieee754_log
1583      0.0236  __dubsin
1424      0.0213  time_to_ra_dec(double, double*, double*)
1408      0.0210  __dubcos
1322      0.0197  _int_malloc
1026      0.0153  sincos
826       0.0123  _int_free
785       0.0117  malloc
554       0.0083  sw_sum2_t31(float**, PoTPlan*)
518       0.0077  f_GetChiSq(float*, int, int, float, float, float*, float*)
457       0.0068  csloww1
431       0.0064  free
419       0.0063  malloc_consolidate
362       0.0054  workunit_grp::workunit_grp()
316       0.0047  .divsi3_skip_div0_test
312       0.0047  seti_analyze(ANALYSIS_STATE&)
269       0.0040  calc_detection_freq(double, double, double)
252       0.0038  SPIKE_INFO::SPIKE_INFO()
237       0.0035  f_GetPeak(float*, int, int, float, float, float*)
232       0.0035  csloww
214       0.0032  find_pulse(float const*, int, float, int, int)
213       0.0032  SPIKE_INFO::~SPIKE_INFO()
163       0.0024  spike::spike()
155       0.0023  sw_sum5_t31(float**, PoTPlan*)
150       0.0022  fraction_done(double, double)
132       0.0020  analysis_config::analysis_config()
132       0.0020  sw_sum4_t31(float**, PoTPlan*)
129       0.0019  sw_sum3_t31(float**, PoTPlan*)
121       0.0018  timer_handler()
120       0.0018  f_GetTrueMean(float*, int, float, int, int)
114       0.0017  cnvt_bin_hz(int, int)
110       0.0016  checkpoint(unsigned char)
109       0.0016  __udivsi3
104       0.0016  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
103       0.0015  splitter_config::splitter_config()
92        0.0014  tape::tape()
84        0.0013  workunit_header::workunit_header()
80        0.0012  __ieee754_log10
79        0.0012  top_sum3(float**, PoTPlan*)
76        0.0011  data_description_t::data_description_t()
74        0.0011  isnanl
72        0.0011  gaussian::gaussian()
72        0.0011  lcgf(double, double)
66       9.9e-04  logl
64       9.6e-04  PulseProgressUnits(double, int)
61       9.1e-04  operator delete(void*)
60       9.0e-04  cdft(int, int, float (*) [2], int*, float*)
59       8.8e-04  __divsi3
59       8.8e-04  float_to_uchar(float*, unsigned char*, long, float)
47       7.0e-04  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
47       7.0e-04  __default_sa_restorer_v2
46       6.9e-04  result::result()
44       6.6e-04  boinc_time_to_checkpoint
42       6.3e-04  GAUSS_INFO::~GAUSS_INFO()
38       5.7e-04  MFILE::MFILE()
37       5.5e-04  log10l
33       4.9e-04  nanosleep
27       4.0e-04  boinc_fraction_done
27       4.0e-04  operator new(unsigned int)
24       3.6e-04  ____libc_enable_asynccancel_veneer
23       3.4e-04  top_sum4(float**, PoTPlan*)
21       3.1e-04  GetPulsePoTLen(long, int*, int*)
19       2.8e-04  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
12       1.8e-04  MFILE::~MFILE()
9        1.3e-04  ChirpProgressUnits()
8        1.2e-04  GAUSS_INFO::GAUSS_INFO()
7        1.0e-04  TripletProgressUnits()
4        6.0e-05  receiver_config::receiver_config()
3        4.5e-05  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
3        4.5e-05  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
3        4.5e-05  boinc_ops_cumulative
3        4.5e-05  plan_PulsePoT(PoTPlan*, int, float*, int*)
3        4.5e-05  subband_description_t::subband_description_t()
3        4.5e-05  t_funct(int, int, int)
2        3.0e-05  GaussianProgressUnits()
2        3.0e-05  PULSE_INFO::PULSE_INFO()
2        3.0e-05  __docos
2        3.0e-05  pulse::pulse()
2        3.0e-05  timer_thread(void*)
1        1.5e-05  Laligned
1        1.5e-05  PULSE_INFO::~PULSE_INFO()
1        1.5e-05  _IO_new_file_xsputn
1        1.5e-05  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
1        1.5e-05  ___printf_fp
1        1.5e-05  recorder_config::recorder_config()
1        1.5e-05  std::basic_ios<char, std::char_traits<char> >::init(std::basic_streambuf<char, std::char_traits<char> >*)
1        1.5e-05  std::basic_ostream<char, std::char_traits<char> >& std::operator<< <std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*)
1        1.5e-05  uselocale
 
 
Wed Sep 14 17:21:32 PDT 2011
Wed Sep 14 17:21:43 PDT 2011
 
 
Wed Sep 14 17:40:46 PDT 2011
 
 
 
Wed Sep 14 17:52:41 PDT 2011
 
 
 
Wed Sep 14 18:03:15 PDT 2011
 
 
```