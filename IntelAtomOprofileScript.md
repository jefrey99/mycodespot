# This script was used to profile SETI at home on x86 (Atom) #

```
#!/bin/bash
SleepSeconds=118

./seti_boinc --standalone &

# Running Timer Mode
sudo rm -r /var/lib/oprofile/
sudo rm -r /root/.oprofile/daemonrc
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --start
sudo opcontrol --status
echo "profiling for $SleepSeconds seconds"
sleep $SleepSeconds
sudo opcontrol --dump
date >> Atom_Oprofile.txt
sudo opreport >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
sudo opreport -l /home/xbmc/Documents/boinc/seti_boinc/client/seti_boinc >> Atom_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt

# Running next event
sudo rm -r /var/lib/oprofile/
sudo rm -r /root/.oprofile/daemonrc
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=INST_RETIRED:10000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> Atom_Oprofile.txt
sudo opreport >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
sudo opreport -l /home/xbmc/Documents/boinc/seti_boinc/client/seti_boinc >> Atom_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt

# Running next event 
sudo rm -r /var/lib/oprofile/
sudo rm -r /root/.oprofile/daemonrc
date
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=LLC_MISSES:10000:0x41:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> Atom_Oprofile.txt
sudo opreport >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
sudo opreport -l /home/xbmc/Documents/boinc/seti_boinc/client/seti_boinc >> Atom_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt

# Running next event 
sudo rm -r /var/lib/oprofile/
sudo rm -r /root/.oprofile/daemonrc
date
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=LLC_REFS:10000:0x4f:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> Atom_Oprofile.txt
sudo opreport >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
sudo opreport -l /home/xbmc/Documents/boinc/seti_boinc/client/seti_boinc >> Atom_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt

# Running next event 
sudo rm -r /var/lib/oprofile/
sudo rm -r /root/.oprofile/daemonrc
date
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=BR_INST_RETIRED:10000:0x00:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> Atom_Oprofile.txt
sudo opreport >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
sudo opreport -l /home/xbmc/Documents/boinc/seti_boinc/client/seti_boinc >> Atom_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt

# Running next event 
sudo rm -r /var/lib/oprofile/
sudo rm -r /root/.oprofile/daemonrc
date
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --event=BR_MISS_PRED_RETIRED:10000:0x00:0:1
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
date >> Atom_Oprofile.txt
sudo opreport >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
sudo opreport -l /home/xbmc/Documents/boinc/seti_boinc/client/seti_boinc >> Atom_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> Atom_Oprofile.txt
echo " " >> Atom_Oprofile.txt
```

