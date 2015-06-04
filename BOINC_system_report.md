# Introduction #

## BOINC report on versatile ##
```
user41@ca9-natty:~/boinc/client$ ./boinc &
[1] 3848
user41@ca9-natty:~/boinc/client$ 13-Sep-2011 23:10:02 [---] Starting BOINC client version 6.13.0 for armv7l-unknown-linux-gnueabi
13-Sep-2011 23:10:02 [---] This a development version of BOINC and may not function properly
13-Sep-2011 23:10:02 [---] log flags: file_xfer, sched_ops, task
13-Sep-2011 23:10:02 [---] Libraries: libcurl/7.21.3 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.18
13-Sep-2011 23:10:02 [---] Data directory: /home/user41/boinc/client
getaddrinfo: Success
13-Sep-2011 23:10:02 [---] Processor: 4  
13-Sep-2011 23:10:02 [---] Processor features: 
13-Sep-2011 23:10:02 [---] OS: Linux: 3.1.0-rc1-07755-g461bf77-dirty
13-Sep-2011 23:10:02 [---] Memory: 1010.67 MB physical, 0 bytes virtual
13-Sep-2011 23:10:02 [---] Disk: 90.48 GB total, 30.42 GB free
13-Sep-2011 23:10:02 [---] Local time is UTC -7 hours
13-Sep-2011 23:10:02 [---] No usable GPUs found
13-Sep-2011 23:10:02 [---] No general preferences found - using BOINC defaults
13-Sep-2011 23:10:02 [---] Preferences:
13-Sep-2011 23:10:02 [---]    max memory usage when active: 505.34MB
13-Sep-2011 23:10:02 [---]    max memory usage when idle: 909.60MB
13-Sep-2011 23:10:02 [---]    max disk usage: 10.00GB
13-Sep-2011 23:10:02 [---]    don't use GPU while active
13-Sep-2011 23:10:02 [---]    suspend work if non-BOINC CPU load exceeds 25 %
13-Sep-2011 23:10:02 [---]    (to change preferences, visit the web site of an attached project, or select Preferences in the Manager)
13-Sep-2011 23:10:02 [---] Not using a proxy
13-Sep-2011 23:10:02 [---] This computer is not attached to any projects
13-Sep-2011 23:10:02 [---] Visit http://boinc.berkeley.edu for instructions
Initialization completed

user41@ca9-natty:~/boinc/client$ ./boinccmd --run_benchmarks
13-Sep-2011 23:12:40 [---] Running CPU benchmarks
user41@ca9-natty:~/boinc/client$ 13-Sep-2011 23:12:41 [---] Suspending computation - CPU benchmarks in progress
13-Sep-2011 23:13:12 [---] Benchmark results:
13-Sep-2011 23:13:12 [---]    Number of CPUs: 4
13-Sep-2011 23:13:12 [---]    335 floating point MIPS (Whetstone) per CPU
13-Sep-2011 23:13:12 [---]    1071 integer MIPS (Dhrystone) per CPU
13-Sep-2011 23:13:13 [---] Resuming computation

```


## On Atom 4 ##

