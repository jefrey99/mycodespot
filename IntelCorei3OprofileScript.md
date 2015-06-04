# This script was used to profile SETI at home on x86 (Nehalem) #

```
#!/bin/bash
SleepSeconds=100 

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
date >> Nehalem_Timer_Mode.txt
sudo opreport >> Nehalem_Timer_Mode.txt
echo " " >> Nehalem_Timer_Mode.txt
sudo opreport -l /home/jeff/stuff/seti_boinc/client/seti_boinc >> Nehalem_Timer_Mode.txt
sudo opcontrol --shutdown

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
date >> Nehalem_INST_RETIRED.txt
sudo opreport >> Nehalem_INST_RETIRED.txt
echo " " >> Nehalem_INST_RETIRED.txt
sudo opreport -l /home/jeff/stuff/seti_boinc/client/seti_boinc >> Nehalem_INST_RETIRED.txt
sudo opcontrol --shutdown

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
date >> Nehalem_LLC_MISSES.txt
sudo opreport >> Nehalem_LLC_MISSES.txt
echo " " >> Nehalem_LLC_MISSES.txt
sudo opreport -l /home/jeff/stuff/seti_boinc/client/seti_boinc >> Nehalem_LLC_MISSES.txt
sudo opcontrol --shutdown

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
date >> Nehalem_LLC_REFS.txt
sudo opreport >> Nehalem_LLC_REFS.txt
echo " " >> Nehalem_LLC_REFS.txt
sudo opreport -l /home/jeff/stuff/seti_boinc/client/seti_boinc >> Nehalem_LLC_REFS.txt
sudo opcontrol --shutdown

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
date >> Nehalem_BR_INST_RETIRED.txt
sudo opreport >> Nehalem_BR_INST_RETIRED.txt
echo " " >> Nehalem_BR_INST_RETIRED.txt
sudo opreport -l /home/jeff/stuff/seti_boinc/client/seti_boinc >> Nehalem_BR_INST_RETIRED.txt
sudo opcontrol --shutdown

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
date >> Nehalem_BR_MISS_PRED_RETIRED.txt
sudo opreport >> Nehalem_BR_MISS_PRED_RETIRED.txt
echo " " >> Nehalem_BR_MISS_PRED_RETIRED.txt
sudo opreport -l /home/jeff/stuff/seti_boinc/client/seti_boinc >> Nehalem_BR_MISS_PRED_RETIRED.txt
sudo opcontrol --shutdown
```