### Atom Profiling ###
```
Sun Aug 14 19:04:22 CDT 2011
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted CPU_CLK_UNHALTED events (Clock cycles when not halted) with a unit mask of 0x00 (core_p Core cycles when core is not halted) count 100000
CPU_CLK_UNHALT...|
  samples|      %|
------------------
  2069891 50.2315 no-vmlinux
  2027265 49.1971 seti_boinc
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	  2027254 99.9995 seti_boinc
	       11 5.4e-04 [vdso] (tgid:2317 range:0x3dd000-0x3de000)
    17798  0.4319 oprofiled
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	    17788 99.9438 oprofiled
	       10  0.0562 [vdso] (tgid:2496 range:0x57f000-0x580000)
     2535  0.0615 libc-2.12.1.so
      812  0.0197 bash
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	      810 99.7537 bash
	        2  0.2463 [vdso] (tgid:2532 range:0xf06000-0xf07000)
      503  0.0122 libcairo.so.2.11000.0
      399  0.0097 ld-2.12.1.so
      223  0.0054 dbus-daemon
      183  0.0044 libglib-2.0.so.0.2600.1
      171  0.0041 libdbus-1.so.3.5.2
      159  0.0039 boinc
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	      107 67.2956 boinc
	       52 32.7044 [vdso] (tgid:935 range:0x3a4000-0x3a5000)
      134  0.0033 libpthread-2.12.1.so
      104  0.0025 Xorg
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	       94 90.3846 Xorg
	       10  9.6154 [vdso] (tgid:1221 range:0x7bc000-0x7bd000)
      101  0.0025 libgobject-2.0.so.0.2600.1
       61  0.0015 nvidia_drv.so
       29 7.0e-04 libORBit-2.so.0.1.0
       28 6.8e-04 libdbus-glib-1.so.2.1.0
       27 6.6e-04 libgdk-x11-2.0.so.0.2200.0
       24 5.8e-04 compiz
       22 5.3e-04 libxcb.so.1.1.0
       18 4.4e-04 libnvidia-glcore.so.260.19.06
       17 4.1e-04 libX11.so.6.3.0
       13 3.2e-04 grep
       12 2.9e-04 NetworkManager
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	       11 91.6667 NetworkManager
	        1  8.3333 [vdso] (tgid:808 range:0x576000-0x577000)
       11 2.7e-04 libgthread-2.0.so.0.2600.1
       11 2.7e-04 irqbalance
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        6 54.5455 irqbalance
	        5 45.4545 [vdso] (tgid:925 range:0x5ad000-0x5ae000)
        9 2.2e-04 libgconf-2.so.4.1.5
        8 1.9e-04 libpam.so.0.82.2
        8 1.9e-04 librt-2.12.1.so
        8 1.9e-04 libcurl.so.4.2.0
        7 1.7e-04 dash
        7 1.7e-04 libm-2.12.1.so
        7 1.7e-04 libpangoft2-1.0.so.0.2800.2
        6 1.5e-04 libgio-2.0.so.0.2600.1
        5 1.2e-04 sudo
        5 1.2e-04 libgtk-x11-2.0.so.0.2200.0
        5 1.2e-04 libgvfscommon.so.0.0.0
        5 1.2e-04 libpango-1.0.so.0.2800.2
        4 9.7e-05 libnm-glib.so.2.4.1
        4 9.7e-05 libusbmuxd.so.1.0.4
        3 7.3e-05 mawk
        3 7.3e-05 nm-applet
        3 7.3e-05 libezoom.so
        3 7.3e-05 gnome-settings-daemon
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        3 100.000 [vdso] (tgid:1479 range:0x30f000-0x310000)
        3 7.3e-05 libcompizconfig.so.0.0.0
        3 7.3e-05 libgnome-keyring.so.0.1.1
        3 7.3e-05 libnm-util.so.1.6.0
        3 7.3e-05 rsyslogd
        2 4.9e-05 libneg.so
        2 4.9e-05 libscale.so
        2 4.9e-05 libsnap.so
        2 4.9e-05 libmurrine.so
        2 4.9e-05 libavahi-common.so.3.5.2
        2 4.9e-05 libavahi-core.so.7.0.0
        2 4.9e-05 libstartup-notification-1.so.0.0.0
        1 2.4e-05 cat
        1 2.4e-05 ls
        1 2.4e-05 sleep
        1 2.4e-05 libcrypto.so.0.9.8
        1 2.4e-05 libnss_files-2.12.1.so
        1 2.4e-05 libselinux.so.1
        1 2.4e-05 libudev.so.0.9.1
        1 2.4e-05 expr
        1 2.4e-05 gtk-window-decorator
        1 2.4e-05 libfade.so
        1 2.4e-05 libmove.so
        1 2.4e-05 libsvg.so
        1 2.4e-05 libvpswitch.so
        1 2.4e-05 libwall.so
        1 2.4e-05 libmouse.so
        1 2.4e-05 gvfs-afc-volume-monitor
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        1 100.000 [vdso] (tgid:1572 range:0xd27000-0xd28000)
        1 2.4e-05 libXext.so.6.4.0
        1 2.4e-05 libXrender.so.1.3.0
        1 2.4e-05 libck-connector.so.0.0.0
        1 2.4e-05 gconfd-2
        1 2.4e-05 libpangocairo-1.0.so.0.2800.2
        1 2.4e-05 libwnck-1.so.22.3.30
        1 2.4e-05 libxklavier.so.16.0.0
        1 2.4e-05 libGL.so.260.19.06
        1 2.4e-05 udisks-daemon
        1 2.4e-05 sshd
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        1 100.000 [vdso] (tgid:1958 range:0xb44000-0xb45000)
 
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted CPU_CLK_UNHALTED events (Clock cycles when not halted) with a unit mask of 0x00 (core_p Core cycles when core is not halted) count 100000
samples  %        image name               symbol name
182724    8.9306  seti_boinc               sse_pulPoTf2u(float**, PoTPlan*)
157275    7.6867  seti_boinc               sse_pulPoTf3u(float**, PoTPlan*)
149761    7.3195  seti_boinc               sse_pulPoTf4u(float**, PoTPlan*)
140885    6.8857  seti_boinc               sse_pulPoTf5u(float**, PoTPlan*)
139743    6.8299  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
130841    6.3948  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
103612    5.0640  seti_boinc               lcgf(double, double)
93833     4.5860  seti_boinc               GaussFit(float*, int, int)
89893     4.3935  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
80333     3.9262  seti_boinc               sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
55020     2.6891  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
54242     2.6511  seti_boinc               find_pulse(float const*, int, float, int, int)
49982     2.4428  seti_boinc               sse_pulPoTf2ALu(float**, PoTPlan*)
49744     2.4312  seti_boinc               n1bv_128
48970     2.3934  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
42932     2.0983  seti_boinc               q1bv_8
38534     1.8833  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
37237     1.8199  seti_boinc               t1bv_8
33911     1.6574  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
31853     1.5568  seti_boinc               fftwf_cpy2d
25680     1.2551  seti_boinc               t1bv_4
25271     1.2351  seti_boinc               t_funct(int, int, int)
23452     1.1462  seti_boinc               __ieee754_log
21479     1.0498  seti_boinc               t3bv_4
18413     0.8999  seti_boinc               __i686.get_pc_thunk.bx
18096     0.8844  seti_boinc               find_triplets(float const*, int, float, int, int)
16965     0.8292  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
14177     0.6929  seti_boinc               n1bv_64
13575     0.6635  seti_boinc               sse_pulPoTf2(float**, PoTPlan*)
9823      0.4801  seti_boinc               t1bv_16
9222      0.4507  seti_boinc               __ieee754_pow
7666      0.3747  seti_boinc               _int_malloc
7404      0.3619  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
7095      0.3468  seti_boinc               sse_pulPoTf2L8(float**, PoTPlan*)
6929      0.3387  seti_boinc               pow
6771      0.3309  seti_boinc               log
6609      0.3230  seti_boinc               isnan
5487      0.2682  seti_boinc               sse_pulPoTf2L4(float**, PoTPlan*)
4726      0.2310  seti_boinc               _int_free
4069      0.1989  seti_boinc               malloc
3915      0.1913  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
3745      0.1830  seti_boinc               fraction_done(double, double)
3737      0.1826  seti_boinc               time_to_ra_dec(double, double*, double*)
3566      0.1743  seti_boinc               t1bv_2
3516      0.1718  seti_boinc               sse_pulPoTf2AL(float**, PoTPlan*)
3296      0.1611  seti_boinc               sse_pulPoTf2AL4(float**, PoTPlan*)
3273      0.1600  seti_boinc               sse_pulPoTf4L8(float**, PoTPlan*)
3229      0.1578  seti_boinc               sse_pulPoTf3L8(float**, PoTPlan*)
3154      0.1542  seti_boinc               n2bv_64
2921      0.1428  seti_boinc               free
2588      0.1265  seti_boinc               PulseProgressUnits(double, int)
2560      0.1251  seti_boinc               sse_pulPoTf3(float**, PoTPlan*)
2403      0.1174  seti_boinc               t2bv_64
1790      0.0875  seti_boinc               sse_pulPoTf5L4(float**, PoTPlan*)
1738      0.0849  seti_boinc               malloc_consolidate
1598      0.0781  seti_boinc               sse_pulPoTf2AL8(float**, PoTPlan*)
1431      0.0699  seti_boinc               operator new(unsigned int)
1325      0.0648  seti_boinc               analysis_config::analysis_config()
1312      0.0641  seti_boinc               cnvt_bin_hz(int, int)
1291      0.0631  seti_boinc               __memset_sse2
1191      0.0582  seti_boinc               checkpoint(unsigned char)
1135      0.0555  seti_boinc               calc_detection_freq(double, double, double)
1118      0.0546  seti_boinc               sse_pulPoTf5L8(float**, PoTPlan*)
1079      0.0527  seti_boinc               receiver_config::receiver_config()
1056      0.0516  seti_boinc               TripletProgressUnits()
1022      0.0499  seti_boinc               sse_pulPoTf5(float**, PoTPlan*)
960       0.0469  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
916       0.0448  seti_boinc               operator delete(void*)
887       0.0434  seti_boinc               boinc_fraction_done
877       0.0429  seti_boinc               sse_pulPoTf4(float**, PoTPlan*)
857       0.0419  seti_boinc               workunit_grp::workunit_grp()
853       0.0417  seti_boinc               gaussian::gaussian()
774       0.0378  seti_boinc               data_description_t::data_description_t()
745       0.0364  seti_boinc               __i686.get_pc_thunk.cx
744       0.0364  seti_boinc               seti_analyze(ANALYSIS_STATE&)
680       0.0332  seti_boinc               t2bv_32
665       0.0325  seti_boinc               floor
646       0.0316  seti_boinc               splitter_config::splitter_config()
623       0.0304  seti_boinc               finite
572       0.0280  seti_boinc               result::result()
551       0.0269  seti_boinc               __memmove_ssse3
542       0.0265  seti_boinc               tape::tape()
526       0.0257  seti_boinc               recorder_config::recorder_config()
507       0.0248  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
417       0.0204  seti_boinc               T.9614
414       0.0202  seti_boinc               n2bv_32
399       0.0195  seti_boinc               workunit_header::workunit_header()
367       0.0179  seti_boinc               n1bv_16
366       0.0179  seti_boinc               subband_description_t::subband_description_t()
365       0.0178  seti_boinc               apply
363       0.0177  seti_boinc               __ieee754_log10
351       0.0172  seti_boinc               n2bv_16
344       0.0168  seti_boinc               SpikeProgressUnits(int)
342       0.0167  seti_boinc               GaussianProgressUnits()
335       0.0164  seti_boinc               pulse::pulse()
333       0.0163  seti_boinc               _int_memalign
333       0.0163  seti_boinc               t2bv_4
292       0.0143  seti_boinc               MFILE::MFILE()
288       0.0141  seti_boinc               MFILE::~MFILE()
281       0.0137  seti_boinc               GAUSS_INFO::GAUSS_INFO()
280       0.0137  seti_boinc               apply_dit
277       0.0135  seti_boinc               apply
264       0.0129  seti_boinc               T.9615
236       0.0115  seti_boinc               memalign
221       0.0108  seti_boinc               T.9610
189       0.0092  seti_boinc               spike::spike()
179       0.0087  seti_boinc               apply
176       0.0086  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
161       0.0079  seti_boinc               PULSE_INFO::~PULSE_INFO()
153       0.0075  seti_boinc               T.9619
151       0.0074  seti_boinc               boinc_time_to_checkpoint
148       0.0072  seti_boinc               n2bv_8
139       0.0068  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
137       0.0067  seti_boinc               log10
135       0.0066  seti_boinc               apply
134       0.0065  seti_boinc               PULSE_INFO::PULSE_INFO()
127       0.0062  seti_boinc               fftwf_execute_dft
123       0.0060  seti_boinc               floorf
104       0.0051  seti_boinc               apply_dif
103       0.0050  seti_boinc               fftwf_malloc
85        0.0042  seti_boinc               invert_lcgf(float, float, float)
84        0.0041  seti_boinc               apply_iter
84        0.0041  seti_boinc               fftwf_free
71        0.0035  seti_boinc               fftwf_kernel_malloc
59        0.0029  seti_boinc               fftwf_kernel_free
56        0.0027  seti_boinc               SPIKE_INFO::SPIKE_INFO()
55        0.0027  seti_boinc               apply
54        0.0026  seti_boinc               apply_extra_iter
53        0.0026  seti_boinc               apply_before
49        0.0024  seti_boinc               copy
42        0.0021  seti_boinc               free_a(void*)
40        0.0020  seti_boinc               malloc_a(unsigned int, unsigned int)
39        0.0019  seti_boinc               fftwf_cpy2d_ci
17       8.3e-04  seti_boinc               worker_signal_handler(int)
14       6.8e-04  seti_boinc               boinc_sleep(double)
13       6.4e-04  seti_boinc               timer_handler()
12       5.9e-04  [vdso] (tgid:2317 range:0x3dd000-0x3de000) [vdso] (tgid:2317 range:0x3dd000-0x3de000)
10       4.9e-04  seti_boinc               __libc_disable_asynccancel
9        4.4e-04  seti_boinc               __libc_enable_asynccancel
5        2.4e-04  seti_boinc               __nanosleep_nocancel
5        2.4e-04  seti_boinc               dtime()
5        2.4e-04  seti_boinc               getrusage
4        2.0e-04  seti_boinc               gettimeofday
4        2.0e-04  seti_boinc               plan_PulsePoT(PoTPlan*, int, float*, int*)
3        1.5e-04  seti_boinc               usleep
2        9.8e-05  seti_boinc               timer_thread(void*)
1        4.9e-05  seti_boinc               GetPulsePoTLen(long, int*, int*)
1        4.9e-05  seti_boinc               PULSE_INFO::operator=(PULSE_INFO const&)
1        4.9e-05  seti_boinc               analysis_config::operator=(analysis_config const&)
1        4.9e-05  seti_boinc               nanosleep
1        4.9e-05  seti_boinc               spike::operator=(spike const&)
1        4.9e-05  seti_boinc               strcpy
 
 
Sun Aug 14 19:06:26 CDT 2011
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted CPU_CLK_UNHALTED events (Clock cycles when not halted) with a unit mask of 0x00 (core_p Core cycles when core is not halted) count 100000
CPU_CLK_UNHALT...|
  samples|      %|
------------------
  2078781 50.3390 no-vmlinux
  2025861 49.0576 seti_boinc
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	  2025842 99.9991 seti_boinc
	       19 9.4e-04 [vdso] (tgid:2317 range:0x3dd000-0x3de000)
    18287  0.4428 oprofiled
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	    18279 99.9563 oprofiled
	        8  0.0437 [vdso] (tgid:2858 range:0xc8c000-0xc8d000)
     3077  0.0745 libc-2.12.1.so
      798  0.0193 bash
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	      795 99.6241 bash
	        3  0.3759 [vdso] (tgid:2894 range:0x32f000-0x330000)
      542  0.0131 libcairo.so.2.11000.0
      414  0.0100 ld-2.12.1.so
      277  0.0067 libglib-2.0.so.0.2600.1
      225  0.0054 dbus-daemon
      194  0.0047 boinc
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	      103 53.0928 boinc
	       91 46.9072 [vdso] (tgid:935 range:0x3a4000-0x3a5000)
      193  0.0047 libdbus-1.so.3.5.2
      155  0.0038 libpthread-2.12.1.so
      119  0.0029 libgobject-2.0.so.0.2600.1
       91  0.0022 Xorg
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	       79 86.8132 Xorg
	       12 13.1868 [vdso] (tgid:1221 range:0x7bc000-0x7bd000)
       64  0.0015 libORBit-2.so.0.1.0
       61  0.0015 nvidia_drv.so
       39 9.4e-04 libgconf-2.so.4.1.5
       32 7.7e-04 libgdk-x11-2.0.so.0.2200.0
       31 7.5e-04 libdbus-glib-1.so.2.1.0
       28 6.8e-04 libnvidia-glcore.so.260.19.06
       23 5.6e-04 libX11.so.6.3.0
       22 5.3e-04 compiz
       22 5.3e-04 libxcb.so.1.1.0
       18 4.4e-04 NetworkManager
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	       14 77.7778 NetworkManager
	        4 22.2222 [vdso] (tgid:808 range:0x576000-0x577000)
       16 3.9e-04 libgthread-2.0.so.0.2600.1
       12 2.9e-04 libgtk-x11-2.0.so.0.2200.0
        9 2.2e-04 librt-2.12.1.so
        8 1.9e-04 grep
        8 1.9e-04 libnm-util.so.1.6.0
        7 1.7e-04 mawk
        7 1.7e-04 libgconfbackend-xml.so
        7 1.7e-04 libgio-2.0.so.0.2600.1
        7 1.7e-04 libpango-1.0.so.0.2800.2
        7 1.7e-04 libpangoft2-1.0.so.0.2800.2
        6 1.5e-04 dash
        6 1.5e-04 gconfd-2
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        4 66.6667 gconfd-2
	        2 33.3333 [vdso] (tgid:1471 range:0x3fa000-0x3fb000)
        5 1.2e-04 libm-2.12.1.so
        5 1.2e-04 nm-applet
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        3 60.0000 [vdso] (tgid:1499 range:0x84a000-0x84b000)
	        2 40.0000 nm-applet
        5 1.2e-04 libcurl.so.4.2.0
        5 1.2e-04 libusbmuxd.so.1.0.4
        4 9.7e-05 libpam.so.0.82.2
        4 9.7e-05 libudev.so.0.9.1
        4 9.7e-05 sudo
        4 9.7e-05 libgnome-keyring.so.0.1.1
        4 9.7e-05 libstartup-notification-1.so.0.0.0
        3 7.3e-05 gnome-panel
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        2 66.6667 [vdso] (tgid:1505 range:0xe2f000-0xe30000)
	        1 33.3333 gnome-panel
        3 7.3e-05 libnm-glib.so.2.4.1
        3 7.3e-05 irqbalance
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        2 66.6667 [vdso] (tgid:925 range:0x5ad000-0x5ae000)
	        1 33.3333 irqbalance
        3 7.3e-05 rsyslogd
        2 4.8e-05 libcrypto.so.0.9.8
        2 4.8e-05 wpa_supplicant
        2 4.8e-05 ssh-agent
        2 4.8e-05 libfade.so
        2 4.8e-05 libsession.so
        2 4.8e-05 gnome-settings-daemon
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        2 100.000 [vdso] (tgid:1479 range:0x30f000-0x310000)
        2 4.8e-05 libwnck-1.so.22.3.30
        2 4.8e-05 libxklavier.so.16.0.0
        2 4.8e-05 udisks-daemon
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        2 100.000 [vdso] (tgid:1567 range:0x286000-0x287000)
        2 4.8e-05 evdev_drv.so
        1 2.4e-05 cat
        1 2.4e-05 ls
        1 2.4e-05 rm
        1 2.4e-05 libacl.so.1.1.0
        1 2.4e-05 libnsl-2.12.1.so
        1 2.4e-05 libnss_compat-2.12.1.so
        1 2.4e-05 libpopt.so.0.0.0
        1 2.4e-05 pam_deny.so
        1 2.4e-05 pam_limits.so
        1 2.4e-05 expr
        1 2.4e-05 gnome-power-manager
        1 2.4e-05 nautilus
        1 2.4e-05 ophelp
        1 2.4e-05 libccp.so
        1 2.4e-05 libdecoration.so
        1 2.4e-05 libexpo.so
        1 2.4e-05 libscale.so
        1 2.4e-05 libscaleaddon.so
        1 2.4e-05 libsnap.so
        1 2.4e-05 libworkarounds.so
        1 2.4e-05 libgconf.so
        1 2.4e-05 libkeybindings.so
        1 2.4e-05 gvfs-afc-volume-monitor
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        1 100.000 [vdso] (tgid:1572 range:0xd27000-0xd28000)
        1 2.4e-05 libXext.so.6.4.0
        1 2.4e-05 libavahi-core.so.7.0.0
        1 2.4e-05 libcompizconfig.so.0.0.0
        1 2.4e-05 libgvfscommon.so.0.0.0
        1 2.4e-05 libpulse-mainloop-glib.so.0.0.4
        1 2.4e-05 libstdc++.so.6.0.14
        1 2.4e-05 libupower-glib.so.1.0.1
        1 2.4e-05 rtkit-daemon
        1 2.4e-05 libextmod.so
        1 2.4e-05 console-kit-daemon
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        1 100.000 [vdso] (tgid:1147 range:0xe4e000-0xe4f000)
        1 2.4e-05 sshd
	CPU_CLK_UNHALT...|
	  samples|      %|
	------------------
	        1 100.000 [vdso] (tgid:1958 range:0xb44000-0xb45000)
 
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted CPU_CLK_UNHALTED events (Clock cycles when not halted) with a unit mask of 0x00 (core_p Core cycles when core is not halted) count 100000
samples  %        image name               symbol name
229889   11.2350  seti_boinc               GetFixedPoT(float*, int, int, float*, int, int)
213368   10.4276  seti_boinc               f_GetChiSq(float*, int, int, float, float, float*, float*)
166818    8.1526  seti_boinc               lcgf(double, double)
154471    7.5492  seti_boinc               GaussFit(float*, int, int)
148454    7.2551  seti_boinc               analyze_pot(float*, int, ChirpFftPair_t&)
133413    6.5201  seti_boinc               sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
88448     4.3226  seti_boinc               FindSpikes(float*, int, int, SETI_WU_INFO&)
83532     4.0823  seti_boinc               n1bv_128
80577     3.9379  seti_boinc               f_GetTrueMean(float*, int, float, int, int)
71012     3.4704  seti_boinc               q1bv_8
63800     3.1180  seti_boinc               f_GetPeak(float*, int, int, float, float, float*)
61805     3.0205  seti_boinc               t1bv_8
54988     2.6873  seti_boinc               float_to_uchar(float*, unsigned char*, long, float)
52684     2.5747  seti_boinc               fftwf_cpy2d
42529     2.0784  seti_boinc               t1bv_4
37143     1.8152  seti_boinc               __ieee754_log
35772     1.7482  seti_boinc               t3bv_4
27782     1.3577  seti_boinc               v_GetPowerSpectrum(float (*) [2], float*, int)
27218     1.3302  seti_boinc               find_triplets(float const*, int, float, int, int)
23696     1.1581  seti_boinc               find_pulse(float const*, int, float, int, int)
23347     1.1410  seti_boinc               n1bv_64
16360     0.7995  seti_boinc               t1bv_16
14680     0.7174  seti_boinc               __ieee754_pow
14646     0.7158  seti_boinc               __i686.get_pc_thunk.bx
11476     0.5608  seti_boinc               pow
10890     0.5322  seti_boinc               log
10729     0.5243  seti_boinc               isnan
7161      0.3500  seti_boinc               _int_malloc
6783      0.3315  seti_boinc               sse_pulPoTf4L8(float**, PoTPlan*)
6424      0.3139  seti_boinc               ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
6088      0.2975  seti_boinc               fraction_done(double, double)
6042      0.2953  seti_boinc               sse_pulPoTf3(float**, PoTPlan*)
6004      0.2934  seti_boinc               n2bv_64
5971      0.2918  seti_boinc               t1bv_2
5900      0.2883  seti_boinc               sse_pulPoTf3L8(float**, PoTPlan*)
5188      0.2535  seti_boinc               _int_free
5082      0.2484  seti_boinc               PulseProgressUnits(double, int)
5000      0.2444  seti_boinc               sse_pulPoTf2L4(float**, PoTPlan*)
4864      0.2377  seti_boinc               malloc
4534      0.2216  seti_boinc               sse_pulPoTf2L8(float**, PoTPlan*)
4453      0.2176  seti_boinc               t2bv_64
4060      0.1984  seti_boinc               sse_pulPoTf2(float**, PoTPlan*)
4050      0.1979  seti_boinc               time_to_ra_dec(double, double*, double*)
3282      0.1604  seti_boinc               sse_pulPoTf5L4(float**, PoTPlan*)
3084      0.1507  seti_boinc               free
3015      0.1473  seti_boinc               sse_pulPoTf2AL4(float**, PoTPlan*)
2649      0.1295  seti_boinc               sse_pulPoTf3u(float**, PoTPlan*)
2586      0.1264  seti_boinc               sse_pulPoTf5L8(float**, PoTPlan*)
2386      0.1166  seti_boinc               sse_pulPoTf5(float**, PoTPlan*)
2126      0.1039  seti_boinc               sse_pulPoTf4u(float**, PoTPlan*)
2081      0.1017  seti_boinc               sse_pulPoTf4(float**, PoTPlan*)
1933      0.0945  seti_boinc               checkpoint(unsigned char)
1778      0.0869  seti_boinc               TripletProgressUnits()
1563      0.0764  seti_boinc               cnvt_bin_hz(int, int)
1552      0.0758  seti_boinc               operator new(unsigned int)
1438      0.0703  seti_boinc               gaussian::gaussian()
1369      0.0669  seti_boinc               boinc_fraction_done
1362      0.0666  seti_boinc               t2bv_32
1274      0.0623  seti_boinc               analysis_config::analysis_config()
1265      0.0618  seti_boinc               calc_detection_freq(double, double, double)
1259      0.0615  seti_boinc               std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
1116      0.0545  seti_boinc               receiver_config::receiver_config()
1090      0.0533  seti_boinc               floor
1046      0.0511  seti_boinc               finite
1012      0.0495  seti_boinc               __i686.get_pc_thunk.cx
968       0.0473  seti_boinc               sse_pulPoTf5u(float**, PoTPlan*)
962       0.0470  seti_boinc               __memset_sse2
911       0.0445  seti_boinc               malloc_consolidate
908       0.0444  seti_boinc               operator delete(void*)
899       0.0439  seti_boinc               workunit_grp::workunit_grp()
814       0.0398  seti_boinc               sse_pulPoTf2AL(float**, PoTPlan*)
796       0.0389  seti_boinc               GAUSS_INFO::~GAUSS_INFO()
781       0.0382  seti_boinc               data_description_t::data_description_t()
737       0.0360  seti_boinc               splitter_config::splitter_config()
735       0.0359  seti_boinc               sse_pulPoTf2AL8(float**, PoTPlan*)
654       0.0320  seti_boinc               __memmove_ssse3
609       0.0298  seti_boinc               GaussianProgressUnits()
582       0.0284  seti_boinc               result::result()
555       0.0271  seti_boinc               tape::tape()
534       0.0261  seti_boinc               recorder_config::recorder_config()
509       0.0249  seti_boinc               apply
490       0.0239  seti_boinc               MFILE::~MFILE()
478       0.0234  seti_boinc               apply
478       0.0234  seti_boinc               n2bv_32
470       0.0230  seti_boinc               GAUSS_INFO::GAUSS_INFO()
468       0.0229  seti_boinc               MFILE::MFILE()
379       0.0185  seti_boinc               T.9614
374       0.0183  seti_boinc               workunit_header::workunit_header()
366       0.0179  seti_boinc               apply_dit
359       0.0175  seti_boinc               subband_description_t::subband_description_t()
352       0.0172  seti_boinc               seti_analyze(ANALYSIS_STATE&)
279       0.0136  seti_boinc               apply
263       0.0129  seti_boinc               boinc_time_to_checkpoint
249       0.0122  seti_boinc               T.9610
225       0.0110  seti_boinc               T.9615
198       0.0097  seti_boinc               apply
176       0.0086  seti_boinc               T.9619
143       0.0070  seti_boinc               apply_dif
122       0.0060  seti_boinc               apply_iter
111       0.0054  seti_boinc               __ieee754_log10
109       0.0053  seti_boinc               apply_before
97        0.0047  seti_boinc               apply
85        0.0042  seti_boinc               fftwf_execute_dft
82        0.0040  seti_boinc               SPIKE_INFO::~SPIKE_INFO()
74        0.0036  seti_boinc               copy
69        0.0034  seti_boinc               SpikeProgressUnits(int)
61        0.0030  seti_boinc               log10
52        0.0025  seti_boinc               spike::spike()
44        0.0022  seti_boinc               fftwf_cpy2d_ci
30        0.0015  seti_boinc               ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
19       9.3e-04  [vdso] (tgid:2317 range:0x3dd000-0x3de000) [vdso] (tgid:2317 range:0x3dd000-0x3de000)
19       9.3e-04  seti_boinc               timer_handler()
15       7.3e-04  seti_boinc               __nanosleep_nocancel
15       7.3e-04  seti_boinc               worker_signal_handler(int)
14       6.8e-04  seti_boinc               SPIKE_INFO::SPIKE_INFO()
9        4.4e-04  seti_boinc               __libc_disable_asynccancel
8        3.9e-04  seti_boinc               __libc_enable_asynccancel
7        3.4e-04  seti_boinc               boinc_sleep(double)
7        3.4e-04  seti_boinc               getrusage
5        2.4e-04  seti_boinc               _int_memalign
4        2.0e-04  seti_boinc               GetPulsePoTLen(long, int*, int*)
4        2.0e-04  seti_boinc               PULSE_INFO::PULSE_INFO()
4        2.0e-04  seti_boinc               dtime()
4        2.0e-04  seti_boinc               plan_PulsePoT(PoTPlan*, int, float*, int*)
4        2.0e-04  seti_boinc               usleep
3        1.5e-04  seti_boinc               gettimeofday
3        1.5e-04  seti_boinc               pulse::pulse()
2        9.8e-05  seti_boinc               fftwf_malloc
2        9.8e-05  seti_boinc               floorf
2        9.8e-05  seti_boinc               memalign
2        9.8e-05  seti_boinc               result_group_start()
2        9.8e-05  seti_boinc               timer_thread(void*)
1        4.9e-05  seti_boinc               PULSE_INFO::~PULSE_INFO()
1        4.9e-05  seti_boinc               calloc_a(unsigned int, unsigned int, unsigned int)
1        4.9e-05  seti_boinc               fftwf_free
1        4.9e-05  seti_boinc               invert_lcgf(float, float, float)
1        4.9e-05  seti_boinc               malloc_a(unsigned int, unsigned int)
1        4.9e-05  seti_boinc               nanosleep
 
 
Sun Aug 14 19:08:31 CDT 2011
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted LLC_MISSES events (Last level cache demand requests from this core that missed the LLC) with a unit mask of 0x41 (No unit mask) count 10000
 LLC_MISSES:10000|
  samples|      %|
------------------
    39325 99.7843 seti_boinc
       22  0.0558 libc-2.12.1.so
       13  0.0330 ld-2.12.1.so
        8  0.0203 libglib-2.0.so.0.2600.1
        6  0.0152 bash
        6  0.0152 no-vmlinux
        4  0.0101 dbus-daemon
        4  0.0101 libpthread-2.12.1.so
        3  0.0076 compiz
        2  0.0051 libdbus-1.so.3.5.2
        2  0.0051 oprofiled
        2  0.0051 libgobject-2.0.so.0.2600.1
        1  0.0025 libm-2.12.1.so
        1  0.0025 Xorg
        1  0.0025 boinc
        1  0.0025 libscale.so
        1  0.0025 libsession.so
        1  0.0025 libkeyboard.so
        1  0.0025 libcairo.so.2.11000.0
        1  0.0025 libcompizconfig.so.0.0.0
        1  0.0025 libcurl.so.4.2.0
        1  0.0025 libdbus-glib-1.so.2.1.0
        1  0.0025 libgdk-x11-2.0.so.0.2200.0
        1  0.0025 libxcb.so.1.1.0
        1  0.0025 NetworkManager
 
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted LLC_MISSES events (Last level cache demand requests from this core that missed the LLC) with a unit mask of 0x41 (No unit mask) count 10000
samples  %        symbol name
22395    56.9485  GetFixedPoT(float*, int, int, float*, int, int)
11268    28.6535  analyze_pot(float*, int, ChirpFftPair_t&)
2682      6.8201  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
559       1.4215  n1bv_128
433       1.1011  fftwf_cpy2d
353       0.8976  n1bv_64
279       0.7095  q1bv_8
253       0.6434  n2bv_64
190       0.4832  t3bv_4
173       0.4399  t1bv_4
163       0.4145  v_GetPowerSpectrum(float (*) [2], float*, int)
116       0.2950  FindSpikes(float*, int, int, SETI_WU_INFO&)
50        0.1271  find_pulse(float const*, int, float, int, int)
41        0.1043  t1bv_8
35        0.0890  t1bv_2
25        0.0636  __i686.get_pc_thunk.bx
22        0.0559  n2bv_32
21        0.0534  apply
19        0.0483  n2bv_16
18        0.0458  _int_malloc
14        0.0356  find_triplets(float const*, int, float, int, int)
13        0.0331  seti_analyze(ANALYSIS_STATE&)
11        0.0280  t1bv_16
10        0.0254  GaussFit(float*, int, int)
10        0.0254  TripletProgressUnits()
10        0.0254  apply
8         0.0203  apply
8         0.0203  sse_pulPoTf3L8(float**, PoTPlan*)
7         0.0178  apply_before
7         0.0178  apply_dif
7         0.0178  apply_dit
7         0.0178  malloc
6         0.0153  apply_iter
5         0.0127  apply
5         0.0127  fftwf_execute_dft
4         0.0102  SPIKE_INFO::~SPIKE_INFO()
4         0.0102  __ieee754_pow
4         0.0102  boinc_fraction_done
4         0.0102  cnvt_bin_hz(int, int)
4         0.0102  fftwf_cpy2d_ci
4         0.0102  log
4         0.0102  pow
4         0.0102  sse_pulPoTf2L8(float**, PoTPlan*)
4         0.0102  tape::tape()
3         0.0076  PulseProgressUnits(double, int)
3         0.0076  T.9610
3         0.0076  __ieee754_log
3         0.0076  calc_detection_freq(double, double, double)
3         0.0076  data_description_t::data_description_t()
3         0.0076  f_GetChiSq(float*, int, int, float, float, float*, float*)
3         0.0076  isnan
3         0.0076  operator new(unsigned int)
3         0.0076  sse_pulPoTf3u(float**, PoTPlan*)
3         0.0076  time_to_ra_dec(double, double*, double*)
2         0.0051  GaussianProgressUnits()
2         0.0051  _int_free
2         0.0051  apply
2         0.0051  free
2         0.0051  malloc_consolidate
2         0.0051  operator delete(void*)
2         0.0051  receiver_config::receiver_config()
2         0.0051  splitter_config::splitter_config()
2         0.0051  sse_pulPoTf2(float**, PoTPlan*)
2         0.0051  sse_pulPoTf2AL(float**, PoTPlan*)
2         0.0051  sse_pulPoTf3(float**, PoTPlan*)
2         0.0051  sse_pulPoTf4u(float**, PoTPlan*)
2         0.0051  t2bv_64
1         0.0025  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
1         0.0025  __ieee754_log10
1         0.0025  copy
1         0.0025  gaussian::gaussian()
1         0.0025  getrusage
1         0.0025  recorder_config::recorder_config()
1         0.0025  sse_pulPoTf2ALu(float**, PoTPlan*)
1         0.0025  timer_handler()
1         0.0025  workunit_grp::workunit_grp()
1         0.0025  workunit_header::workunit_header()
 
 
Sun Aug 14 19:10:35 CDT 2011
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted LLC_REFS events (Last level cache demand requests from this core) with a unit mask of 0x4f (No unit mask) count 10000
   LLC_REFS:10000|
  samples|      %|
------------------
   171422 99.4922 seti_boinc
      274  0.1590 libc-2.12.1.so
      110  0.0638 ld-2.12.1.so
       63  0.0366 Xorg
       54  0.0313 bash
       53  0.0308 libglib-2.0.so.0.2600.1
       42  0.0244 libcairo.so.2.11000.0
       36  0.0209 libgobject-2.0.so.0.2600.1
       27  0.0157 libpthread-2.12.1.so
       27  0.0157 no-vmlinux
       26  0.0151 boinc
	   LLC_REFS:10000|
	  samples|      %|
	------------------
	       25 96.1538 boinc
	        1  3.8462 [vdso] (tgid:935 range:0x3a4000-0x3a5000)
       24  0.0139 nvidia_drv.so
       19  0.0110 libX11.so.6.3.0
       18  0.0104 oprofiled
       17  0.0099 libdbus-1.so.3.5.2
       15  0.0087 dbus-daemon
        9  0.0052 libORBit-2.so.0.1.0
        9  0.0052 libgdk-x11-2.0.so.0.2200.0
        5  0.0029 libgtk-x11-2.0.so.0.2200.0
        5  0.0029 libxcb.so.1.1.0
        4  0.0023 gnome-screensaver
        3  0.0017 mawk
        3  0.0017 libdbus-glib-1.so.2.1.0
        3  0.0017 libGL.so.260.19.06
        3  0.0017 NetworkManager
        2  0.0012 compiz
	   LLC_REFS:10000|
	  samples|      %|
	------------------
	        1 50.0000 compiz
	        1 50.0000 [vdso] (tgid:1496 range:0xd6a000-0xd6b000)
        2  0.0012 sudo
        2  0.0012 libgconf-2.so.4.1.5
        2  0.0012 evdev_drv.so
        2  0.0012 irqbalance
        1 5.8e-04 libcrypto.so.0.9.8
        1 5.8e-04 libm-2.12.1.so
        1 5.8e-04 librt-2.12.1.so
        1 5.8e-04 libccp.so
        1 5.8e-04 libfade.so
        1 5.8e-04 libscale.so
        1 5.8e-04 libkeyboard.so
        1 5.8e-04 libmurrine.so
        1 5.8e-04 libcurl.so.4.2.0
        1 5.8e-04 gconfd-2
        1 5.8e-04 libgmodule-2.0.so.0.2600.1
        1 5.8e-04 libgthread-2.0.so.0.2600.1
        1 5.8e-04 libnm-glib.so.2.4.1
        1 5.8e-04 libpango-1.0.so.0.2800.2
        1 5.8e-04 libnvidia-glcore.so.260.19.06
        1 5.8e-04 libextmod.so
 
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted LLC_REFS events (Last level cache demand requests from this core) with a unit mask of 0x4f (No unit mask) count 10000
samples  %        symbol name
29983    17.4916  t1bv_8
22892    13.3548  GetFixedPoT(float*, int, int, float*, int, int)
21621    12.6133  analyze_pot(float*, int, ChirpFftPair_t&)
20687    12.0684  q1bv_8
15937     9.2974  fftwf_cpy2d
12103     7.0607  n1bv_64
10163     5.9289  n1bv_128
8157      4.7587  t1bv_4
7371      4.3001  v_GetPowerSpectrum(float (*) [2], float*, int)
5363      3.1287  t3bv_4
4729      2.7588  FindSpikes(float*, int, int, SETI_WU_INFO&)
2725      1.5897  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
2061      1.2024  t1bv_16
1831      1.0682  t2bv_64
1823      1.0635  n2bv_64
1014      0.5916  t1bv_2
325       0.1896  t2bv_32
169       0.0986  _int_malloc
145       0.0846  __i686.get_pc_thunk.bx
130       0.0758  find_triplets(float const*, int, float, int, int)
120       0.0700  find_pulse(float const*, int, float, int, int)
116       0.0677  apply
107       0.0624  GaussFit(float*, int, int)
87        0.0508  time_to_ra_dec(double, double*, double*)
79        0.0461  apply
76        0.0443  __ieee754_pow
74        0.0432  malloc
69        0.0403  apply_dit
68        0.0397  sse_pulPoTf3L8(float**, PoTPlan*)
63        0.0368  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
63        0.0368  seti_analyze(ANALYSIS_STATE&)
49        0.0286  checkpoint(unsigned char)
49        0.0286  malloc_consolidate
47        0.0274  _int_free
44        0.0257  isnan
43        0.0251  TripletProgressUnits()
42        0.0245  MFILE::MFILE()
42        0.0245  __memset_sse2
42        0.0245  fraction_done(double, double)
35        0.0204  analysis_config::analysis_config()
33        0.0193  apply
32        0.0187  f_GetChiSq(float*, int, int, float, float, float*, float*)
30        0.0175  receiver_config::receiver_config()
30        0.0175  splitter_config::splitter_config()
30        0.0175  workunit_grp::workunit_grp()
29        0.0169  n2bv_32
28        0.0163  cnvt_bin_hz(int, int)
27        0.0158  recorder_config::recorder_config()
24        0.0140  apply_dif
24        0.0140  pow
23        0.0134  calc_detection_freq(double, double, double)
22        0.0128  floor
22        0.0128  tape::tape()
21        0.0123  boinc_time_to_checkpoint
21        0.0123  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
19        0.0111  log
19        0.0111  operator new(unsigned int)
18        0.0105  __ieee754_log
18        0.0105  __memmove_ssse3
18        0.0105  apply
18        0.0105  f_GetTrueMean(float*, int, float, int, int)
18        0.0105  sse_pulPoTf3(float**, PoTPlan*)
16        0.0093  gaussian::gaussian()
15        0.0088  fftwf_execute_dft
14        0.0082  lcgf(double, double)
14        0.0082  sse_pulPoTf2L8(float**, PoTPlan*)
14        0.0082  subband_description_t::subband_description_t()
13        0.0076  data_description_t::data_description_t()
13        0.0076  f_GetPeak(float*, int, int, float, float, float*)
13        0.0076  free
13        0.0076  operator delete(void*)
13        0.0076  result::result()
12        0.0070  PulseProgressUnits(double, int)
12        0.0070  boinc_fraction_done
11        0.0064  SPIKE_INFO::~SPIKE_INFO()
11        0.0064  apply
10        0.0058  GaussianProgressUnits()
10        0.0058  MFILE::~MFILE()
10        0.0058  apply_iter
9         0.0053  GAUSS_INFO::~GAUSS_INFO()
9         0.0053  float_to_uchar(float*, unsigned char*, long, float)
8         0.0047  SpikeProgressUnits(int)
8         0.0047  workunit_header::workunit_header()
7         0.0041  __i686.get_pc_thunk.cx
7         0.0041  __ieee754_log10
7         0.0041  apply_before
6         0.0035  SPIKE_INFO::SPIKE_INFO()
6         0.0035  sse_pulPoTf3u(float**, PoTPlan*)
6         0.0035  sse_pulPoTf4L8(float**, PoTPlan*)
5         0.0029  T.9610
5         0.0029  sse_pulPoTf2(float**, PoTPlan*)
4         0.0023  fftwf_cpy2d_ci
4         0.0023  log10
4         0.0023  spike::spike()
4         0.0023  sse_pulPoTf2AL4(float**, PoTPlan*)
4         0.0023  sse_pulPoTf5L8(float**, PoTPlan*)
3         0.0018  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
3         0.0018  sse_pulPoTf5L4(float**, PoTPlan*)
2         0.0012  __libc_disable_asynccancel
2         0.0012  copy
2         0.0012  timer_handler()
1        5.8e-04  GAUSS_INFO::GAUSS_INFO()
1        5.8e-04  PULSE_INFO::~PULSE_INFO()
1        5.8e-04  T.9614
1        5.8e-04  __nanosleep_nocancel
1        5.8e-04  _int_memalign
1        5.8e-04  boinc_sleep(double)
1        5.8e-04  calloc_a(unsigned int, unsigned int, unsigned int)
1        5.8e-04  dtime()
1        5.8e-04  getrusage
1        5.8e-04  memalign
1        5.8e-04  pulse::pulse()
1        5.8e-04  sse_pulPoTf2AL8(float**, PoTPlan*)
1        5.8e-04  sse_pulPoTf2L4(float**, PoTPlan*)
1        5.8e-04  sse_pulPoTf4(float**, PoTPlan*)
1        5.8e-04  sse_pulPoTf5(float**, PoTPlan*)
1        5.8e-04  sse_pulPoTf5u(float**, PoTPlan*)
1        5.8e-04  timer_thread(void*)
 
 
Sun Aug 14 19:12:38 CDT 2011
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted BR_INST_RETIRED events (number of branch instructions retired) with a unit mask of 0x00 (any Retired branch instructions) count 10000
BR_INST_RETIRE...|
  samples|      %|
------------------
   654657 98.3750 seti_boinc
     4412  0.6630 libc-2.12.1.so
     3637  0.5465 oprofiled
     1083  0.1627 bash
      590  0.0887 libcairo.so.2.11000.0
      432  0.0649 ld-2.12.1.so
      148  0.0222 dbus-daemon
      104  0.0156 libdbus-1.so.3.5.2
       66  0.0099 libglib-2.0.so.0.2600.1
       63  0.0095 ophelp
       48  0.0072 libpthread-2.12.1.so
       39  0.0059 boinc
	BR_INST_RETIRE...|
	  samples|      %|
	------------------
	       35 89.7436 boinc
	        4 10.2564 [vdso] (tgid:935 range:0x3a4000-0x3a5000)
       35  0.0053 libgobject-2.0.so.0.2600.1
       33  0.0050 Xorg
	BR_INST_RETIRE...|
	  samples|      %|
	------------------
	       32 96.9697 Xorg
	        1  3.0303 [vdso] (tgid:1221 range:0x7bc000-0x7bd000)
       13  0.0020 nvidia_drv.so
       11  0.0017 libORBit-2.so.0.1.0
       10  0.0015 libpam.so.0.82.2
       10  0.0015 libX11.so.6.3.0
        9  0.0014 dash
        8  0.0012 grep
        8  0.0012 no-vmlinux
        8  0.0012 libpangoft2-1.0.so.0.2800.2
        5 7.5e-04 sudo
        5 7.5e-04 libgthread-2.0.so.0.2600.1
        4 6.0e-04 mawk
        4 6.0e-04 libgdk-x11-2.0.so.0.2200.0
        3 4.5e-04 libm-2.12.1.so
        3 4.5e-04 libxcb.so.1.1.0
        2 3.0e-04 libgconf-2.so.4.1.5
        2 3.0e-04 libgtk-x11-2.0.so.0.2200.0
        2 3.0e-04 libnvidia-glcore.so.260.19.06
        2 3.0e-04 NetworkManager
        2 3.0e-04 irqbalance
        1 1.5e-04 libnss_compat-2.12.1.so
        1 1.5e-04 libnss_files-2.12.1.so
        1 1.5e-04 libpopt.so.0.0.0
        1 1.5e-04 libmurrine.so
        1 1.5e-04 gvfs-afc-volume-monitor
	BR_INST_RETIRE...|
	  samples|      %|
	------------------
	        1 100.000 [vdso] (tgid:1572 range:0xd27000-0xd28000)
        1 1.5e-04 libgio-2.0.so.0.2600.1
        1 1.5e-04 libgvfscommon.so.0.0.0
        1 1.5e-04 libnl.so.1.1
        1 1.5e-04 libnm-util.so.1.6.0
        1 1.5e-04 libpango-1.0.so.0.2800.2
        1 1.5e-04 libpangocairo-1.0.so.0.2800.2
        1 1.5e-04 libpixman-1.so.0.18.4
        1 1.5e-04 libusbmuxd.so.1.0.4
 
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted BR_INST_RETIRED events (number of branch instructions retired) with a unit mask of 0x00 (any Retired branch instructions) count 10000
samples  %        symbol name
159859   24.4194  FindSpikes(float*, int, int, SETI_WU_INFO&)
79835    12.1953  f_GetTrueMean(float*, int, float, int, int)
48100     7.3476  fftwf_cpy2d
47558     7.2648  f_GetPeak(float*, int, int, float, float, float*)
44627     6.8170  GaussFit(float*, int, int)
30773     4.7008  find_triplets(float const*, int, float, int, int)
17619     2.6914  find_pulse(float const*, int, float, int, int)
17405     2.6587  GetFixedPoT(float*, int, int, float*, int, int)
16504     2.5211  analyze_pot(float*, int, ChirpFftPair_t&)
14487     2.2130  f_GetChiSq(float*, int, int, float, float, float*, float*)
14183     2.1665  lcgf(double, double)
13359     2.0407  __ieee754_pow
10743     1.6411  pow
10013     1.5295  v_GetPowerSpectrum(float (*) [2], float*, int)
9724      1.4854  isnan
9471      1.4468  float_to_uchar(float*, unsigned char*, long, float)
8997      1.3743  __i686.get_pc_thunk.bx
8388      1.2813  _int_free
6861      1.0481  _int_malloc
6796      1.0381  malloc
6086      0.9297  TripletProgressUnits()
5471      0.8357  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
5465      0.8348  free
5404      0.8255  log
4944      0.7552  __ieee754_log
4717      0.7205  t1bv_4
3647      0.5571  t3bv_4
3189      0.4871  sse_pulPoTf4L8(float**, PoTPlan*)
3132      0.4784  fraction_done(double, double)
2909      0.4444  time_to_ra_dec(double, double*, double*)
2601      0.3973  __i686.get_pc_thunk.cx
2339      0.3573  operator new(unsigned int)
1761      0.2690  sse_pulPoTf3(float**, PoTPlan*)
1724      0.2634  t1bv_8
1623      0.2479  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
1547      0.2363  checkpoint(unsigned char)
1385      0.2116  t1bv_2
1360      0.2077  GAUSS_INFO::~GAUSS_INFO()
1188      0.1815  malloc_consolidate
1169      0.1786  operator delete(void*)
1164      0.1778  sse_pulPoTf2L4(float**, PoTPlan*)
1121      0.1712  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
1075      0.1642  PulseProgressUnits(double, int)
997       0.1523  sse_pulPoTf3L8(float**, PoTPlan*)
908       0.1387  sse_pulPoTf2AL4(float**, PoTPlan*)
752       0.1149  sse_pulPoTf2L8(float**, PoTPlan*)
725       0.1107  __memmove_ssse3
615       0.0939  MFILE::~MFILE()
582       0.0889  MFILE::MFILE()
554       0.0846  sse_pulPoTf4(float**, PoTPlan*)
512       0.0782  GaussianProgressUnits()
498       0.0761  __memset_sse2
411       0.0628  receiver_config::receiver_config()
400       0.0611  sse_pulPoTf2(float**, PoTPlan*)
375       0.0573  analysis_config::analysis_config()
370       0.0565  t1bv_16
353       0.0539  result::result()
350       0.0535  T.9614
342       0.0522  sse_pulPoTf5L8(float**, PoTPlan*)
333       0.0509  data_description_t::data_description_t()
329       0.0503  workunit_grp::workunit_grp()
326       0.0498  sse_pulPoTf5(float**, PoTPlan*)
322       0.0492  gaussian::gaussian()
321       0.0490  cnvt_bin_hz(int, int)
269       0.0411  calc_detection_freq(double, double, double)
232       0.0354  splitter_config::splitter_config()
230       0.0351  tape::tape()
227       0.0347  workunit_header::workunit_header()
222       0.0339  finite
215       0.0328  q1bv_8
209       0.0319  GAUSS_INFO::GAUSS_INFO()
194       0.0296  sse_pulPoTf2AL8(float**, PoTPlan*)
192       0.0293  n1bv_128
192       0.0293  subband_description_t::subband_description_t()
190       0.0290  sse_pulPoTf5L4(float**, PoTPlan*)
175       0.0267  recorder_config::recorder_config()
172       0.0263  boinc_time_to_checkpoint
167       0.0255  T.9615
159       0.0243  apply
158       0.0241  T.9619
117       0.0179  boinc_fraction_done
116       0.0177  T.9610
114       0.0174  floor
56        0.0086  n1bv_64
53        0.0081  apply
52        0.0079  apply
44        0.0067  apply_dit
29        0.0044  SPIKE_INFO::~SPIKE_INFO()
27        0.0041  seti_analyze(ANALYSIS_STATE&)
16        0.0024  SpikeProgressUnits(int)
14        0.0021  apply_dif
13        0.0020  log10
12        0.0018  n2bv_64
11        0.0017  t2bv_64
9         0.0014  t2bv_32
6        9.2e-04  apply
6        9.2e-04  spike::spike()
5        7.6e-04  apply_before
5        7.6e-04  fftwf_cpy2d_ci
4        6.1e-04  fftwf_execute_dft
3        4.6e-04  __ieee754_log10
3        4.6e-04  apply_iter
3        4.6e-04  timer_handler()
2        3.1e-04  __nanosleep_nocancel
2        3.1e-04  fftwf_malloc
1        1.5e-04  GetPulsePoTLen(long, int*, int*)
1        1.5e-04  PULSE_INFO::~PULSE_INFO()
1        1.5e-04  SPIKE_INFO::SPIKE_INFO()
1        1.5e-04  ___printf_fp
1        1.5e-04  __libc_disable_asynccancel
1        1.5e-04  boinc_sleep(double)
1        1.5e-04  copy
1        1.5e-04  dtime()
1        1.5e-04  floorf
1        1.5e-04  gettimeofday
1        1.5e-04  memalign
1        1.5e-04  memcpy
1        1.5e-04  pulse::pulse()
1        1.5e-04  std::ostream::sentry::sentry(std::ostream&)
1        1.5e-04  t_funct(int, int, int)
1        1.5e-04  vfprintf
 
 
Sun Aug 14 19:14:42 CDT 2011
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted BR_MISS_PRED_RETIRED events (number of mispredicted branches retired (precise)) with a unit mask of 0x00 (No unit mask) count 10000
BR_MISS_PRED_R...|
  samples|      %|
------------------
    15792 97.2354 seti_boinc
      201  1.2376 libc-2.12.1.so
       85  0.5234 bash
       42  0.2586 libcairo.so.2.11000.0
       27  0.1662 ld-2.12.1.so
       18  0.1108 libglib-2.0.so.0.2600.1
       12  0.0739 libdbus-1.so.3.5.2
       11  0.0677 dbus-daemon
        8  0.0493 libgobject-2.0.so.0.2600.1
        5  0.0308 libpthread-2.12.1.so
        5  0.0308 libORBit-2.so.0.1.0
        4  0.0246 Xorg
        4  0.0246 boinc
	BR_MISS_PRED_R...|
	  samples|      %|
	------------------
	        3 75.0000 boinc
	        1 25.0000 [vdso] (tgid:935 range:0x3a4000-0x3a5000)
        3  0.0185 ophelp
        2  0.0123 dash
        2  0.0123 libpam.so.0.82.2
        2  0.0123 no-vmlinux
        2  0.0123 libgconf-2.so.4.1.5
        2  0.0123 libgdk-x11-2.0.so.0.2200.0
        1  0.0062 grep
        1  0.0062 libdl-2.12.1.so
        1  0.0062 libm-2.12.1.so
        1  0.0062 gnome-screensaver
        1  0.0062 sudo
        1  0.0062 libdbus-glib-1.so.2.1.0
        1  0.0062 gconfd-2
        1  0.0062 libgio-2.0.so.0.2600.1
        1  0.0062 libgtk-x11-2.0.so.0.2200.0
        1  0.0062 libnm-glib.so.2.4.1
        1  0.0062 libpulse-mainloop-glib.so.0.0.4
        1  0.0062 libwnck-1.so.22.3.30
        1  0.0062 libxcb.so.1.1.0
        1  0.0062 udisks-daemon
 
CPU: Intel Atom, speed 1795.65 MHz (estimated)
Counted BR_MISS_PRED_RETIRED events (number of mispredicted branches retired (precise)) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
3641     23.0560  f_GetTrueMean(float*, int, float, int, int)
1231      7.7951  GaussFit(float*, int, int)
841       5.3255  analyze_pot(float*, int, ChirpFftPair_t&)
822       5.2052  find_triplets(float const*, int, float, int, int)
763       4.8316  sse_pulPoTf2L4(float**, PoTPlan*)
736       4.6606  sse_pulPoTf2L8(float**, PoTPlan*)
686       4.3440  find_pulse(float const*, int, float, int, int)
629       3.9830  sse_pulPoTf2(float**, PoTPlan*)
557       3.5271  sse_pulPoTf2AL4(float**, PoTPlan*)
439       2.7799  sse_pulPoTf3(float**, PoTPlan*)
416       2.6342  sse_pulPoTf4L8(float**, PoTPlan*)
349       2.2100  _int_malloc
333       2.1087  _int_free
308       1.9504  sse_pulPoTf2u(float**, PoTPlan*)
303       1.9187  lcgf(double, double)
289       1.8300  float_to_uchar(float*, unsigned char*, long, float)
269       1.7034  GetFixedPoT(float*, int, int, float*, int, int)
227       1.4374  sse_pulPoTf3L8(float**, PoTPlan*)
227       1.4374  sse_pulPoTf4u(float**, PoTPlan*)
224       1.4184  sse_pulPoTf3u(float**, PoTPlan*)
204       1.2918  sse_pulPoTf5L8(float**, PoTPlan*)
195       1.2348  sse_pulPoTf2AL(float**, PoTPlan*)
181       1.1461  sse_pulPoTf5u(float**, PoTPlan*)
161       1.0195  sse_pulPoTf4(float**, PoTPlan*)
158       1.0005  sse_pulPoTf2AL8(float**, PoTPlan*)
147       0.9309  sse_pulPoTf5L4(float**, PoTPlan*)
145       0.9182  sse_pulPoTf2ALu(float**, PoTPlan*)
132       0.8359  sse_pulPoTf5(float**, PoTPlan*)
129       0.8169  __memmove_ssse3
128       0.8105  __memset_sse2
90        0.5699  time_to_ra_dec(double, double*, double*)
81        0.5129  f_GetChiSq(float*, int, int, float, float, float*, float*)
71        0.4496  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
66        0.4179  GAUSS_INFO::GAUSS_INFO()
66        0.4179  malloc
63        0.3989  FindSpikes(float*, int, int, SETI_WU_INFO&)
55        0.3483  malloc_consolidate
46        0.2913  t_funct(int, int, int)
39        0.2470  free
38        0.2406  checkpoint(unsigned char)
32        0.2026  operator new(unsigned int)
28        0.1773  __ieee754_log
27        0.1710  GAUSS_INFO::~GAUSS_INFO()
27        0.1710  __ieee754_pow
22        0.1393  t1bv_16
15        0.0950  apply
14        0.0887  apply
14        0.0887  apply_dit
13        0.0823  calc_detection_freq(double, double, double)
13        0.0823  gaussian::gaussian()
12        0.0760  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
12        0.0760  v_GetPowerSpectrum(float (*) [2], float*, int)
11        0.0697  t1bv_4
10        0.0633  log
6         0.0380  MFILE::~MFILE()
6         0.0380  q1bv_8
4         0.0253  apply
4         0.0253  t1bv_8
3         0.0190  fftwf_execute_dft
3         0.0190  memalign
3         0.0190  seti_analyze(ANALYSIS_STATE&)
2         0.0127  SPIKE_INFO::SPIKE_INFO()
2         0.0127  fftwf_cpy2d
2         0.0127  n2bv_64
2         0.0127  result::result()
2         0.0127  t2bv_4
1         0.0063  PULSE_INFO::~PULSE_INFO()
1         0.0063  PulseProgressUnits(double, int)
1         0.0063  SPIKE_INFO::~SPIKE_INFO()
1         0.0063  __ieee754_log10
1         0.0063  _int_memalign
1         0.0063  apply
1         0.0063  apply
1         0.0063  boinc_sleep(double)
1         0.0063  dtime()
1         0.0063  f_GetPeak(float*, int, int, float, float, float*)
1         0.0063  fftwf_cpy2d_ci
1         0.0063  n1bv_128
1         0.0063  t2bv_32
1         0.0063  t2bv_64
1         0.0063  t3bv_4
1         0.0063  timer_handler()
1         0.0063  timer_thread(void*)
1         0.0063  workunit_header::workunit_header()

```