```
xbmc@atom:~/Documents/boinc/boinc/client$ ./boinc &
[1] 16647
xbmc@atom:~/Documents/boinc/boinc/client$ 15-Sep-2011 22:35:56 [---] Starting BOINC client version 6.13.0 for i686-pc-linux-gnu
15-Sep-2011 22:35:56 [---] This a development version of BOINC and may not function properly
15-Sep-2011 22:35:56 [---] log flags: file_xfer, sched_ops, task
15-Sep-2011 22:35:56 [---] Libraries: libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.18
15-Sep-2011 22:35:56 [---] Data directory: /home/xbmc/Documents/boinc/boinc/client
15-Sep-2011 22:35:56 [---] Processor: 4 GenuineIntel Intel(R) Atom(TM) CPU D525   @ 1.80GHz [Family 6 Model 28 Stepping 10]
15-Sep-2011 22:35:56 [---] Processor: 512.00 KB cache
15-Sep-2011 22:35:56 [---] Processor features: fpu vme de pse tsc msr pae mce cx8 apic mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe nx lm constant_tsc arch_perfmon pebs bts aperfmperf pni dtes64 monitor ds_cpl tm2 ssse3 cx16 xtpr pdcm movbe lahf_lm
15-Sep-2011 22:35:56 [---] OS: Linux: 2.6.35-22-generic
15-Sep-2011 22:35:56 [---] Memory: 1.96 GB physical, 5.86 GB virtual
15-Sep-2011 22:35:56 [---] Disk: 911.13 GB total, 734.78 GB free
15-Sep-2011 22:35:56 [---] Local time is UTC -5 hours
15-Sep-2011 22:35:56 [---] NVIDIA GPU 0: ION (driver version unknown, CUDA version 3020, compute capability 1.2, 511MB, 39 GFLOPS peak)
15-Sep-2011 22:35:56 [---] No general preferences found - using BOINC defaults
15-Sep-2011 22:35:56 [---] Preferences:
15-Sep-2011 22:35:56 [---]    max memory usage when active: 1005.55MB
15-Sep-2011 22:35:56 [---]    max memory usage when idle: 1809.98MB
15-Sep-2011 22:35:56 [---]    max disk usage: 10.00GB
15-Sep-2011 22:35:56 [---]    don't use GPU while active
15-Sep-2011 22:35:56 [---]    suspend work if non-BOINC CPU load exceeds 25 %
15-Sep-2011 22:35:56 [---]    (to change preferences, visit the web site of an attached project, or select Preferences in the Manager)
15-Sep-2011 22:35:56 [---] Not using a proxy
15-Sep-2011 22:35:56 [---] This computer is not attached to any projects
15-Sep-2011 22:35:56 [---] Visit http://boinc.berkeley.edu for instructions
Initialization completed

xbmc@atom:~/Documents/boinc/boinc/client$ ./boinccmd --run_benchmarks
15-Sep-2011 22:36:01 [---] Running CPU benchmarks
xbmc@atom:~/Documents/boinc/boinc/client$ 15-Sep-2011 22:36:01 [---] Suspending computation - CPU benchmarks in progress
15-Sep-2011 22:36:32 [---] Benchmark results:
15-Sep-2011 22:36:32 [---]    Number of CPUs: 4
15-Sep-2011 22:36:32 [---]    678 floating point MIPS (Whetstone) per CPU
15-Sep-2011 22:36:32 [---]    1826 integer MIPS (Dhrystone) per CPU
15-Sep-2011 22:36:33 [---] Resuming computation


```