### Intel Core i3 - SETI@Home - Timer Mode ###
```
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted CPU_CLK_UNHALTED events (Clock cycles when not halted) with a unit mask of 0x00 (No unit mask) count 100000
CPU_CLK_UNHALT...|
  samples|      %|
------------------
  2083406 96.3701 seti_boinc
    56696  2.6225 no-vmlinux
     5091  0.2355 oprofiled
     2684  0.1242 python2.6
     1927  0.0891 libglib-2.0.so.0.2600.0
     1772  0.0820 libc-2.12.1.so
     1087  0.0503 Xorg
      929  0.0430 libcairo.so.2.11000.0
      808  0.0374 libgobject-2.0.so.0.2600.0
      734  0.0340 libpthread-2.12.1.so
      629  0.0291 libgdk-x11-2.0.so.0.2200.0
      621  0.0287 libdrm_intel.so.1.0.0
      569  0.0263 libgtk-x11-2.0.so.0.2200.0
      449  0.0208 ld-2.12.1.so
      435  0.0201 bash
      403  0.0186 i965_dri.so
      387  0.0179 libdbus-1.so.3.5.2
      328  0.0152 intel_drv.so
      310  0.0143 mysqld
      303  0.0140 libX11.so.6.3.0
      228  0.0105 libpangoft2-1.0.so.0.2800.1
      218  0.0101 libpango-1.0.so.0.2800.1
      195  0.0090 libxcb.so.1.1.0
      194  0.0090 libpixman-1.so.0.18.4
      140  0.0065 compiz
       91  0.0042 libfade.so
       86  0.0040 dbus-daemon
       81  0.0037 _glib.so
       65  0.0030 libgthread-2.0.so.0.2600.0
       53  0.0025 libpyglib-2.0-python2.6.so.0.0.0
       51  0.0024 libGL.so.1.2
       47  0.0022 libgdk_pixbuf-2.0.so.0.2200.0
       37  0.0017 libm-2.12.1.so
       34  0.0016 libpangocairo-1.0.so.0.2800.1
       32  0.0015 librt-2.12.1.so
       32  0.0015 libXrender.so.1.3.0
       31  0.0014 libgtksourceview-2.0.so.0.0.0
       31  0.0014 libfb.so
       30  0.0014 libdbus-glib-1.so.2.1.0
       29  0.0013 libdecoration.so
       29  0.0013 libexpo.so
       27  0.0012 evdev_drv.so
       26  0.0012 libvte.so.9.2600.0
       24  0.0011 libgio-2.0.so.0.2600.0
       23  0.0011 libanimation.so
       23  0.0011 libwall.so
       21 9.7e-04 _gtk.so
       17 7.9e-04 libdrm.so.2.4.0
       17 7.9e-04 libudev.so.0.9.1
       17 7.9e-04 libmurrine.so
       17 7.9e-04 libwnck-1.so.22.3.30
       17 7.9e-04 _gobject.so
       16 7.4e-04 libstaticswitcher.so
       16 7.4e-04 libdri2.so
       13 6.0e-04 libXfixes.so.3.1.0
       13 6.0e-04 libextmod.so
       12 5.6e-04 gedit
       12 5.6e-04 libezoom.so
       11 5.1e-04 libresizeinfo.so
       11 5.1e-04 libscale.so
       11 5.1e-04 libORBit-2.so.0.1.0
       10 4.6e-04 libworkarounds.so
       10 4.6e-04 libgnome-keyring.so.0.1.1
        9 4.2e-04 libsvg.so
        9 4.2e-04 libXdamage.so.1.1.0
        9 4.2e-04 libcompizconfig.so.0.0.0
        9 4.2e-04 libgvfscommon.so.0.0.0
        8 3.7e-04 grep
        8 3.7e-04 libpam.so.0.82.2
        8 3.7e-04 apache2
        8 3.7e-04 libXext.so.6.4.0
        8 3.7e-04 libmetacity-private.so.0.0.0
        7 3.2e-04 gawk
        7 3.2e-04 libresize.so
        7 3.2e-04 libscaleaddon.so
        7 3.2e-04 libusbmuxd.so.1.0.4
        7 3.2e-04 rsyslogd
        6 2.8e-04 libmove.so
        6 2.8e-04 libplace.so
        6 2.8e-04 libsnap.so
        6 2.8e-04 libavahi-common.so.3.5.2
        6 2.8e-04 libstartup-notification-1.so.0.0.0
        5 2.3e-04 libpcre.so.3.12.1
        5 2.3e-04 pango-basic-fc.so
        4 1.9e-04 libapr-1.so.0.4.2
        3 1.4e-04 libccp.so
        3 1.4e-04 libsession.so
        3 1.4e-04 libgconf.so
        3 1.4e-04 libavahi-core.so.7.0.0
        3 1.4e-04 libnm-glib.so.2.4.1
        3 1.4e-04 udisks-daemon
        3 1.4e-04 NetworkManager
        2 9.3e-05 dash
        2 9.3e-05 ls
        2 9.3e-05 mkdir
        2 9.3e-05 libneg.so
        2 9.3e-05 libvpswitch.so
        2 9.3e-05 libbonobo-2.so.0.0.0
        2 9.3e-05 libnm-util.so.1.6.0
        2 9.3e-05 libxklavier.so.16.0.0
        2 9.3e-05 upowerd
        2 9.3e-05 nullmailer-send
        1 4.6e-05 libcrypto.so.0.9.8
        1 4.6e-05 libdl-2.12.1.so
        1 4.6e-05 libresolv-2.12.1.so
        1 4.6e-05 pam_limits.so
        1 4.6e-05 pam_unix.so
        1 4.6e-05 gnome-panel
        1 4.6e-05 gnome-power-manager
        1 4.6e-05 id
        1 4.6e-05 sudo
        1 4.6e-05 libregex.so
        1 4.6e-05 liba11y-keyboard.so
        1 4.6e-05 libmedia-keys.so
        1 4.6e-05 im-ibus.so
        1 4.6e-05 libXi.so.6.1.0
        1 4.6e-05 libappindicator.so.1.0.0
        1 4.6e-05 libgconf-2.so.4.1.5
        1 4.6e-05 libpulse-mainloop-glib.so.0.0.4
        1 4.6e-05 imklog.so
        1 4.6e-05 cron
 
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted CPU_CLK_UNHALTED events (Clock cycles when not halted) with a unit mask of 0x00 (No unit mask) count 100000
samples  %        symbol name
263549   12.6506  n1bv_128
210418   10.1002  f_GetChiSq(float*, int, int, float, float, float*, float*)
182507    8.7605  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
159554    7.6587  GaussFit(float*, int, int)
146171    7.0163  GetFixedPoT(float*, int, int, float*, int, int)
125029    6.0015  lcgf(double, double)
113552    5.4506  analyze_pot(float*, int, ChirpFftPair_t&)
86503     4.1522  FindSpikes(float*, int, int, SETI_WU_INFO&)
76121     3.6539  f_GetPeak(float*, int, int, float, float, float*)
75270     3.6130  f_GetTrueMean(float*, int, float, int, int)
67268     3.2289  t1bv_8
66688     3.2011  t2bv_32
43793     2.1021  float_to_uchar(float*, unsigned char*, long, float)
42073     2.0195  __ieee754_log
39151     1.8793  v_GetPowerSpectrum(float (*) [2], float*, int)
38929     1.8686  t3bv_4
27435     1.3169  find_pulse(float const*, int, float, int, int)
25654     1.2314  __ieee754_pow
23923     1.1483  t1bv_16
21257     1.0204  foldArrayBy2LO(float**, PoTPlan*)
21156     1.0155  find_triplets(float const*, int, float, int, int)
15461     0.7421  t2bv_64
13487     0.6474  isnan
12516     0.6008  _int_malloc
11764     0.5647  foldArrayBy5LO(float**, PoTPlan*)
11754     0.5642  foldArrayBy4(float**, PoTPlan*)
11716     0.5624  malloc
10209     0.4900  foldArrayBy3(float**, PoTPlan*)
9966      0.4784  foldArrayBy4LO(float**, PoTPlan*)
9898      0.4751  foldArrayBy3LO(float**, PoTPlan*)
8777      0.4213  free
8410      0.4037  t1bv_4
8392      0.4028  foldArrayBy5(float**, PoTPlan*)
8140      0.3907  pow
7811      0.3749  n2bv_64
7708      0.3700  foldArrayBy2A(float**, PoTPlan*)
6160      0.2957  log
5496      0.2638  PulseProgressUnits(double, int)
4585      0.2201  fraction_done(double, double)
4119      0.1977  t1bv_32
4000      0.1920  _int_free
3577      0.1717  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
3540      0.1699  time_to_ra_dec(double, double*, double*)
3527      0.1693  malloc_consolidate
3167      0.1520  foldArrayBy2AL(float**, PoTPlan*)
2369      0.1137  floor
1662      0.0798  analysis_config::analysis_config()
1628      0.0781  checkpoint(unsigned char)
1564      0.0751  operator new(unsigned int)
1371      0.0658  boinc_fraction_done
1217      0.0584  t_funct(int, int, int)
1194      0.0573  gaussian::gaussian()
1152      0.0553  finite
1110      0.0533  n2bv_32
1108      0.0532  t2bv_16
1098      0.0527  result::result()
1090      0.0523  cnvt_bin_hz(int, int)
1065      0.0511  workunit_grp::workunit_grp()
1044      0.0501  operator delete(void*)
898       0.0431  TripletProgressUnits()
836       0.0401  __i686.get_pc_thunk.bx
813       0.0390  workunit_header::workunit_header()
811       0.0389  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
666       0.0320  calc_detection_freq(double, double, double)
617       0.0296  splitter_config::splitter_config()
599       0.0288  __memmove_ssse3_rep
598       0.0287  apply
592       0.0284  data_description_t::data_description_t()
510       0.0245  GaussianProgressUnits()
498       0.0239  receiver_config::receiver_config()
476       0.0228  __memset_sse2_rep
474       0.0228  tape::tape()
453       0.0217  GAUSS_INFO::~GAUSS_INFO()
429       0.0206  T.9614
408       0.0196  MFILE::MFILE()
396       0.0190  apply
371       0.0178  MFILE::~MFILE()
370       0.0178  subband_description_t::subband_description_t()
337       0.0162  apply_dit
268       0.0129  recorder_config::recorder_config()
267       0.0128  boinc_time_to_checkpoint
264       0.0127  T.9619
257       0.0123  seti_analyze(ANALYSIS_STATE&)
239       0.0115  GAUSS_INFO::GAUSS_INFO()
236       0.0113  T.9615
228       0.0109  apply
224       0.0108  T.9610
191       0.0092  t2bv_8
180       0.0086  __ieee754_log10
162       0.0078  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
118       0.0057  fftwf_execute_dft
115       0.0055  SpikeProgressUnits(int)
106       0.0051  spike::spike()
59        0.0028  SPIKE_INFO::SPIKE_INFO()
54        0.0026  log10
48        0.0023  SPIKE_INFO::~SPIKE_INFO()
35        0.0017  _int_memalign
29        0.0014  memalign
28        0.0013  pulse::pulse()
21        0.0010  __nanosleep_nocancel
19       9.1e-04  _dl_sysinfo_int80
18       8.6e-04  timer_handler()
13       6.2e-04  floorf
9        4.3e-04  PULSE_INFO::~PULSE_INFO()
8        3.8e-04  boinc_sleep(double)
8        3.8e-04  fftwf_kernel_malloc
8        3.8e-04  invert_lcgf(float, float, float)
7        3.4e-04  GetPulsePoTLen(long, int*, int*)
7        3.4e-04  gettimeofday
7        3.4e-04  worker_signal_handler(int)
6        2.9e-04  PULSE_INFO::PULSE_INFO()
6        2.9e-04  __libc_disable_asynccancel
6        2.9e-04  fftwf_free
6        2.9e-04  fftwf_malloc
6        2.9e-04  result_group_start()
4        1.9e-04  __restore
4        1.9e-04  calloc_a(unsigned int, unsigned int, unsigned int)
4        1.9e-04  dtime()
3        1.4e-04  ChirpProgressUnits()
3        1.4e-04  fftwf_kernel_free
3        1.4e-04  plan_PulsePoT(PoTPlan*, int, float*, int*)
3        1.4e-04  usleep
2        9.6e-05  free_a(void*)
2        9.6e-05  getrusage
2        9.6e-05  malloc_a(unsigned int, unsigned int)
1        4.8e-05  nanosleep
```
### Intel Core i3 - SETI@Home - INST\_RETIRED ###
```
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted INST_RETIRED events (number of instructions retired) with a unit mask of 0x00 (No unit mask) count 10000
INST_RETIRED:1...|
  samples|      %|
------------------
  8591624 94.8216 seti_boinc
   264423  2.9183 oprofiled
    61199  0.6754 libc-2.12.1.so
    38607  0.4261 bash
    13728  0.1515 libcairo.so.2.11000.0
    12507  0.1380 libdrm_intel.so.1.0.0
    11867  0.1310 libglib-2.0.so.0.2600.0
     8774  0.0968 libpixman-1.so.0.18.4
     7269  0.0802 libpthread-2.12.1.so
     7161  0.0790 Xorg
     5730  0.0632 libgobject-2.0.so.0.2600.0
     4124  0.0455 python2.6
     3568  0.0394 libgdk-x11-2.0.so.0.2200.0
     3549  0.0392 ld-2.12.1.so
     2916  0.0322 intel_drv.so
     2518  0.0278 libvte.so.9.2600.0
     2348  0.0259 libgdk_pixbuf-2.0.so.0.2200.0
     2204  0.0243 libpangoft2-1.0.so.0.2800.1
     2196  0.0242 i965_dri.so
     1902  0.0210 mysqld
     1549  0.0171 libgtk-x11-2.0.so.0.2200.0
     1228  0.0136 libdbus-1.so.3.5.2
      997  0.0110 dbus-daemon
      971  0.0107 librsvg-2.so.2.32.0
      838  0.0092 libmurrine.so
      628  0.0069 libpcre.so.3.12.1
      616  0.0068 libX11.so.6.3.0
      593  0.0065 no-vmlinux
      415  0.0046 libxml2.so.2.7.7
      400  0.0044 libxcb.so.1.1.0
      395  0.0044 compiz
      366  0.0040 libpango-1.0.so.0.2800.1
      321  0.0035 ls
      287  0.0032 libgio-2.0.so.0.2600.0
      284  0.0031 libgthread-2.0.so.0.2600.0
      233  0.0026 libm-2.12.1.so
      184  0.0020 gawk
      145  0.0016 libexpo.so
      128  0.0014 libanimation.so
      107  0.0012 libICE.so.6.3.0
      100  0.0011 libXrender.so.1.3.0
       86 9.5e-04 dash
       84 9.3e-04 libGL.so.1.2
       80 8.8e-04 evdev_drv.so
       77 8.5e-04 libpangocairo-1.0.so.0.2800.1
       76 8.4e-04 libdecoration.so
       74 8.2e-04 libfade.so
       65 7.2e-04 libavahi-common.so.3.5.2
       63 7.0e-04 libdbus-glib-1.so.2.1.0
       57 6.3e-04 libfb.so
       52 5.7e-04 libpyglib-2.0-python2.6.so.0.0.0
       52 5.7e-04 libwnck-1.so.22.3.30
       52 5.7e-04 _glib.so
       49 5.4e-04 libextmod.so
       45 5.0e-04 libORBit-2.so.0.1.0
       44 4.9e-04 sed
       44 4.9e-04 libmetacity-private.so.0.0.0
       41 4.5e-04 libpam.so.0.82.2
       40 4.4e-04 libscale.so
       33 3.6e-04 rsyslogd
       32 3.5e-04 grep
       32 3.5e-04 libresize.so
       30 3.3e-04 libwall.so
       27 3.0e-04 librt-2.12.1.so
       27 3.0e-04 libstaticswitcher.so
       26 2.9e-04 libz.so.1.2.3.4
       26 2.9e-04 sudo
       26 2.9e-04 libmove.so
       25 2.8e-04 libpng12.so.0.44.0
       24 2.6e-04 pango-basic-fc.so
       22 2.4e-04 libgvfscommon.so.0.0.0
       21 2.3e-04 ophelp
       19 2.1e-04 libfreetype.so.6.6.0
       18 2.0e-04 libncurses.so.5.7
       18 2.0e-04 gnome-panel
       18 2.0e-04 libresizeinfo.so
       17 1.9e-04 libstartup-notification-1.so.0.0.0
       16 1.8e-04 libdrm.so.2.4.0
       16 1.8e-04 libavahi-core.so.7.0.0
       15 1.7e-04 libezoom.so
       13 1.4e-04 libsvg.so
       13 1.4e-04 libXfixes.so.3.1.0
       11 1.2e-04 gnome-terminal
       11 1.2e-04 libneg.so
       11 1.2e-04 libdri2.so
        9 9.9e-05 libxklavier.so.16.0.0
        9 9.9e-05 _gtk.so
        8 8.8e-05 gtk-window-decorator
        8 8.8e-05 libfilebrowser.so
        8 8.8e-05 libpixmap.so
        8 8.8e-05 libgnome-keyring.so.0.1.1
        8 8.8e-05 _gobject.so
        7 7.7e-05 libscaleaddon.so
        7 7.7e-05 libworkarounds.so
        7 7.7e-05 libXi.so.6.1.0
        7 7.7e-05 NetworkManager
        6 6.6e-05 libregex.so
        6 6.6e-05 libupower-glib.so.1.0.1
        4 4.4e-05 libdl-2.12.1.so
        4 4.4e-05 dircolors
        4 4.4e-05 libplace.so
        4 4.4e-05 libsession.so
        4 4.4e-05 libapr-1.so.0.4.2
        3 3.3e-05 libgcrypt.so.11.5.3
        3 3.3e-05 libudev.so.0.9.1
        3 3.3e-05 gnome-session
        3 3.3e-05 libccp.so
        3 3.3e-05 libgconf-2.so.4.1.5
        3 3.3e-05 libnm-util.so.1.6.0
        3 3.3e-05 _dbus_bindings.so
        2 2.2e-05 libnss_compat-2.12.1.so
        2 2.2e-05 libnss_files-2.12.1.so
        2 2.2e-05 libselinux.so.1
        2 2.2e-05 nm-applet
        2 2.2e-05 apache2
        2 2.2e-05 libdbus.so
        2 2.2e-05 libsnap.so
        2 2.2e-05 libvpswitch.so
        2 2.2e-05 liba11y-keyboard.so
        2 2.2e-05 libcanberra-gtk-module.so
        2 2.2e-05 libXdamage.so.1.1.0
        2 2.2e-05 libbonobo-2.so.0.0.0
        2 2.2e-05 libcompizconfig.so.0.0.0
        2 2.2e-05 libdbusmenu-glib.so.1.0.17
        2 2.2e-05 libnm-glib.so.2.4.1
        2 2.2e-05 libpanel-applet-2.so.0.2.68
        2 2.2e-05 libpulse-mainloop-glib.so.0.0.4
        2 2.2e-05 notify-osd
        2 2.2e-05 upowerd
        1 1.1e-05 cat
        1 1.1e-05 libattr.so.1.1.0
        1 1.1e-05 libnih.so.1.0.0
        1 1.1e-05 libpopt.so.0.0.0
        1 1.1e-05 init
        1 1.1e-05 gnome-power-manager
        1 1.1e-05 seq
        1 1.1e-05 ssh-agent
        1 1.1e-05 libgnomecompat.so
        1 1.1e-05 libmousepoll.so
        1 1.1e-05 libgconf.so
        1 1.1e-05 libpixbufloader-png.so
        1 1.1e-05 wnck-applet
        1 1.1e-05 indicator-session-service
        1 1.1e-05 libGLU.so.1.3.070900
        1 1.1e-05 libXcursor.so.1.0.2
        1 1.1e-05 libXext.so.6.4.0
        1 1.1e-05 libXrandr.so.2.2.0
        1 1.1e-05 libnl.so.1.1
        1 1.1e-05 libpulsecommon-0.9.21.so
        1 1.1e-05 libstdc++.so.6.0.14
        1 1.1e-05 libusbmuxd.so.1.0.4
        1 1.1e-05 udisks-daemon
        1 1.1e-05 libdbe.so
        1 1.1e-05 cron
        1 1.1e-05 nullmailer-send
 
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted INST_RETIRED events (number of instructions retired) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
806103    9.3366  f_GetTrueMean(float*, int, float, int, int)
717897    8.3150  GaussFit(float*, int, int)
708868    8.2104  n1bv_128
672225    7.7860  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
601850    6.9709  f_GetPeak(float*, int, int, float, float, float*)
590862    6.8436  FindSpikes(float*, int, int, SETI_WU_INFO&)
436156    5.0518  lcgf(double, double)
401338    4.6485  t1bv_8
323348    3.7452  f_GetChiSq(float*, int, int, float, float, float*, float*)
317069    3.6724  t2bv_32
234729    2.7187  v_GetPowerSpectrum(float (*) [2], float*, int)
231380    2.6799  t3bv_4
200300    2.3200  find_triplets(float const*, int, float, int, int)
191039    2.2127  GetFixedPoT(float*, int, int, float*, int, int)
185095    2.1439  __ieee754_pow
165872    1.9212  analyze_pot(float*, int, ChirpFftPair_t&)
157836    1.8281  t1bv_16
146084    1.6920  find_pulse(float const*, int, float, int, int)
129994    1.5056  foldArrayBy2LO(float**, PoTPlan*)
111980    1.2970  float_to_uchar(float*, unsigned char*, long, float)
93247     1.0800  malloc
91522     1.0600  __ieee754_log
84356     0.9770  free
77843     0.9016  foldArrayBy3LO(float**, PoTPlan*)
72138     0.8355  foldArrayBy5LO(float**, PoTPlan*)
67831     0.7856  t2bv_64
60135     0.6965  _int_malloc
59720     0.6917  foldArrayBy4LO(float**, PoTPlan*)
59568     0.6899  foldArrayBy4(float**, PoTPlan*)
58252     0.6747  foldArrayBy3(float**, PoTPlan*)
56273     0.6518  t1bv_4
51458     0.5960  pow
46227     0.5354  foldArrayBy2A(float**, PoTPlan*)
35654     0.4130  foldArrayBy5(float**, PoTPlan*)
34110     0.3951  n2bv_64
33538     0.3885  fraction_done(double, double)
23982     0.2778  time_to_ra_dec(double, double*, double*)
23298     0.2698  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
17820     0.2064  foldArrayBy2AL(float**, PoTPlan*)
17716     0.2052  t1bv_32
17057     0.1976  isnan
16392     0.1899  PulseProgressUnits(double, int)
16121     0.1867  _int_free
14167     0.1641  malloc_consolidate
8218      0.0952  operator new(unsigned int)
7699      0.0892  floor
6563      0.0760  boinc_fraction_done
6305      0.0730  workunit_grp::workunit_grp()
5786      0.0670  t_funct(int, int, int)
5643      0.0654  analysis_config::analysis_config()
5461      0.0633  t2bv_16
5434      0.0629  n1fv_128
5392      0.0625  n2bv_32
5082      0.0589  gaussian::gaussian()
4867      0.0564  result::result()
4720      0.0547  workunit_header::workunit_header()
4719      0.0547  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
4632      0.0536  checkpoint(unsigned char)
4616      0.0535  MFILE::~MFILE()
4575      0.0530  TripletProgressUnits()
4385      0.0508  __memmove_ssse3_rep
4292      0.0497  finite
4201      0.0487  fftwf_cpy2d_pair
3995      0.0463  splitter_config::splitter_config()
3416      0.0396  t2_32
3363      0.0390  receiver_config::receiver_config()
3339      0.0387  calc_detection_freq(double, double, double)
3313      0.0384  cnvt_bin_hz(int, int)
3139      0.0364  operator delete(void*)
3130      0.0363  data_description_t::data_description_t()
3049      0.0353  __i686.get_pc_thunk.bx
2978      0.0345  t1_32
2597      0.0301  tape::tape()
2557      0.0296  GAUSS_INFO::~GAUSS_INFO()
2269      0.0263  log
2127      0.0246  recorder_config::recorder_config()
2035      0.0236  t1_64
1971      0.0228  __memset_sse2_rep
1874      0.0217  MFILE::MFILE()
1874      0.0217  t1fv_8
1773      0.0205  t2bv_8
1583      0.0183  fftwf_twiddle_awake
1543      0.0179  subband_description_t::subband_description_t()
1543      0.0179  v_BaseLineSmooth(float (*) [2], int, int, int)
1480      0.0171  t2_64
1457      0.0169  T.9619
1409      0.0163  T.9614
1193      0.0138  t2fv_16
908       0.0105  GaussianProgressUnits()
876       0.0101  t2fv_32
797       0.0092  t2fv_8
746       0.0086  t1_2
688       0.0080  GAUSS_INFO::GAUSS_INFO()
663       0.0077  apply_dit
614       0.0071  apply
497       0.0058  t2_16
492       0.0057  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
469       0.0054  SpikeProgressUnits(int)
412       0.0048  T.9610
389       0.0045  apply
374       0.0043  n1fv_64
372       0.0043  q1fv_8
363       0.0042  dobatch
361       0.0042  cexp_zero
352       0.0041  t1fv_4
338       0.0039  fftwf_cpy2d
335       0.0039  seti_analyze(ANALYSIS_STATE&)
311       0.0036  t1fv_2
271       0.0031  recur
227       0.0026  t1fuv_2
223       0.0026  apply
222       0.0026  q1fv_2
216       0.0025  spike::spike()
195       0.0023  t1fuv_8
183       0.0021  fftwf_cpy1d
152       0.0018  memalign
144       0.0017  __ieee754_log10
124       0.0014  SPIKE_INFO::SPIKE_INFO()
112       0.0013  SPIKE_INFO::~SPIKE_INFO()
109       0.0013  GetProgressUnitSize(int, int)
107       0.0012  _int_memalign
104       0.0012  GetPulsePoTLen(long, int*, int*)
98        0.0011  fftwf_cpy2d_pair_co
96        0.0011  boinc_time_to_checkpoint
86       1.0e-03  fftwf_cpy2d_pair_ci
82       9.5e-04  t1_16
66       7.6e-04  recur
54       6.3e-04  log10
53       6.1e-04  fftwf_execute_dft
45       5.2e-04  T.9615
36       4.2e-04  floorf
34       3.9e-04  fftwf_md5putc
34       3.9e-04  invert_lcgf(float, float, float)
34       3.9e-04  pulse::pulse()
29       3.4e-04  apply_buf
21       2.4e-04  calloc_a(unsigned int, unsigned int, unsigned int)
19       2.2e-04  PULSE_INFO::~PULSE_INFO()
18       2.1e-04  plan_PulsePoT(PoTPlan*, int, float*, int*)
13       1.5e-04  PULSE_INFO::PULSE_INFO()
10       1.2e-04  fftwf_kernel_free
10       1.2e-04  fftwf_kernel_malloc
10       1.2e-04  timer_handler()
9        1.0e-04  fftwf_malloc
8        9.3e-05  fftwf_md5putb
8        9.3e-05  invoke_solver
7        8.1e-05  fftwf_md5end
7        8.1e-05  malloc_a(unsigned int, unsigned int)
6        6.9e-05  mkplan
5        5.8e-05  __libc_disable_asynccancel
3        3.5e-05  ChirpProgressUnits()
3        3.5e-05  apply
3        3.5e-05  fftwf_free
3        3.5e-05  fftwf_mkstride
3        3.5e-05  htab_insert
3        3.5e-05  htab_lookup
2        2.3e-05  __restore
2        2.3e-05  boinc_sleep(double)
2        2.3e-05  fftwf_ct_applicable
2        2.3e-05  fftwf_isqrt
2        2.3e-05  fftwf_mkproblem
2        2.3e-05  fftwf_plan_awake
2        2.3e-05  mkplan
2        2.3e-05  result_group_start()
2        2.3e-05  search0
2        2.3e-05  usleep
2        2.3e-05  worker_signal_handler(int)
1        1.2e-05  __libc_enable_asynccancel
1        1.2e-05  __nanosleep_nocancel
1        1.2e-05  _dl_sysinfo_int80
1        1.2e-05  awake
1        1.2e-05  dtime()
1        1.2e-05  fftwf_choose_radix
1        1.2e-05  fftwf_md5int
1        1.2e-05  fftwf_mkplan_d
1        1.2e-05  fftwf_mkproblem_dft
1        1.2e-05  fftwf_mktensor
1        1.2e-05  fftwf_pickdim
1        1.2e-05  fftwf_tensor_append
1        1.2e-05  fftwf_tensor_compress_contiguous
1        1.2e-05  fftwf_tensor_md5
1        1.2e-05  fill_slot
1        1.2e-05  free_a(void*)
1        1.2e-05  gettimeofday
1        1.2e-05  hash
1        1.2e-05  hinsert0
1        1.2e-05  memcpy
1        1.2e-05  mkplan
1        1.2e-05  mkplan
1        1.2e-05  mkplan
1        1.2e-05  mkplan
1        1.2e-05  nanosleep
1        1.2e-05  timer_thread(void*)
```