### Atom Events ###

```
xbmc@atom:~/Documents/boinc/seti_boinc/client$ sudo opcontrol --list-events | more
oprofile: available events for CPU type "Intel Atom"

See Intel Architecture Developer's Manual Volume 3B, Appendix A and
Intel Architecture Optimization Reference Manual (730795-001)

CPU_CLK_UNHALTED: (counter: all)
	Clock cycles when not halted (min count: 6000) 
	Unit masks (default 0x0)
	----------
	0x00: core_p Core cycles when core is not halted 
	0x01: bus Bus cycles when core is not halted 
	0x02: no_other Bus cycles when core is active and the other is halted 
UNHALTED_REFERENCE_CYCLES: (counter: all)
	Unhalted reference cycles (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: No unit mask 
INST_RETIRED: (counter: all)
	number of instructions retired (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: No unit mask 
LLC_MISSES: (counter: all)
	Last level cache demand requests from this core that missed the LLC (min count: 6000) 
	Unit masks (default 0x41)
	----------
	0x41: No unit mask 
LLC_REFS: (counter: all)
	Last level cache demand requests from this core (min count: 6000) 
	Unit masks (default 0x4f)
	----------
	0x4f: No unit mask 
BR_INST_RETIRED: (counter: all)
	number of branch instructions retired (min count: 500) 
	Unit masks (default 0x0)
	----------
	0x00: any Retired branch instructions 
	0x01: pred_not_taken Retired branch instructions that were predicted not-taken 
	0x02: mispred_not_taken Retired branch instructions that were mispredicted not-taken 
	0x04: pred_taken Retired branch instructions that were predicted taken 
	0x08: mispred_taken Retired branch instructions that were mispredicted taken 
	0x0a: mispred Retired mispredicted branch instructions (precise event) 
	0x0c: taken Retired taken branch instructions 
	0x0f: any1 Retired branch instructions 
BR_MISS_PRED_RETIRED: (counter: all)
	number of mispredicted branches retired (precise) (min count: 500) 
STORE_FORWARDS: (counter: all)
	Good store forwards (min count: 6000) 
	Unit masks (default 0x81)
	----------
	0x81: good Good store forwards 
SEGMENT_REG_LOADS: (counter: all)
	Number of segment register loads (min count: 6000) 
	Unit masks (default 0x0)
	----------
	0x00: any Number of segment register loads 
PREFETCH: (counter: all)
	Streaming SIMD Extensions (SSE) Prefetch instructions executed (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: prefetcht0 Streaming SIMD Extensions (SSE) PrefetchT0 instructions executed 
	0x06: sw_l2 Streaming SIMD Extensions (SSE) PrefetchT1 and PrefetchT2 instructions executed 
	0x08: prefetchnta Streaming SIMD Extensions (SSE) Prefetch NTA instructions executed 
DATA_TLB_MISSES: (counter: all)
	Memory accesses that missed the DTLB (min count: 6000) 
	Unit masks (default 0x7)

	0x07: dtlb_miss Memory accesses that missed the DTLB 
	0x05: dtlb_miss_ld DTLB misses due to load operations 
	0x09: l0_dtlb_miss_ld L0_DTLB misses due to load operations 
	0x06: dtlb_miss_st DTLB misses due to store operations 
PAGE_WALKS: (counter: all)
	Page walks (min count: 6000) 
	Unit masks (default 0x3)
	----------
	0x03: walks Number of page-walks executed 
	0x03: cycles Duration of page-walks in core cycles 
X87_COMP_OPS_EXE: (counter: all)
	Floating point computational micro-ops (min count: 6000) 
	Unit masks (default 0x81)
	----------
	0x01: s Floating point computational micro-ops executed 
	0x81: ar Floating point computational micro-ops retired 
FP_ASSIST: (counter: all)
	Floating point assists (min count: 6000) 
	Unit masks (default 0x81)
	----------
	0x81: ar Floating point assists 
MUL: (counter: all)
	Multiply operations (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: s Multiply operations executed 
	0x81: ar Multiply operations retired 
DIV: (counter: all)
	Divide operations (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: s Divide operations executed 
	0x81: ar Divide operations retired 
CYCLES_DIV_BUSY: (counter: all)
	Cycles the driver is busy (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: No unit mask 
CORE: (counter: all)
	Cycles L2 address bus is in use (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
L2_DBUS_BUSY: (counter: all)
	Cycles the L2 cache data bus is busy (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
L2_LINES_IN: (counter: all)
	L2 cache misses (min count: 500) 
	Unit masks (default 0x1e0)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x60: all All inclusive 
	0x20: hw Hardware prefetch only 
	0x00: exclude_hw Exclude hardware prefetch 
L2_M_LINES_IN: (counter: all)
	L2 cache line modifications (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
L2_LINES_OUT: (counter: all)
	L2 cache lines evicted (min count: 500) 
	Unit masks (default 0x1e0)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x60: all All inclusive 
	0x20: hw Hardware prefetch only 
	0x00: exclude_hw Exclude hardware prefetch 
L2_M_LINES_OUT: (counter: all)
	Modified lines evicted from the L2 cache (min count: 500) 
	Unit masks (default 0x1e0)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x60: all All inclusive 
	0x20: hw Hardware prefetch only 
	0x00: exclude_hw Exclude hardware prefetch 
L2_IFETCH: (counter: all)
	L2 cacheable instruction fetch requests (min count: 6000) 
	Unit masks (default 0x18f)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
L2_LD: (counter: all)
	L2 cache reads (min count: 6000) 
	Unit masks (default 0x1ef)
	----------
	0x180: all All cores. 
	0x80: this This Core.
	0x60: all All inclusive 
	0x20: hw Hardware prefetch only 
	0x00: exclude_hw Exclude hardware prefetch 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
L2_ST: (counter: all)
	L2 store requests (min count: 6000) 
	Unit masks (default 0x18f)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
L2_LOCK: (counter: all)
	L2 locked accesses (min count: 6000) 
	Unit masks (default 0x18f)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
L2_RQSTS: (counter: all)
	L2 cache requests (min count: 6000) 
	Unit masks (default 0x1ef)
	----------
	0x41: i_state L2 cache demand requests from this core that missed the L2 
	0x4f: mesi L2 cache demand requests from this core 

	0x180: all All cores. 
	0x80: this This Core. 
	0x60: all All inclusive 
	0x20: hw Hardware prefetch only 
	0x00: exclude_hw Exclude hardware prefetch 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
L2_REJECT_BUSQ: (counter: all)
	Rejected L2 cache requests (min count: 500) 
	Unit masks (default 0x1ef)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x60: all All inclusive 
	0x20: hw Hardware prefetch only 
	0x00: exclude_hw Exclude hardware prefetch 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
L2_NO_REQ: (counter: all)
	Cycles no L2 cache requests are pending (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
EIST_TRANS: (counter: all)
	Number of Enhanced Intel SpeedStep(R) Technology (EIST) transitions (min count: 6000) 
THERMAL_TRIP: (counter: all)
	Number of thermal trips (min count: 6000) 
	Unit masks (default 0xc0)
	----------
	0xc0: thermal_trip Number of thermal trips. 
L1D_CACHE: (counter: all)
	L1d Cache accesses (min count: 6000) 
	Unit masks (default 0x21)
	----------
	0x21: ld L1 Cacheable Data Reads 
	0x22: st L1 Cacheable Data Writes 
BUS_REQUEST_OUTSTANDING: (counter: all)
	Outstanding cacheable data read bus requests duration (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_BNR_DRV: (counter: all)
	Number of Bus Not Ready signals asserted (min count: 6000) 
	Unit masks (default 0x0)
	----------
	0x00: this This agent 
	0x40: any Include any agents 
BUS_DRDY_CLOCKS: (counter: all)
	Bus cycles when data is sent on the bus (min count: 6000) 
	Unit masks (default 0x0)
	----------
	0x00: this This agent 
	0x40: any Include any agents 
BUS_LOCK_CLOCKS: (counter: all)
	Bus cycles when a LOCK signal is asserted. (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_DATA_RCV: (counter: all)
	Bus cycles while processor receives data (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
BUS_TRANS_BRD: (counter: all)
	Burst read bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_RFO: (counter: all)
	RFO bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_WB: (counter: all)
	Explicit writeback bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents
BUS_TRANS_IFETCH: (counter: all)
	Instruction-fetch bus transactions. (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_INVAL: (counter: all)
	Invalidate bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_PWR: (counter: all)
	Partial write bus transaction. (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_P: (counter: all)
	Partial bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_IO: (counter: all)

	IO bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_DEF: (counter: all)
	Deferred bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_BURST: (counter: all)
	Burst (full cache-line) bus transactions. (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_MEM: (counter: all)
	Memory bus transactions (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_TRANS_ANY: (counter: all)
	All bus transactions (min count: 500)
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
EXT_SNOOP: (counter: all)
	External snoops (min count: 500) 
	Unit masks (default 0x18f)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x08: modified Counts modified state 
	0x04: exclusive Counts exclusive state 
	0x02: shared Counts shared state 
	0x01: invalid Counts invalid state 
BUS_HIT_DRV: (counter: all)
	HIT signal asserted (min count: 500) 
	Unit masks (default 0x0)
	----------
	0x00: this This agent 
	0x40: any Include any agents 
BUS_HITM_DRV: (counter: all)
	HITM signal asserted (min count: 500) 
	Unit masks (default 0x0)
	----------
	0x00: this This agent 
	0x40: any Include any agents 
BUSQ_EMPTY: (counter: all)
	Bus queue is empty (min count: 500) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores.

	0x80: this This Core. 
SNOOP_STALL_DRV: (counter: all)
	Bus stalled for snoops (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
	0x00: this This agent 
	0x40: any Include any agents 
BUS_IO_WAIT: (counter: all)
	IO requests waiting in the bus queue (min count: 6000) 
	Unit masks (default 0x180)
	----------
	0x180: all All cores. 
	0x80: this This Core. 
ICACHE: (counter: all)
	Instruction cache accesses (min count: 6000) 
	Unit masks (default 0x3)
	----------
	0x03: accesses Instruction fetches 
	0x02: misses Icache miss 
ITLB: (counter: all)
	ITLB events (min count: 6000) 
	Unit masks (default 0x4)
	----------
	0x04: flush ITLB flushes 
	0x02: misses ITLB misses 
MACRO_INSTS: (counter: all)
	instructions decoded (min count: 6000) 
	Unit masks (default 0x3)
	----------
	0x02: cisc_decoded CISC macro instructions decoded 
	0x03: all_decoded All Instructions decoded

SIMD_UOPS_EXEC: (counter: all)
	SIMD micro-ops executed (min count: 6000) 
	Unit masks (default 0x80)
	----------
	0x00: s SIMD micro-ops executed (excluding stores) 
	0x80: ar SIMD micro-ops retired (excluding stores) 
SIMD_SAT_UOP_EXEC: (counter: all)
	SIMD saturated arithmetic micro-ops executed (min count: 6000) 
	Unit masks (default 0x0)
	----------
	0x00: s SIMD saturated arithmetic micro-ops executed 
	0x80: ar SIMD saturated arithmetic micro-ops retired 
SIMD_UOP_TYPE_EXEC: (counter: all)
	SIMD packed microops executed (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: s SIMD packed multiply microops executed 
	0x81: ar SIMD packed multiply microops retired 
	0x02: s SIMD packed shift micro-ops executed 
	0x82: ar SIMD packed shift micro-ops retired 
	0x04: s SIMD pack micro-ops executed 
	0x84: ar SIMD pack micro-ops retired 
	0x08: s SIMD unpack micro-ops executed 
	0x88: ar SIMD unpack micro-ops retired 
	0x10: s SIMD packed logical microops executed 
	0x90: ar SIMD packed logical microops retired 
	0x20: s SIMD packed arithmetic micro-ops executed 
	0xa0: ar SIMD packed arithmetic micro-ops retired 
UOPS_RETIRED: (counter: all)
	Micro-ops retired (min count: 6000) 
	Unit masks (default 0x10)
	----------
	0x10: any Micro-ops retired

MACHINE_CLEARS: (counter: all)
	Self-Modifying Code detected (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: No unit mask 
CYCLES_INT_MASKED: (counter: all)
	Cycles during which interrupts are disabled (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: cycles_int_masked Cycles during which interrupts are disabled 
	0x02: cycles_int_pending_and_masked Cycles during which interrupts are pending and disabled 
SIMD_INST_RETIRED: (counter: all)
	Retired Streaming SIMD Extensions (SSE) instructions (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: packed_single Retired Streaming SIMD Extensions (SSE) packed-single instructions 
	0x02: scalar_single Retired Streaming SIMD Extensions (SSE) scalar-single instructions 
	0x04: packed_double Retired Streaming SIMD Extensions 2 (SSE2) packed-double instructions 
	0x08: scalar_double Retired Streaming SIMD Extensions 2 (SSE2) scalar-double instructions 
	0x10: vector Retired Streaming SIMD Extensions 2 (SSE2) vector instructions 
	0x1f: any Retired Streaming SIMD instructions 
HW_INT_RCV: (counter: all)
	Hardware interrupts received (min count: 6000) 
SIMD_COMP_INST_RETIRED: (counter: all)
	Retired computational Streaming SIMD Extensions (SSE) instructions. (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: packed_single Retired computational Streaming SIMD Extensions (SSE) packed-single 
              instructions 
	0x02: scalar_single Retired computational Streaming SIMD Extensions (SSE) scalar-single 
              instructions 
	0x04: packed_double Retired computational Streaming SIMD Extensions 2 (SSE2) packed-double 
              instructions

	Retired computational Streaming SIMD Extensions (SSE) instructions. (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: packed_single Retired computational Streaming SIMD Extensions (SSE) packed-single 
              instructions 
	0x02: scalar_single Retired computational Streaming SIMD Extensions (SSE) scalar-single 
              instructions 
	0x04: packed_double Retired computational Streaming SIMD Extensions 2 (SSE2) packed-double 
              instructions 
	0x08: scalar_double Retired computational Streaming SIMD Extensions 2 (SSE2) scalar-double 
              instructions 
MEM_LOAD_RETIRED: (counter: all)
	Retired loads (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: l2_hit Retired loads that hit the L2 cache (precise event) 
	0x02: l2_miss Retired loads that miss the L2 cache (precise event) 
	0x04: dtlb_miss Retired loads that miss the DTLB (precise event) 
SIMD_ASSIST: (counter: all)
	SIMD assists invoked (min count: 6000) 
SIMD_INSTR_RETIRED: (counter: all)
	SIMD Instructions retired (min count: 6000) 
SIMD_SAT_INSTR_RETIRED: (counter: all)
	Saturated arithmetic instructions retired (min count: 6000) 
BR_INST_DECODED: (counter: all)
	Branch instructions decoded (min count: 6000) 
BOGUS_BR: (counter: all)
	Bogus branches (min count: 6000) 
BACLEARS: (counter: all)
	BACLEARS asserted (min count: 6000) 
	Unit masks (default 0x1)
	----------
	0x01: No unit mask 


```