## On 4xCA9 ##
```
lucid@lucid-desktop:~/Documents/boinc/client$ ./boinc &
[1] 28560
lucid@lucid-desktop:~/Documents/boinc/client$ 15-Sep-2011 02:20:40 [---] Starting BOINC client version 6.13.1 for armv7l-unknown-linux-gnueabi
15-Sep-2011 02:20:40 [---] This a development version of BOINC and may not function properly
15-Sep-2011 02:20:40 [---] log flags: file_xfer, sched_ops, task
15-Sep-2011 02:20:40 [---] Libraries: libcurl/7.19.7 OpenSSL/0.9.8k zlib/1.2.3.3 libidn/1.15
15-Sep-2011 02:20:40 [---] Data directory: /home/lucid/Documents/boinc/client
15-Sep-2011 02:20:40 [---] Processor: 4  
15-Sep-2011 02:20:40 [---] Processor features: 
15-Sep-2011 02:20:40 [---] OS: Linux: 2.6.38-00545-g06c5d6a-dirty
15-Sep-2011 02:20:40 [---] Memory: 1.85 GB physical, 0 bytes virtual
15-Sep-2011 02:20:40 [---] Disk: 3.63 GB total, 1.16 GB free
15-Sep-2011 02:20:40 [---] Local time is UTC +8 hours
15-Sep-2011 02:20:40 [---] No usable GPUs found
15-Sep-2011 02:20:40 [---] No general preferences found - using BOINC defaults
15-Sep-2011 02:20:40 [---] Preferences:
15-Sep-2011 02:20:40 [---]    max memory usage when active: 948.41MB
15-Sep-2011 02:20:40 [---]    max memory usage when idle: 1707.15MB
15-Sep-2011 02:20:40 [---]    max disk usage: 1.07GB
15-Sep-2011 02:20:40 [---]    don't use GPU while active
15-Sep-2011 02:20:40 [---]    suspend work if non-BOINC CPU load exceeds 25 %
15-Sep-2011 02:20:40 [---]    (to change preferences, visit the web site of an attached project, or select Preferences in the Manager)
15-Sep-2011 02:20:40 [---] Not using a proxy
15-Sep-2011 02:20:40 [---] This computer is not attached to any projects
15-Sep-2011 02:20:40 [---] Visit http://boinc.berkeley.edu for instructions
Initialization completed

lucid@lucid-desktop:~/Documents/boinc/client$ ./boinccmd --run_benchmarks
15-Sep-2011 02:21:05 [---] Running CPU benchmarks
lucid@lucid-desktop:~/Documents/boinc/client$ 15-Sep-2011 02:21:06 [---] Suspending computation - CPU benchmarks in progress
15-Sep-2011 02:21:37 [---] Benchmark results:
15-Sep-2011 02:21:37 [---]    Number of CPUs: 4
15-Sep-2011 02:21:37 [---]    608 floating point MIPS (Whetstone) per CPU
15-Sep-2011 02:21:37 [---]    1914 integer MIPS (Dhrystone) per CPU
15-Sep-2011 02:21:38 [---] Resuming computation

```

## On Core i3 notebook ##
```
jeff@east:~/stuff/boinc/client$ ./boinc &
[1] 2778
jeff@east:~/stuff/boinc/client$ 14-Sep-2011 15:31:21 [---] Starting BOINC client version 6.13.0 for i686-pc-linux-gnu
14-Sep-2011 15:31:21 [---] This a development version of BOINC and may not function properly
14-Sep-2011 15:31:21 [---] log flags: file_xfer, sched_ops, task
14-Sep-2011 15:31:21 [---] Libraries: libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.18
14-Sep-2011 15:31:21 [---] Data directory: /home/jeff/stuff/boinc/client
14-Sep-2011 15:31:21 [---] Processor: 4 GenuineIntel Intel(R) Core(TM) i3 CPU       M 330  @ 2.13GHz [Family 6 Model 37 Stepping 2]
14-Sep-2011 15:31:21 [---] Processor: 3.00 MB cache
14-Sep-2011 15:31:21 [---] Processor features: fpu vme de pse tsc msr pae mce cx8 apic mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe nx rdtscp lm constant_tsc arch_perfmon pebs bts xtopology nonstop_tsc aperfmperf pni dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16
14-Sep-2011 15:31:21 [---] OS: Linux: 2.6.35-22-generic
14-Sep-2011 15:31:21 [---] Memory: 2.63 GB physical, 4.01 GB virtual
14-Sep-2011 15:31:21 [---] Disk: 92.17 GB total, 9.12 GB free
14-Sep-2011 15:31:21 [---] Local time is UTC -5 hours
14-Sep-2011 15:31:21 [---] No usable GPUs found
14-Sep-2011 15:31:21 [---] No general preferences found - using BOINC defaults
14-Sep-2011 15:31:21 [---] Preferences:
14-Sep-2011 15:31:21 [---]    max memory usage when active: 1347.47MB
14-Sep-2011 15:31:21 [---]    max memory usage when idle: 2425.45MB
14-Sep-2011 15:31:21 [---]    max disk usage: 9.05GB
14-Sep-2011 15:31:21 [---]    don't use GPU while active
14-Sep-2011 15:31:21 [---]    suspend work if non-BOINC CPU load exceeds 25 %
14-Sep-2011 15:31:21 [---]    (to change preferences, visit the web site of an attached project, or select Preferences in the Manager)

jeff@east:~/stuff/boinc/client$ ./14-Sep-2011 15:31:21 [---] Not using a proxy
14-Sep-2011 15:31:21 [---] This computer is not attached to any projects
14-Sep-2011 15:31:21 [---] Visit http://boinc.berkeley.edu for instructions
Initialization completed

bash: ./: is a directory
jeff@east:~/stuff/boinc/client$ ./boinccmd --run_benchmarks
14-Sep-2011 15:31:37 [---] Running CPU benchmarks
jeff@east:~/stuff/boinc/client$ 14-Sep-2011 15:31:38 [---] Suspending computation - CPU benchmarks in progress
14-Sep-2011 15:32:09 [---] Benchmark results:
14-Sep-2011 15:32:09 [---]    Number of CPUs: 4
14-Sep-2011 15:32:09 [---]    1512 floating point MIPS (Whetstone) per CPU
14-Sep-2011 15:32:09 [---]    3543 integer MIPS (Dhrystone) per CPU
14-Sep-2011 15:32:10 [---] Resuming computation


```