### Intel Core i3 - SETI@Home - LLC\_MISSES ###

```
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted LLC_MISSES events (Last level cache demand requests from this core that missed the LLC) with a unit mask of 0x41 (No unit mask) count 10000
 LLC_MISSES:10000|
  samples|      %|
------------------
    69816 97.8130 seti_boinc
      172  0.2410 libglib-2.0.so.0.2600.0
      165  0.2312 python2.6
      146  0.2045 Xorg
      135  0.1891 libc-2.12.1.so
      107  0.1499 libgtk-x11-2.0.so.0.2200.0
      101  0.1415 libcairo.so.2.11000.0
       83  0.1163 libgdk-x11-2.0.so.0.2200.0
       78  0.1093 libgobject-2.0.so.0.2600.0
       71  0.0995 libdrm_intel.so.1.0.0
       56  0.0785 libpthread-2.12.1.so
       56  0.0785 i965_dri.so
       35  0.0490 libpango-1.0.so.0.2800.1
       35  0.0490 intel_drv.so
       31  0.0434 libX11.so.6.3.0
       24  0.0336 libdbus-1.so.3.5.2
       23  0.0322 compiz
       19  0.0266 mysqld
       18  0.0252 libxcb.so.1.1.0
       15  0.0210 libfade.so
       15  0.0210 libmurrine.so
       14  0.0196 libpixman-1.so.0.18.4
        9  0.0126 libpangoft2-1.0.so.0.2800.1
        8  0.0112 no-vmlinux
        7  0.0098 ld-2.12.1.so
        6  0.0084 libm-2.12.1.so
        6  0.0084 libanimation.so
        6  0.0084 libdecoration.so
        6  0.0084 libexpo.so
        6  0.0084 libgthread-2.0.so.0.2600.0
        6  0.0084 libGL.so.1.2
        6  0.0084 evdev_drv.so
        6  0.0084 libfb.so
        5  0.0070 _glib.so
        4  0.0056 bash
        4  0.0056 libscale.so
        4  0.0056 libgtksourceview-2.0.so.0.0.0
        4  0.0056 libpyglib-2.0-python2.6.so.0.0.0
        4  0.0056 libvte.so.9.2600.0
        3  0.0042 im-ibus.so
        3  0.0042 libXext.so.6.4.0
        3  0.0042 libXfixes.so.3.1.0
        3  0.0042 libXrender.so.1.3.0
        3  0.0042 libpangocairo-1.0.so.0.2800.1
        2  0.0028 dbus-daemon
        2  0.0028 libdrm.so.2.4.0
        2  0.0028 librt-2.12.1.so
        2  0.0028 gedit
        2  0.0028 libresize.so
        2  0.0028 libresizeinfo.so
        2  0.0028 libstaticswitcher.so
        2  0.0028 libXi.so.6.1.0
        2  0.0028 libdbus-glib-1.so.2.1.0
        2  0.0028 librsvg-2.so.2.32.0
        2  0.0028 libxklavier.so.16.0.0
        2  0.0028 libdri2.so
        1  0.0014 ls
        1  0.0014 libz.so.1.2.3.4
        1  0.0014 gawk
        1  0.0014 gnome-power-manager
        1  0.0014 libimgjpeg.so
        1  0.0014 libneg.so
        1  0.0014 libscaleaddon.so
        1  0.0014 libvpswitch.so
        1  0.0014 libORBit-2.so.0.1.0
        1  0.0014 libXdamage.so.1.1.0
        1  0.0014 libavahi-common.so.3.5.2
        1  0.0014 libcompizconfig.so.0.0.0
        1  0.0014 libdecoration.so.0.0.0
        1  0.0014 libfreetype.so.6.6.0
        1  0.0014 libgconfbackend-xml.so
        1  0.0014 libgdk_pixbuf-2.0.so.0.2200.0
        1  0.0014 libgio-2.0.so.0.2600.0
        1  0.0014 libgnome-keyring.so.0.1.1
        1  0.0014 libmetacity-private.so.0.0.0
        1  0.0014 libstartup-notification-1.so.0.0.0
        1  0.0014 libxml2.so.2.7.7
        1  0.0014 pango-basic-fc.so
        1  0.0014 _gobject.so
        1  0.0014 _gtk.so
        1  0.0014 udisks-daemon
        1  0.0014 libextmod.so
 
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted LLC_MISSES events (Last level cache demand requests from this core that missed the LLC) with a unit mask of 0x41 (No unit mask) count 10000
samples  %        symbol name
33613    48.1451  GetFixedPoT(float*, int, int, float*, int, int)
18229    26.1101  n1bv_128
16293    23.3371  analyze_pot(float*, int, ChirpFftPair_t&)
459       0.6574  n2bv_64
264       0.3781  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
188       0.2693  v_GetPowerSpectrum(float (*) [2], float*, int)
147       0.2106  t2bv_32
142       0.2034  t3bv_4
74        0.1060  t1bv_8
67        0.0960  _int_malloc
53        0.0759  n2bv_32
37        0.0530  malloc_consolidate
16        0.0229  malloc
13        0.0186  GaussFit(float*, int, int)
12        0.0172  FindSpikes(float*, int, int, SETI_WU_INFO&)
12        0.0172  seti_analyze(ANALYSIS_STATE&)
12        0.0172  t1bv_4
10        0.0143  t2bv_64
9         0.0129  _int_free
9         0.0129  checkpoint(unsigned char)
8         0.0115  apply
8         0.0115  apply
8         0.0115  time_to_ra_dec(double, double*, double*)
7         0.0100  t1bv_16
6         0.0086  calc_detection_freq(double, double, double)
6         0.0086  free
5         0.0072  f_GetTrueMean(float*, int, float, int, int)
4         0.0057  __memset_sse2_rep
4         0.0057  apply_dit
4         0.0057  cnvt_bin_hz(int, int)
4         0.0057  f_GetChiSq(float*, int, int, float, float, float*, float*)
4         0.0057  find_triplets(float const*, int, float, int, int)
4         0.0057  pow
4         0.0057  result::result()
3         0.0043  MFILE::~MFILE()
3         0.0043  T.9614
3         0.0043  __i686.get_pc_thunk.bx
3         0.0043  __ieee754_log
3         0.0043  __memmove_ssse3_rep
3         0.0043  boinc_time_to_checkpoint
3         0.0043  data_description_t::data_description_t()
3         0.0043  fftwf_execute_dft
3         0.0043  lcgf(double, double)
3         0.0043  log10
3         0.0043  operator new(unsigned int)
3         0.0043  workunit_grp::workunit_grp()
2         0.0029  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
2         0.0029  PulseProgressUnits(double, int)
2         0.0029  SPIKE_INFO::~SPIKE_INFO()
2         0.0029  SpikeProgressUnits(int)
2         0.0029  T.9610
2         0.0029  boinc_fraction_done
2         0.0029  f_GetPeak(float*, int, int, float, float, float*)
2         0.0029  gaussian::gaussian()
2         0.0029  operator delete(void*)
2         0.0029  spike::spike()
2         0.0029  tape::tape()
2         0.0029  workunit_header::workunit_header()
1         0.0014  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
1         0.0014  __ieee754_log10
1         0.0014  __ieee754_pow
1         0.0014  __nanosleep_nocancel
1         0.0014  __restore
1         0.0014  _dl_sysinfo_int80
1         0.0014  analysis_config::analysis_config()
1         0.0014  apply
1         0.0014  find_pulse(float const*, int, float, int, int)
1         0.0014  foldArrayBy2LO(float**, PoTPlan*)
1         0.0014  fraction_done(double, double)
1         0.0014  getrusage
1         0.0014  isnan
1         0.0014  log
1         0.0014  memalign
1         0.0014  pulse::pulse()
1         0.0014  recorder_config::recorder_config()
1         0.0014  splitter_config::splitter_config()
1         0.0014  t1bv_32
1         0.0014  t_funct(int, int, int)
1         0.0014  timer_handler()
```

### Intel Core i3 - SETI@Home - LLC\_REFS ###

```
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted LLC_REFS events (Last level cache demand requests from this core) with a unit mask of 0x4f (No unit mask) count 10000
   LLC_REFS:10000|
  samples|      %|
------------------
   186781 95.5099 seti_boinc
     1086  0.5553 libc-2.12.1.so
      939  0.4802 libcairo.so.2.11000.0
      938  0.4796 libglib-2.0.so.0.2600.0
      921  0.4710 Xorg
      685  0.3503 libgobject-2.0.so.0.2600.0
      536  0.2741 libgtk-x11-2.0.so.0.2200.0
      404  0.2066 libgdk-x11-2.0.so.0.2200.0
      370  0.1892 libpango-1.0.so.0.2800.1
      342  0.1749 python2.6
      317  0.1621 intel_drv.so
      304  0.1554 libdrm_intel.so.1.0.0
      291  0.1488 libpthread-2.12.1.so
      227  0.1161 libpixman-1.so.0.18.4
      148  0.0757 libX11.so.6.3.0
      113  0.0578 libpangoft2-1.0.so.0.2800.1
      111  0.0568 i965_dri.so
       98  0.0501 libxcb.so.1.1.0
       80  0.0409 libmurrine.so
       74  0.0378 compiz
       70  0.0358 libdbus-1.so.3.5.2
       57  0.0291 no-vmlinux
       57  0.0291 libpangocairo-1.0.so.0.2800.1
       49  0.0251 libXrender.so.1.3.0
       35  0.0179 mysqld
       34  0.0174 ld-2.12.1.so
       34  0.0174 evdev_drv.so
       33  0.0169 libm-2.12.1.so
       32  0.0164 libfb.so
       28  0.0143 libfade.so
       27  0.0138 librsvg-2.so.2.32.0
       21  0.0107 libgio-2.0.so.0.2600.0
       20  0.0102 bash
       19  0.0097 libgtksourceview-2.0.so.0.0.0
       17  0.0087 libextmod.so
       15  0.0077 libexpo.so
       15  0.0077 libgthread-2.0.so.0.2600.0
       14  0.0072 libGL.so.1.2
       13  0.0066 libdrm.so.2.4.0
       11  0.0056 libanimation.so
       10  0.0051 librt-2.12.1.so
       10  0.0051 libudev.so.0.9.1
       10  0.0051 libpyglib-2.0-python2.6.so.0.0.0
        9  0.0046 oprofiled
        9  0.0046 libdecoration.so
        9  0.0046 libstaticswitcher.so
        8  0.0041 gedit
        7  0.0036 libscaleaddon.so
        7  0.0036 libwall.so
        7  0.0036 libxml2.so.2.7.7
        7  0.0036 pango-basic-fc.so
        7  0.0036 _glib.so
        6  0.0031 libgdk_pixbuf-2.0.so.0.2200.0
        6  0.0031 libwnck-1.so.22.3.30
        5  0.0026 dbus-daemon
        5  0.0026 libscale.so
        5  0.0026 libXfixes.so.3.1.0
        5  0.0026 libdbus-glib-1.so.2.1.0
        5  0.0026 libfreetype.so.6.6.0
        5  0.0026 libgvfscommon.so.0.0.0
        5  0.0026 libstartup-notification-1.so.0.0.0
        4  0.0020 libezoom.so
        3  0.0015 gawk
        3  0.0015 libregex.so
        3  0.0015 libresizeinfo.so
        3  0.0015 _gtk.so
        2  0.0010 libsession.so
        2  0.0010 libworkarounds.so
        2  0.0010 im-ibus.so
        2  0.0010 libXext.so.6.4.0
        2  0.0010 _gobject.so
        1 5.1e-04 ls
        1 5.1e-04 libz.so.1.2.3.4
        1 5.1e-04 gtk-window-decorator
        1 5.1e-04 libmousepoll.so
        1 5.1e-04 libmove.so
        1 5.1e-04 libresize.so
        1 5.1e-04 libsvg.so
        1 5.1e-04 libvpswitch.so
        1 5.1e-04 libgvfsdbus.so
        1 5.1e-04 libkeyboard.so
        1 5.1e-04 libmouse.so
        1 5.1e-04 libpixmap.so
        1 5.1e-04 libORBit-2.so.0.1.0
        1 5.1e-04 libavahi-common.so.3.5.2
        1 5.1e-04 libavahi-core.so.7.0.0
        1 5.1e-04 libgconf-2.so.4.1.5
        1 5.1e-04 libnm-glib.so.2.4.1
        1 5.1e-04 libnm-util.so.1.6.0
        1 5.1e-04 libpulse-mainloop-glib.so.0.0.4
        1 5.1e-04 libvte.so.9.2600.0
        1 5.1e-04 libxklavier.so.16.0.0
        1 5.1e-04 libdri2.so
        1 5.1e-04 rsyslogd
 
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted LLC_REFS events (Last level cache demand requests from this core) with a unit mask of 0x4f (No unit mask) count 10000
samples  %        symbol name
108392   58.0316  n1bv_128
38554    20.6413  GetFixedPoT(float*, int, int, float*, int, int)
22844    12.2304  analyze_pot(float*, int, ChirpFftPair_t&)
6256      3.3494  t2bv_32
2660      1.4241  t1bv_8
2014      1.0783  v_GetPowerSpectrum(float (*) [2], float*, int)
1032      0.5525  t2bv_64
764       0.4090  t1bv_16
577       0.3089  FindSpikes(float*, int, int, SETI_WU_INFO&)
575       0.3078  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
442       0.2366  n2bv_64
442       0.2366  t3bv_4
301       0.1612  t1bv_32
299       0.1601  t1bv_4
181       0.0969  _int_malloc
137       0.0733  malloc
136       0.0728  malloc_consolidate
105       0.0562  apply
79        0.0423  apply
73        0.0391  apply_dit
67        0.0359  n2bv_32
62        0.0332  find_pulse(float const*, int, float, int, int)
59        0.0316  seti_analyze(ANALYSIS_STATE&)
48        0.0257  find_triplets(float const*, int, float, int, int)
47        0.0252  time_to_ra_dec(double, double*, double*)
39        0.0209  foldArrayBy3(float**, PoTPlan*)
36        0.0193  _int_free
34        0.0182  free
26        0.0139  foldArrayBy4(float**, PoTPlan*)
26        0.0139  pow
20        0.0107  GaussFit(float*, int, int)
19        0.0102  cnvt_bin_hz(int, int)
18        0.0096  calc_detection_freq(double, double, double)
17        0.0091  __ieee754_log10
17        0.0091  log
16        0.0086  workunit_grp::workunit_grp()
15        0.0080  result::result()
14        0.0075  analysis_config::analysis_config()
14        0.0075  apply
14        0.0075  foldArrayBy5(float**, PoTPlan*)
12        0.0064  __ieee754_pow
12        0.0064  __memset_sse2_rep
12        0.0064  fftwf_execute_dft
12        0.0064  tape::tape()
11        0.0059  T.9610
11        0.0059  foldArrayBy2A(float**, PoTPlan*)
11        0.0059  operator new(unsigned int)
10        0.0054  __ieee754_log
10        0.0054  foldArrayBy3LO(float**, PoTPlan*)
10        0.0054  workunit_header::workunit_header()
9         0.0048  SpikeProgressUnits(int)
8         0.0043  TripletProgressUnits()
8         0.0043  f_GetChiSq(float*, int, int, float, float, float*, float*)
7         0.0037  MFILE::MFILE()
7         0.0037  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
7         0.0037  SPIKE_INFO::SPIKE_INFO()
7         0.0037  SPIKE_INFO::~SPIKE_INFO()
7         0.0037  boinc_fraction_done
7         0.0037  checkpoint(unsigned char)
7         0.0037  spike::spike()
7         0.0037  splitter_config::splitter_config()
6         0.0032  T.9614
6         0.0032  foldArrayBy2AL(float**, PoTPlan*)
6         0.0032  recorder_config::recorder_config()
5         0.0027  __i686.get_pc_thunk.bx
5         0.0027  f_GetTrueMean(float*, int, float, int, int)
5         0.0027  foldArrayBy2LO(float**, PoTPlan*)
5         0.0027  foldArrayBy4LO(float**, PoTPlan*)
5         0.0027  fraction_done(double, double)
4         0.0021  data_description_t::data_description_t()
4         0.0021  foldArrayBy5LO(float**, PoTPlan*)
4         0.0021  n1_16
4         0.0021  t_funct(int, int, int)
3         0.0016  GaussianProgressUnits()
3         0.0016  MFILE::~MFILE()
3         0.0016  _int_memalign
3         0.0016  floorf
3         0.0016  isnan
3         0.0016  n2bv_16
3         0.0016  operator delete(void*)
3         0.0016  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
2         0.0011  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
2         0.0011  PULSE_INFO::PULSE_INFO()
2         0.0011  T.9615
2         0.0011  __memmove_ssse3_rep
2         0.0011  f_GetPeak(float*, int, int, float, float, float*)
2         0.0011  fftwf_malloc
2         0.0011  memalign
2         0.0011  pulse::pulse()
2         0.0011  timer_handler()
1        5.4e-04  GAUSS_INFO::GAUSS_INFO()
1        5.4e-04  GetPulsePoTLen(long, int*, int*)
1        5.4e-04  PULSE_INFO::~PULSE_INFO()
1        5.4e-04  PulseProgressUnits(double, int)
1        5.4e-04  __libc_disable_asynccancel
1        5.4e-04  __nanosleep_nocancel
1        5.4e-04  _dl_sysinfo_int80
1        5.4e-04  boinc_time_to_checkpoint
1        5.4e-04  dtime()
1        5.4e-04  float_to_uchar(float*, unsigned char*, long, float)
1        5.4e-04  floor
1        5.4e-04  lcgf(double, double)
1        5.4e-04  malloc_a(unsigned int, unsigned int)
1        5.4e-04  receiver_config::receiver_config()
1        5.4e-04  result_group_start()
1        5.4e-04  subband_description_t::subband_description_t()
1        5.4e-04  t2bv_16
```