## i.MX53 QSB ##

```
lucid@lucid-desktop:~/Documents/boinc/client$ ./boinc &
[1] 6345
lucid@lucid-desktop:~/Documents/boinc/client$ 15-Sep-2011 04:59:41 [---] Starting BOINC client version 6.13.1 for armv7l-unknown-linux-gnueabi
15-Sep-2011 04:59:41 [---] This a development version of BOINC and may not function properly
15-Sep-2011 04:59:41 [---] log flags: file_xfer, sched_ops, task
15-Sep-2011 04:59:41 [---] Libraries: libcurl/7.19.7 OpenSSL/0.9.8k zlib/1.2.3.3 libidn/1.15
15-Sep-2011 04:59:41 [---] Data directory: /home/lucid/Documents/boinc/client
15-Sep-2011 04:59:41 [---] Processor: 1  
15-Sep-2011 04:59:41 [---] Processor features: 
15-Sep-2011 04:59:41 [---] OS: Linux: 2.6.38-00462-gc38d9c7-dirty
15-Sep-2011 04:59:41 [---] Memory: 851.00 MB physical, 0 bytes virtual
15-Sep-2011 04:59:41 [---] Disk: 114.24 GB total, 106.05 GB free
15-Sep-2011 04:59:41 [---] Local time is UTC +8 hours
15-Sep-2011 04:59:41 [---] No usable GPUs found
15-Sep-2011 04:59:41 [---] No general preferences found - using BOINC defaults
15-Sep-2011 04:59:41 [---] Preferences:
15-Sep-2011 04:59:41 [---]    max memory usage when active: 425.50MB
15-Sep-2011 04:59:41 [---]    max memory usage when idle: 765.90MB
15-Sep-2011 04:59:41 [---]    max disk usage: 10.00GB
15-Sep-2011 04:59:41 [---]    don't use GPU while active
15-Sep-2011 04:59:41 [---]    suspend work if non-BOINC CPU load exceeds 25 %
15-Sep-2011 04:59:41 [---]    (to change preferences, visit the web site of an attached project, or select Preferences in the Manager)
15-Sep-2011 04:59:41 [---] Not using a proxy
15-Sep-2011 04:59:41 [---] This computer is not attached to any projects
15-Sep-2011 04:59:41 [---] Visit http://boinc.berkeley.edu for instructions
Initialization completed

lucid@lucid-desktop:~/Documents/boinc/client$ ./boinccmd --run_benchmarks
15-Sep-2011 04:59:57 [---] Running CPU benchmarks
lucid@lucid-desktop:~/Documents/boinc/client$ 15-Sep-2011 04:59:58 [---] Suspending computation - CPU benchmarks in progress
15-Sep-2011 05:00:29 [---] Benchmark results:
15-Sep-2011 05:00:29 [---]    Number of CPUs: 1
15-Sep-2011 05:00:29 [---]    157 floating point MIPS (Whetstone) per CPU
15-Sep-2011 05:00:29 [---]    1710 integer MIPS (Dhrystone) per CPU
15-Sep-2011 05:00:30 [---] Resuming computation


```
## OMAP4430 ##
```
jeff@CortexA9x2:~/Documents/boinc/boinc/client$ 02-Jul-2011 15:07:29 [---] Starting BOINC client version 6.13.0 for armv7l-unknown-linux-gnueabi
02-Jul-2011 15:07:29 [---] This a development version of BOINC and may not function properly
02-Jul-2011 15:07:29 [---] log flags: file_xfer, sched_ops, task
02-Jul-2011 15:07:29 [---] Libraries: libcurl/7.21.0 OpenSSL/0.9.8o zlib/1.2.3.4 libidn/1.18
02-Jul-2011 15:07:29 [---] Data directory: /home/jeff/Documents/boinc/boinc/client
02-Jul-2011 15:07:29 [---] Processor: 2  
02-Jul-2011 15:07:29 [---] Processor features: 
02-Jul-2011 15:07:29 [---] OS: Linux: 2.6.35-903-omap4
02-Jul-2011 15:07:29 [---] Memory: 665.86 MB physical, 512.00 MB virtual
02-Jul-2011 15:07:29 [---] Disk: 7.10 GB total, 2.90 GB free
02-Jul-2011 15:07:29 [---] Local time is UTC -5 hours
02-Jul-2011 15:07:29 [---] No usable GPUs found
02-Jul-2011 15:07:29 [---] No general preferences found - using BOINC defaults
02-Jul-2011 15:07:29 [---] Preferences:
02-Jul-2011 15:07:29 [---]    max memory usage when active: 332.93MB
02-Jul-2011 15:07:29 [---]    max memory usage when idle: 599.28MB
02-Jul-2011 15:07:29 [---]    max disk usage: 2.80GB
02-Jul-2011 15:07:29 [---]    don't use GPU while active
02-Jul-2011 15:07:29 [---]    suspend work if non-BOINC CPU load exceeds 25 %
02-Jul-2011 15:07:29 [---]    (to change preferences, visit the web site of an attached project, or select Preferences in the Manager)
02-Jul-2011 15:07:29 [---] Not using a proxy
02-Jul-2011 15:07:29 [---] This computer is not attached to any projects
02-Jul-2011 15:07:29 [---] Visit http://boinc.berkeley.edu for instructions
Initialization completed

jeff@CortexA9x2:~/Documents/boinc/boinc/client$ ./boinccmd --run_benchmarks
02-Jul-2011 15:07:42 [---] Running CPU benchmarks
jeff@CortexA9x2:~/Documents/boinc/boinc/client$ 02-Jul-2011 15:07:42 [---] Suspending computation - CPU benchmarks in progress
02-Jul-2011 15:08:13 [---] Benchmark results:
02-Jul-2011 15:08:13 [---]    Number of CPUs: 2
02-Jul-2011 15:08:13 [---]    642 floating point MIPS (Whetstone) per CPU
02-Jul-2011 15:08:13 [---]    2016 integer MIPS (Dhrystone) per CPU
02-Jul-2011 15:08:14 [---] Resuming computation

jeff@CortexA9x2:~/Documents/boinc/boinc/client$ ./boinccmd --run_benchmarks
02-Jul-2011 15:08:33 [---] Running CPU benchmarks
jeff@CortexA9x2:~/Documents/boinc/boinc/client$ 02-Jul-2011 15:08:34 [---] Suspending computation - CPU benchmarks in progress
02-Jul-2011 15:09:05 [---] Benchmark results:
02-Jul-2011 15:09:05 [---]    Number of CPUs: 2
02-Jul-2011 15:09:05 [---]    642 floating point MIPS (Whetstone) per CPU
02-Jul-2011 15:09:05 [---]    2009 integer MIPS (Dhrystone) per CPU
02-Jul-2011 15:09:06 [---] Resuming computation

```