### Intel Core i3 - SETI@Home - BR\_INST\_RETIRED ###

```
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted BR_INST_RETIRED events (number of branch instructions retired) with a unit mask of 0x00 (No unit mask) count 10000
BR_INST_RETIRE...|
  samples|      %|
------------------
  2188459 90.0339 seti_boinc
    32111  1.3211 libdrm_intel.so.1.0.0
    30642  1.2606 libcairo.so.2.11000.0
    24070  0.9902 libc-2.12.1.so
    23782  0.9784 libglib-2.0.so.0.2600.0
    23353  0.9607 libpixman-1.so.0.18.4
    18797  0.7733 libgobject-2.0.so.0.2600.0
    15048  0.6191 libpangoft2-1.0.so.0.2800.1
    14430  0.5937 oprofiled
    11218  0.4615 libgtk-x11-2.0.so.0.2200.0
    10835  0.4458 libpthread-2.12.1.so
     9578  0.3940 Xorg
     4704  0.1935 libpango-1.0.so.0.2800.1
     4226  0.1739 intel_drv.so
     3538  0.1456 libgdk-x11-2.0.so.0.2200.0
     2045  0.0841 librsvg-2.so.2.32.0
     1496  0.0615 libxml2.so.2.7.7
     1432  0.0589 libhunspell-1.2.so.0.0.0
     1178  0.0485 bash
      999  0.0411 libgthread-2.0.so.0.2600.0
      764  0.0314 python2.6
      657  0.0270 libX11.so.6.3.0
      631  0.0260 libmurrine.so
      623  0.0256 libpcre.so.3.12.1
      576  0.0237 libpangocairo-1.0.so.0.2800.1
      569  0.0234 ld-2.12.1.so
      483  0.0199 libm-2.12.1.so
      471  0.0194 no-vmlinux
      400  0.0165 mysqld
      375  0.0154 i965_dri.so
      357  0.0147 libxcb.so.1.1.0
      352  0.0145 libdbus-1.so.3.5.2
      276  0.0114 libXrender.so.1.3.0
      269  0.0111 libextmod.so
      252  0.0104 libgio-2.0.so.0.2600.0
      227  0.0093 compiz
      209  0.0086 pango-basic-fc.so
      159  0.0065 dbus-daemon
      116  0.0048 libgdk_pixbuf-2.0.so.0.2200.0
      116  0.0048 libgtksourceview-2.0.so.0.0.0
      114  0.0047 libfb.so
       66  0.0027 evdev_drv.so
       46  0.0019 gawk
       46  0.0019 libfreetype.so.6.6.0
       38  0.0016 libdecoration.so
       38  0.0016 libavahi-common.so.3.5.2
       36  0.0015 gedit
       31  0.0013 libGL.so.1.2
       30  0.0012 libexpo.so
       29  0.0012 libfade.so
       28  0.0012 librt-2.12.1.so
       28  0.0012 libvte.so.9.2600.0
       26  0.0011 libdrm.so.2.4.0
       19 7.8e-04 libgvfscommon.so.0.0.0
       16 6.6e-04 libanimation.so
       16 6.6e-04 libresize.so
       16 6.6e-04 libpyglib-2.0-python2.6.so.0.0.0
       15 6.2e-04 libdbus-glib-1.so.2.1.0
       15 6.2e-04 _glib.so
       13 5.3e-04 libORBit-2.so.0.1.0
       12 4.9e-04 libXfixes.so.3.1.0
       12 4.9e-04 rsyslogd
       11 4.5e-04 libwall.so
       10 4.1e-04 dash
       10 4.1e-04 grep
       10 4.1e-04 libpam.so.0.82.2
        9 3.7e-04 libz.so.1.2.3.4
        9 3.7e-04 sudo
        9 3.7e-04 libscale.so
        9 3.7e-04 libsvg.so
        9 3.7e-04 libwnck-1.so.22.3.30
        8 3.3e-04 libstaticswitcher.so
        7 2.9e-04 libavahi-core.so.7.0.0
        6 2.5e-04 libmetacity-private.so.0.0.0
        5 2.1e-04 libpng12.so.0.44.0
        4 1.6e-04 libmove.so
        4 1.6e-04 libworkarounds.so
        4 1.6e-04 libdri2.so
        3 1.2e-04 libudev.so.0.9.1
        3 1.2e-04 libregex.so
        3 1.2e-04 libresizeinfo.so
        3 1.2e-04 libscaleaddon.so
        3 1.2e-04 im-ibus.so
        3 1.2e-04 libstartup-notification-1.so.0.0.0
        2 8.2e-05 wpa_supplicant
        2 8.2e-05 gnome-panel
        2 8.2e-05 ophelp
        2 8.2e-05 libsession.so
        2 8.2e-05 libvpswitch.so
        2 8.2e-05 libgvfsdbus.so
        2 8.2e-05 libXdamage.so.1.1.0
        2 8.2e-05 libfontconfig.so.1.4.4
        2 8.2e-05 libnm-util.so.1.6.0
        2 8.2e-05 notify-osd
        2 8.2e-05 _gobject.so
        2 8.2e-05 NetworkManager
        1 4.1e-05 ls
        1 4.1e-05 sleep
        1 4.1e-05 libdl-2.12.1.so
        1 4.1e-05 libgcrypt.so.11.5.3
        1 4.1e-05 libnss_files-2.12.1.so
        1 4.1e-05 libpopt.so.0.0.0
        1 4.1e-05 libselinux.so.1
        1 4.1e-05 pam_unix.so
        1 4.1e-05 nm-applet
        1 4.1e-05 seq
        1 4.1e-05 libezoom.so
        1 4.1e-05 libimgjpeg.so
        1 4.1e-05 libplace.so
        1 4.1e-05 libpixbufloader-png.so
        1 4.1e-05 libdocinfo.so
        1 4.1e-05 liba11y-keyboard.so
        1 4.1e-05 libpixmap.so
        1 4.1e-05 libcanberra-gtk-module.so
        1 4.1e-05 libXext.so.6.4.0
        1 4.1e-05 libXi.so.6.1.0
        1 4.1e-05 libapr-1.so.0.4.2
        1 4.1e-05 libcompizconfig.so.0.0.0
        1 4.1e-05 libgconf-2.so.4.1.5
        1 4.1e-05 libnm-glib.so.2.4.1
        1 4.1e-05 libpulse-mainloop-glib.so.0.0.4
        1 4.1e-05 libusbmuxd.so.1.0.4
        1 4.1e-05 libxklavier.so.16.0.0

CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted BR_INST_RETIRED events (number of branch instructions retired) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
564687   25.8074  FindSpikes(float*, int, int, SETI_WU_INFO&)
279743   12.7849  f_GetTrueMean(float*, int, float, int, int)
177541    8.1140  GaussFit(float*, int, int)
135373    6.1868  find_triplets(float const*, int, float, int, int)
126744    5.7925  f_GetPeak(float*, int, int, float, float, float*)
62817     2.8709  GetFixedPoT(float*, int, int, float*, int, int)
58644     2.6802  lcgf(double, double)
54540     2.4926  free
49986     2.2845  f_GetChiSq(float*, int, int, float, float, float*, float*)
49020     2.2403  __ieee754_pow
45817     2.0939  find_pulse(float const*, int, float, int, int)
39825     1.8201  analyze_pot(float*, int, ChirpFftPair_t&)
39429     1.8020  malloc
37191     1.6997  foldArrayBy2LO(float**, PoTPlan*)
36174     1.6532  __ieee754_log
35384     1.6171  v_GetPowerSpectrum(float (*) [2], float*, int)
34835     1.5920  fraction_done(double, double)
32939     1.5054  float_to_uchar(float*, unsigned char*, long, float)
24623     1.1253  foldArrayBy3LO(float**, PoTPlan*)
24561     1.1225  pow
22316     1.0199  _int_malloc
19433     0.8881  sse2_ChirpData_ak(float (*) [2], float (*) [2], int, double, int, double)
18970     0.8670  foldArrayBy4LO(float**, PoTPlan*)
18671     0.8533  PulseProgressUnits(double, int)
16638     0.7604  boinc_fraction_done
15315     0.6999  foldArrayBy3(float**, PoTPlan*)
14125     0.6455  foldArrayBy2A(float**, PoTPlan*)
13435     0.6140  isnan
13378     0.6114  foldArrayBy4(float**, PoTPlan*)
11608     0.5305  _int_free
11126     0.5085  time_to_ra_dec(double, double*, double*)
9721      0.4443  t3bv_4
8238      0.3765  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
7693      0.3516  t1bv_8
6749      0.3084  foldArrayBy5(float**, PoTPlan*)
6744      0.3082  malloc_consolidate
5496      0.2512  foldArrayBy2AL(float**, PoTPlan*)
4845      0.2214  foldArrayBy5LO(float**, PoTPlan*)
3746      0.1712  operator new(unsigned int)
3553      0.1624  t_funct(int, int, int)
2998      0.1370  checkpoint(unsigned char)
2843      0.1299  floor
2481      0.1134  t1bv_4
2358      0.1078  workunit_grp::workunit_grp()
2220      0.1015  GAUSS_INFO::~GAUSS_INFO()
2200      0.1005  MFILE::~MFILE()
1949      0.0891  result::result()
1936      0.0885  __memmove_ssse3_rep
1839      0.0840  splitter_config::splitter_config()
1685      0.0770  receiver_config::receiver_config()
1649      0.0754  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
1636      0.0748  TripletProgressUnits()
1467      0.0670  __memset_sse2_rep
1433      0.0655  workunit_header::workunit_header()
1316      0.0601  gaussian::gaussian()
1315      0.0601  t1bv_16
1291      0.0590  t2bv_32
1285      0.0587  recorder_config::recorder_config()
1115      0.0510  __i686.get_pc_thunk.bx
1074      0.0491  MFILE::MFILE()
1033      0.0472  operator delete(void*)
896       0.0409  calc_detection_freq(double, double, double)
874       0.0399  cnvt_bin_hz(int, int)
829       0.0379  analysis_config::analysis_config()
777       0.0355  data_description_t::data_description_t()
766       0.0350  subband_description_t::subband_description_t()
665       0.0304  n1bv_128
582       0.0266  GaussianProgressUnits()
548       0.0250  T.9614
521       0.0238  tape::tape()
375       0.0171  log
271       0.0124  T.9610
211       0.0096  apply
169       0.0077  SpikeProgressUnits(int)
160       0.0073  apply
154       0.0070  finite
142       0.0065  seti_analyze(ANALYSIS_STATE&)
135       0.0062  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
132       0.0060  t2bv_64
131       0.0060  GAUSS_INFO::GAUSS_INFO()
117       0.0053  apply_dit
83        0.0038  apply
83        0.0038  memalign
81        0.0037  t1bv_32
76        0.0035  n2bv_64
64        0.0029  SPIKE_INFO::~SPIKE_INFO()
62        0.0028  t2bv_16
51        0.0023  spike::spike()
46        0.0021  __ieee754_log10
42        0.0019  n2bv_32
36        0.0016  _int_memalign
24        0.0011  boinc_time_to_checkpoint
19       8.7e-04  PULSE_INFO::~PULSE_INFO()
19       8.7e-04  floorf
19       8.7e-04  t2bv_8
17       7.8e-04  SPIKE_INFO::SPIKE_INFO()
17       7.8e-04  fftwf_execute_dft
12       5.5e-04  log10
11       5.0e-04  calloc_a(unsigned int, unsigned int, unsigned int)
10       4.6e-04  T.9615
9        4.1e-04  pulse::pulse()
7        3.2e-04  PULSE_INFO::PULSE_INFO()
7        3.2e-04  fftwf_malloc
5        2.3e-04  T.9619
5        2.3e-04  fftwf_kernel_malloc
5        2.3e-04  malloc_a(unsigned int, unsigned int)
4        1.8e-04  fftwf_kernel_free
4        1.8e-04  plan_PulsePoT(PoTPlan*, int, float*, int*)
3        1.4e-04  invert_lcgf(float, float, float)
3        1.4e-04  usleep
2        9.1e-05  result_group_start()
1        4.6e-05  GetPulsePoTLen(long, int*, int*)
1        4.6e-05  __restore
1        4.6e-05  fftwf_free
1        4.6e-05  worker_signal_handler(int)
```

### Intel Core i3 - SETI@Home - BR\_MISS\_PRED\_RETIRED ###

```
CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted BR_MISS_PRED_RETIRED events (number of mispredicted branches retired (precise)) with a unit mask of 0x00 (No unit mask) count 10000
BR_MISS_PRED_R...|
  samples|      %|
------------------
    17677 80.3939 seti_boinc
      639  2.9061 libglib-2.0.so.0.2600.0
      582  2.6469 libc-2.12.1.so
      485  2.2057 libcairo.so.2.11000.0
      388  1.7646 libgtk-x11-2.0.so.0.2200.0
      377  1.7146 libgobject-2.0.so.0.2600.0
      325  1.4781 Xorg
      193  0.8778 libpango-1.0.so.0.2800.1
      179  0.8141 libgdk-x11-2.0.so.0.2200.0
      155  0.7049 libdrm_intel.so.1.0.0
      135  0.6140 libpthread-2.12.1.so
      109  0.4957 libpangoft2-1.0.so.0.2800.1
       95  0.4321 python2.6
       84  0.3820 intel_drv.so
       74  0.3365 libX11.so.6.3.0
       60  0.2729 libpixman-1.so.0.18.4
       52  0.2365 libxcb.so.1.1.0
       39  0.1774 i965_dri.so
       36  0.1637 librsvg-2.so.2.32.0
       34  0.1546 libpcre.so.3.12.1
       28  0.1273 ld-2.12.1.so
       27  0.1228 bash
       21  0.0955 no-vmlinux
       20  0.0910 libxml2.so.2.7.7
       19  0.0864 libdbus-1.so.3.5.2
       18  0.0819 libXrender.so.1.3.0
       12  0.0546 libgio-2.0.so.0.2600.0
       11  0.0500 libpangocairo-1.0.so.0.2800.1
       10  0.0455 compiz
       10  0.0455 libgthread-2.0.so.0.2600.0
        9  0.0409 evdev_drv.so
        7  0.0318 libm-2.12.1.so
        6  0.0273 libdrm.so.2.4.0
        6  0.0273 libmurrine.so
        5  0.0227 dbus-daemon
        5  0.0227 libORBit-2.so.0.1.0
        5  0.0227 libgtksourceview-2.0.so.0.0.0
        5  0.0227 libgvfscommon.so.0.0.0
        5  0.0227 _glib.so
        4  0.0182 pango-basic-fc.so
        3  0.0136 libanimation.so
        3  0.0136 libXfixes.so.3.1.0
        3  0.0136 libGL.so.1.2
        3  0.0136 libextmod.so
        2  0.0091 libudev.so.0.9.1
        2  0.0091 libdecoration.so
        2  0.0091 libfade.so
        2  0.0091 libscaleaddon.so
        2  0.0091 libfreetype.so.6.6.0
        2  0.0091 libfb.so
        1  0.0045 libmove.so
        1  0.0045 libresize.so
        1  0.0045 libscale.so
        1  0.0045 libstaticswitcher.so
        1  0.0045 libXi.so.6.1.0
        1  0.0045 libdecoration.so.0.0.0
        1  0.0045 libgconf-2.so.4.1.5
        1  0.0045 libgdk_pixbuf-2.0.so.0.2200.0
        1  0.0045 libgnome-keyring.so.0.1.1
        1  0.0045 libxklavier.so.16.0.0
        1  0.0045 udisks-daemon
        1  0.0045 libdri2.so
        1  0.0045 NetworkManager

CPU: Intel Architectural Perfmon, speed 2133 MHz (estimated)
Counted BR_MISS_PRED_RETIRED events (number of mispredicted branches retired (precise)) with a unit mask of 0x00 (No unit mask) count 10000
samples  %        symbol name
3336     18.8720  GaussFit(float*, int, int)
3326     18.8154  f_GetTrueMean(float*, int, float, int, int)
2516     14.2332  find_pulse(float const*, int, float, int, int)
1716      9.7075  lcgf(double, double)
1061      6.0021  foldArrayBy2A(float**, PoTPlan*)
952       5.3855  foldArrayBy2LO(float**, PoTPlan*)
819       4.6331  foldArrayBy3(float**, PoTPlan*)
413       2.3364  find_triplets(float const*, int, float, int, int)
366       2.0705  foldArrayBy2AL(float**, PoTPlan*)
331       1.8725  foldArrayBy4(float**, PoTPlan*)
308       1.7424  floor
302       1.7084  time_to_ra_dec(double, double*, double*)
297       1.6801  foldArrayBy4LO(float**, PoTPlan*)
281       1.5896  _int_malloc
279       1.5783  foldArrayBy3LO(float**, PoTPlan*)
190       1.0748  analyze_pot(float*, int, ChirpFftPair_t&)
186       1.0522  foldArrayBy5(float**, PoTPlan*)
174       0.9843  foldArrayBy5LO(float**, PoTPlan*)
161       0.9108  FindSpikes(float*, int, int, SETI_WU_INFO&)
156       0.8825  malloc_consolidate
154       0.8712  GetFixedPoT(float*, int, int, float*, int, int)
104       0.5883  ChooseGaussEvent(int, float, float, float, float, int, float, float, float*)
64        0.3621  free
29        0.1641  n1bv_128
28        0.1584  t1bv_16
19        0.1075  f_GetChiSq(float*, int, int, float, float, float*, float*)
15        0.0849  operator delete(void*)
12        0.0679  apply
8         0.0453  apply
7         0.0396  checkpoint(unsigned char)
6         0.0339  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
6         0.0339  _int_free
6         0.0339  t1bv_8
5         0.0283  calc_detection_freq(double, double, double)
4         0.0226  seti_analyze(ANALYSIS_STATE&)
4         0.0226  t2bv_32
3         0.0170  __memset_sse2_rep
3         0.0170  apply
3         0.0170  apply_dit
3         0.0170  malloc
2         0.0113  __ieee754_log10
2         0.0113  float_to_uchar(float*, unsigned char*, long, float)
2         0.0113  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
2         0.0113  v_GetPowerSpectrum(float (*) [2], float*, int)
1         0.0057  SPIKE_INFO::~SPIKE_INFO()
1         0.0057  __ieee754_pow
1         0.0057  __memmove_ssse3_rep
1         0.0057  _int_memalign
1         0.0057  cnvt_bin_hz(int, int)
1         0.0057  f_GetPeak(float*, int, int, float, float, float*)
1         0.0057  fftwf_execute_dft
1         0.0057  fraction_done(double, double)
1         0.0057  memalign
1         0.0057  n2bv_64
1         0.0057  receiver_config::receiver_config()
1         0.0057  spike::spike()
1         0.0057  t1bv_32
1         0.0057  t2bv_64
1         0.0057  t_funct(int, int, int)
1         0.0057  usleep
```

### Core i3 list of events ###

```
jeff@east:~/stuff/seti_boinc/client$ sudo opcontrol --list-events
oprofile: available events for CPU type "Intel Architectural Perfmon"

See Intel 64 and IA-32 Architectures Software Developer's Manual
Volume 3B (Document 253669) Chapter 18 for architectural perfmon events
This is a limited set of fallback events because oprofile doesn't know your CPU
CPU_CLK_UNHALTED: (counter: all)
	Clock cycles when not halted (min count: 6000) 
INST_RETIRED: (counter: all)
	number of instructions retired (min count: 6000) 
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
BR_MISS_PRED_RETIRED: (counter: all)
	number of mispredicted branches retired (precise) (min count: 500) 


```