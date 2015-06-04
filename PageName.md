# Profiling SETI@Home with oprofile on ARM Cortex-A8 #

Add your content here.


### Details ###

```
SleepSeconds=100
./seti_boinc --standalone &
date
sudo opcontrol --init
sudo opcontrol --no-vmlinux
sudo opcontrol --reset
sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds
sudo opcontrol --dump
sudo opreport 

```
# Timer Mode Data #
Using the RTC Timer

### Dumping the data ###
```
lucid@lucid-desktop:~/Documents/seti_boinc/client$ ./go_seti.sh 
Fri Aug 12 07:38:00 CST 2011
[sudo] password for lucid: 
Signalling daemon... done
Profiler running.
Daemon running: pid 5802
Separate options: none
vmlinux file: none
Image filter: none
Call-graph depth: 0
Overflow stats not available
CPU: CPU with timer interrupt, speed 0 MHz (estimated)
Profiling through timer interrupt
          TIMER:0|
  samples|      %|
------------------
     4601 44.7873 seti_boinc
     1625 15.8182 vmlinux-2.6.35.3-850-gbc67621-g91e9da8
     1255 12.2165 libpixman-1.so.0.16.4
      819  7.9724 libc-2.11.1.so
      639  6.2202 Xorg
      227  2.2097 libcairo.so.2.10800.10
      163  1.5867 libz160.so
      134  1.3044 libglib-2.0.so.0.2400.1
      134  1.3044 libgdk-x11-2.0.so.0.2000.1
      121  1.1778 libexa.so
      109  1.0610 imx_drv.so
       89  0.8663 libgobject-2.0.so.0.2400.1
       61  0.5938 libpthread-2.11.1.so
       56  0.5451 libX11.so.6.3.0
       43  0.4186 libgsl-fsl.so.1
       29  0.2823 libfb.so
       26  0.2531 python2.6
       22  0.2142 floaters
       19  0.1850 libxcb.so.1.1.0
       16  0.1557 libgtk-x11-2.0.so.0.2000.1
       15  0.1460 libXrender.so.1.3.0
       13  0.1265 bash
       13  0.1265 libm-2.11.1.so
       12  0.1168 ld-2.11.1.so
        8  0.0779 evdev_drv.so
        6  0.0584 libgthread-2.0.so.0.2400.1
        4  0.0389 librt-2.11.1.so
        3  0.0292 libudev.so.0.6.1
        3  0.0292 libpulsecommon-0.9.21.so
        2  0.0195 libavahi-common.so.3.5.1
        1  0.0097 libdbus-1.so.3.4.0
        1  0.0097 libecore-ver-svn-05.so.0.9.9
        1  0.0097 libgio-2.0.so.0.2400.1
        1  0.0097 libpyglib-2.0-python2.6.so.0.0.0
        1  0.0097 _glib.so
        1  0.0097 rsyslogd
lucid@lucid-desktop:~/Documents/seti_boinc/client$
```
### Isolating SETI@home ###
```
lucid@lucid-desktop:~/Documents/seti_boinc/client$ opreport -l /home/lucid/Documents/seti_boinc/client/seti_boinc
Overflow stats not available
CPU: CPU with timer interrupt, speed 0 MHz (estimated)
Profiling through timer interrupt
samples  %        symbol name
3025     35.4589  top_sum2(float**, PoTPlan*)
1850     21.6856  top_sum3(float**, PoTPlan*)
1553     18.2042  top_sum4(float**, PoTPlan*)
1378     16.1529  top_sum5(float**, PoTPlan*)
90        1.0550  strchr
53        0.6213  __ieee754_log
51        0.5978  Laligned
45        0.5275  n1_64
43        0.5040  sw_sum2_t31(float**, PoTPlan*)
40        0.4689  t1_32
34        0.3985  find_pulse(float const*, int, float, int, int)
26        0.3048  t1_16
22        0.2579  t_funct(int, int, int)
22        0.2579  v_BaseLineSmooth(float (*) [2], int, int, int)
20        0.2344  n1_32
17        0.1993  q1_4
17        0.1993  t1_8
16        0.1876  q1_8
16        0.1876  v_GetPowerSpectrum(float (*) [2], float*, int)
13        0.1524  t1_4
12        0.1407  __ieee754_pow
12        0.1407  lcgf(double, double)
11        0.1289  n1_8
10        0.1172  FindSpikes(float*, int, int, SETI_WU_INFO&)
10        0.1172  time_to_ra_dec(double, double*, double*)
8         0.0938  GenChirpFftPairs(ChirpFftPair_t**, double*)
8         0.0938  GetFixedPoT(float*, int, int, float*, int, int)
8         0.0938  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
8         0.0938  malloc
7         0.0821  _int_malloc
7         0.0821  analyze_pot(float*, int, ChirpFftPair_t&)
7         0.0821  logl
6         0.0703  __divsi3
5         0.0586  __exp1
5         0.0586  calc_detection_freq(double, double, double)
5         0.0586  malloc_consolidate
5         0.0586  memcpy
4         0.0469  analysis_config::analysis_config()
3         0.0352  bits_to_floats(unsigned char*, float (*) [2], int)
3         0.0352  free
3         0.0352  memset
3         0.0352  workunit_grp::workunit_grp()
2         0.0234  GetPulsePoTLen(long, int*, int*)
2         0.0234  SpikeProgressUnits(int)
2         0.0234  fraction_done(double, double)
2         0.0234  operator new(unsigned int)
2         0.0234  powl
2         0.0234  seti_analyze(ANALYSIS_STATE&)
2         0.0234  splitter_config::splitter_config()
2         0.0234  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
2         0.0234  tape::tape()
1         0.0117  GaussianProgressUnits()
1         0.0117  GetProgressUnitSize(int, int)
1         0.0117  T.9826
1         0.0117  __aeabi_d2ulz
1         0.0117  __ieee754_fmod
1         0.0117  __ieee754_log10
1         0.0117  __libc_enable_asynccancel
1         0.0117  _int_free
1         0.0117  apply_dit
1         0.0117  boinc_fraction_done
1         0.0117  cexpl_sqrtn_table
1         0.0117  cnvt_bin_hz(int, int)
1         0.0117  dtime()
1         0.0117  fftwf_kernel_malloc
1         0.0117  fftwf_md5int
1         0.0117  fftwf_md5putb
1         0.0117  fftwf_md5putc
1         0.0117  hgrow
1         0.0117  isnanl
1         0.0117  log10l
1         0.0117  mkplan
1         0.0117  mkplan
1         0.0117  mkplan
1         0.0117  msort_with_tmp
1         0.0117  std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_erase(std::_Rb_tree_node<std::pair<long long const, ChirpFftPair_t> >*)
1         0.0117  std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_insert_unique_(std::_Rb_tree_const_iterator<std::pair<long long const, ChirpFftPair_t> >, std::pair<long long const, ChirpFftPair_t> const&)
1         0.0117  std::string::_M_mutate(unsigned int, unsigned int, unsigned int)
1         0.0117  std::vector<unsigned char, std::allocator<unsigned char> > x_setiathome_decode<unsigned char>(char const*, unsigned int)
1         0.0117  subband_description_t::subband_description_t()
1         0.0117  vscan
1         0.0117  worker_signal_handler(int)
1         0.0117  workunit_header::workunit_header()
lucid@lucid-desktop:~/Documents/seti_boinc/client$

```

## On the Versatile Board ##

#### DCACHE Access ####
```
user41@ca9-natty:~/seti_boinc/client$ opreport
Overflow stats not available
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DCACHE_ACCESS events (Data R/W from cache) with a unit mask of 0x00 (No unit mask) count 500
DCACHE_ACCESS:500|
  samples|      %|
------------------
 17961204 50.2768 no-vmlinux
 11790083 33.0027 seti_boinc
  5634212 15.7712 oprofiled
        DCACHE_ACCESS:500|
          samples|      %|
        ------------------
          5634208 99.9999 oprofiled
                4 7.1e-05 [vectors] (tgid:32380 range:0xffff0000-0xffff1000)
   126138  0.3531 libc-2.13.so
    81590  0.2284 bash
    37943  0.1062 ld-2.13.so
    18019  0.0504 thttpd
    10919  0.0306 libglib-2.0.so.0.2800.6
    10476  0.0293 libpthread-2.13.so
    10023  0.0281 ntpd
     6288  0.0176 Xorg
     4315  0.0121 libgobject-2.0.so.0.2800.6
     3459  0.0097 libpixman-1.so.0.20.2
     3402  0.0095 libcairo.so.2.11000.2
     2811  0.0079 locale-archive
     2767  0.0077 sshd
     2521  0.0071 libcrypto.so.0.9.8
     1904  0.0053 libgtk-x11-2.0.so.0.2400.4
     1594  0.0045 libORBit-2.so.0.1.0
     1565  0.0044 rsyslogd
     1423  0.0040 libxcb.so.1.1.0
     1235  0.0035 libgdk-x11-2.0.so.0.2400.4
     1207  0.0034 libdbus-1.so.3.5.4 (deleted)
     1197  0.0034 librt-2.13.so
     1075  0.0030 libX11.so.6.3.0
      747  0.0021 mawk
      732  0.0020 sudo
        DCACHE_ACCESS:500|
          samples|      %|
        ------------------
              698 95.3552 sudo
               18  2.4590 [heap] (tgid:32384 range:0x2d000-0x53000)
               16  2.1858 [heap] (tgid:32535 range:0x2d000-0x53000)
      691  0.0019 libgio-2.0.so.0.2800.6
      567  0.0016 libm-2.13.so
      512  0.0014 libpango-1.0.so.0.2800.4
      430  0.0012 ophelp
      418  0.0012 libgthread-2.0.so.0.2800.6
      396  0.0011 grep
      385  0.0011 tr
        DCACHE_ACCESS:500|
          samples|      %|
        ------------------
              369 95.8442 tr
                7  1.8182 [heap] (tgid:32627 range:0x18000-0x3b000)
                5  1.2987 [heap] (tgid:32419 range:0x18000-0x3b000)
                4  1.0390 anon (tgid:32419 range:0x402bf000-0x402c2000)
      281 7.9e-04 libfb.so
      169 4.7e-04 dash
      165 4.6e-04 gconfd-2
      151 4.2e-04 libgconf-2.so.4.1.5
      129 3.6e-04 libnss_compat-2.13.so
      114 3.2e-04 libncurses.so.5.7
      111 3.1e-04 libdl-2.13.so
      100 2.8e-04 rtkit-daemon
       96 2.7e-04 libXext.so.6.4.0
       93 2.6e-04 libresolv-2.13.so
       85 2.4e-04 libpangoft2-1.0.so.0.2800.4
       85 2.4e-04 libdbus-glib-1.so.2.1.0
       80 2.2e-04 libgvfscommon.so.0.0.0
       76 2.1e-04 libgcc_s.so.1
       70 2.0e-04 libpopt.so.0.0.0
       65 1.8e-04 libshadow.so
       56 1.6e-04 cron
       53 1.5e-04 libextmod.so
       52 1.5e-04 libXrender.so.1.3.0
       45 1.3e-04 imuxsock.so
       41 1.1e-04 gdm-simple-greeter
       34 9.5e-05 gnome-power-manager
       34 9.5e-05 libpangocairo-1.0.so.0.2800.4
       33 9.2e-05 metacity
       26 7.3e-05 pango-basic-fc.so
       17 4.8e-05 libudev.so.0.11.1
       15 4.2e-05 libselinux.so.1
       13 3.6e-05 rm
       13 3.6e-05 libpam.so.0.82.3
       12 3.4e-05 sleep
        DCACHE_ACCESS:500|
          samples|      %|
        ------------------
                9 75.0000 [heap] (tgid:32534 range:0x15000-0x36000)
                3 25.0000 sleep
       10 2.8e-05 expr
        7 2.0e-05 libmurrine.so
        6 1.7e-05 libnss_dns-2.13.so
        4 1.1e-05 libnsl-2.13.so
        4 1.1e-05 libutil-2.13.so
        4 1.1e-05 libdbe.so
        3 8.4e-06 libnss_nis-2.13.so
        1 2.8e-06 cat
        1 2.8e-06 seq
user41@ca9-natty:~/seti_boinc/client$ 

```

```
user41@ca9-natty:~/seti_boinc/client$ opreport -l /home/user41/seti_boinc/client/seti_boinc
Overflow stats not available
CPU: ARM Cortex-A9, speed 0 MHz (estimated)
Counted DCACHE_ACCESS events (Data R/W from cache) with a unit mask of 0x00 (No unit mask) count 500
samples  %        symbol name
6922454  32.2378  top_sum2(float**, PoTPlan*)
4978590  23.1852  top_sum3(float**, PoTPlan*)
4154442  19.3472  top_sum4(float**, PoTPlan*)
3751867  17.4724  top_sum5(float**, PoTPlan*)
230372    1.0728  strchr
210532    0.9804  find_pulse(float const*, int, float, int, int)
195005    0.9081  Laligned
171753    0.7999  t_funct(int, int, int)
109277    0.5089  sw_sum2_t31(float**, PoTPlan*)
63556     0.2960  cftmdl(int, int, float*, float*)
59700     0.2780  __ieee754_log
42494     0.1979  malloc
41278     0.1922  cft1st(int, float*, float*)
41231     0.1920  v_BaseLineSmooth(float (*) [2], int, int, int)
39521     0.1840  free
26031     0.1212  GetFixedPoT(float*, int, int, float*, int, int)
24644     0.1148  FindSpikes(float*, int, int, SETI_WU_INFO&)
21947     0.1022  memcpy
21732     0.1012  _int_malloc
20287     0.0945  v_GetPowerSpectrum(float (*) [2], float*, int)
15897     0.0740  bitrv2(int, int*, float*)
15790     0.0735  gettimeofday
14503     0.0675  logl
14012     0.0653  GenChirpFftPairs(ChirpFftPair_t**, double*)
13220     0.0616  seti_analyze(ANALYSIS_STATE&)
12669     0.0590  analyze_pot(float*, int, ChirpFftPair_t&)
12196     0.0568  find_triplets(float const*, int, float, int, int)
11811     0.0550  isnanl
11637     0.0542  _int_free
10118     0.0471  bitrv2conj(int, int*, float*)
10013     0.0466  time_to_ra_dec(double, double*, double*)
9431      0.0439  timer_handler()
9132      0.0425  ReportPulseEvent(float, float, float, int, int, float, float, float*, int, int)
9079      0.0423  workunit_grp::workunit_grp()
7913      0.0369  spike::spike()
7809      0.0364  cftbsub(int, float*, float*)
7483      0.0348  __default_sa_restorer_v2
6602      0.0307  receiver_config::receiver_config()
6437      0.0300  analysis_config::analysis_config()
5774      0.0269  lcgf(double, double)
5095      0.0237  boinc_sleep(double)
4999      0.0233  calc_detection_freq(double, double, double)
4927      0.0229  __ieee754_log10
4923      0.0229  dtime()
4497      0.0209  timer_thread(void*)
4408      0.0205  splitter_config::splitter_config()
4275      0.0199  malloc_consolidate
3957      0.0184  SPIKE_INFO::~SPIKE_INFO()
3882      0.0181  data_description_t::data_description_t()
3824      0.0178  workunit_header::workunit_header()
3748      0.0175  cdft(int, int, float (*) [2], int*, float*)
3614      0.0168  worker_signal_handler(int)
3604      0.0168  result::result()
3534      0.0165  operator new(unsigned int)
3462      0.0161  __divsi3
3220      0.0150  _ZN7sqlblobIfEC2EPKfj16tag_xml_encoding.clone.337
3097      0.0144  std::_Rb_tree_insert_and_rebalance(bool, std::_Rb_tree_node_base*, std::_Rb_tree_node_base*, std::_Rb_tree_node_base&)
3050      0.0142  GetProgressUnitSize(int, int)
3001      0.0140  recorder_config::recorder_config()
2739      0.0128  operator delete(void*)
2513      0.0117  cnvt_bin_hz(int, int)
2328      0.0108  nanosleep
2279      0.0106  .divsi3_skip_div0_test
2237      0.0104  ComputePoTInfo(int, int)
2226      0.0104  log10l
2208      0.0103  memset
2191      0.0102  GetPulsePoTLen(long, int*, int*)
2181      0.0102  tape::tape()
1946      0.0091  cftfsub(int, float*, float*)
1829      0.0085  invert_lcgf(float, float, float)
1800      0.0084  SpikeProgressUnits(int)
1773      0.0083  std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_insert_unique_(std::_Rb_tree_const_iterator<std::pair<long long const, ChirpFftPair_t> >, std::pair<long long const, ChirpFftPair_t> const&)
1535      0.0071  _ZN7sqlblobI12coordinate_tEC2EPKS0_j16tag_xml_encoding.clone.343
1531      0.0071  std::_Rb_tree_increment(std::_Rb_tree_node_base*)
1517      0.0071  std::_Rb_tree_decrement(std::_Rb_tree_node_base*)
1512      0.0070  __libc_enable_asynccancel
1485      0.0069  fraction_done(double, double)
1435      0.0067  __libc_disable_asynccancel
1434      0.0067  subband_description_t::subband_description_t()
1353      0.0063  SPIKE_INFO::SPIKE_INFO()
1313      0.0061  usleep
1292      0.0060  pulse::pulse()
1286      0.0060  __ieee754_fmod
1239      0.0058  std::_Rb_tree<long long, std::pair<long long const, ChirpFftPair_t>, std::_Select1st<std::pair<long long const, ChirpFftPair_t> >, std::less<long long>, std::allocator<std::pair<long long const, ChirpFftPair_t> > >::_M_erase(std::_Rb_tree_node<std::pair<long long const, ChirpFftPair_t> >*)
1227      0.0057  std::vector<unsigned char, std::allocator<unsigned char> > x_setiathome_decode<unsigned char>(char const*, unsigned int)
1108      0.0052  _int_memalign
992       0.0046  memalign
962       0.0045  _ZN7sqlblobI17chirp_parameter_tEC2EPKS0_j16tag_xml_encoding.clone.342
934       0.0043  floor
891       0.0041  __aeabi_d2ulz
844       0.0039  __fixdfdi
779       0.0036  fmodl
691       0.0032  __kernel_cosf
589       0.0027  getrusage
475       0.0022  PULSE_INFO::~PULSE_INFO()
442       0.0021  boinc_fraction_done
427       0.0020  PULSE_INFO::PULSE_INFO()
381       0.0018  calloc_a(unsigned int, unsigned int, unsigned int)
320       0.0015  std::vector<unsigned char, std::allocator<unsigned char> >::_M_fill_insert(__gnu_cxx::__normal_iterator<unsigned char*, std::vector<unsigned char, std::allocator<unsigned char> > >, unsigned int, unsigned char const&)
314       0.0015  sincosf
295       0.0014  _ZN7sqlblobIhEC2EPKhj16tag_xml_encoding.clone.336
261       0.0012  std::local_Rb_tree_rotate_left(std::_Rb_tree_node_base*, std::_Rb_tree_node_base*&)
193      9.0e-04  __kernel_sinf
174      8.1e-04  ____libc_enable_asynccancel_veneer
167      7.8e-04  __aeabi_uidivmod
149      6.9e-04  bits_to_floats(unsigned char*, float (*) [2], int)
140      6.5e-04  PulseProgressUnits(double, int)
121      5.6e-04  __mpn_divrem
107      5.0e-04  __udivsi3
101      4.7e-04  ___printf_fp
99       4.6e-04  std::_Rb_tree_decrement(std::_Rb_tree_node_base const*)
96       4.5e-04  GaussianProgressUnits()
95       4.4e-04  __ieee754_exp
87       4.1e-04  TripletProgressUnits()
85       4.0e-04  GaussFit(float*, int, int)
84       3.9e-04  makewt(int, int*, float*)
81       3.8e-04  __mpn_mul_1
77       3.6e-04  std::local_Rb_tree_rotate_right(std::_Rb_tree_node_base*, std::_Rb_tree_node_base*&)
65       3.0e-04  ChirpProgressUnits()
38       1.8e-04  __libc_do_syscall
36       1.7e-04  free_a(void*)
33       1.5e-04  std::basic_ostream<char, std::char_traits<char> >& std::__ostream_insert<char, std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*, int)
32       1.5e-04  hack_digit.11570
32       1.5e-04  malloc_a(unsigned int, unsigned int)
31       1.4e-04  exp
28       1.3e-04  vfprintf
21       9.8e-05  std::basic_streambuf<char, std::char_traits<char> >::xsputn(char const*, int)
20       9.3e-05  Llastword
18       8.4e-05  std::ostreambuf_iterator<char, std::char_traits<char> > std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::_M_insert_float<double>(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, char, double) const
16       7.5e-05  __dynamic_cast
16       7.5e-05  uselocale
15       7.0e-05  coordinate_t::print_xml(int, int, int, char const*) const
14       6.5e-05  strlen
13       6.1e-05  std::type_info::operator==(std::type_info const&) const
12       5.6e-05  open
12       5.6e-05  pulse::operator=(pulse const&)
10       4.7e-05  analysis_config::operator=(analysis_config const&)
10       4.7e-05  std::_Rb_tree_increment(std::_Rb_tree_node_base const*)
9        4.2e-05  f_GetPeakScaleFactor(float)
9        4.2e-05  receiver_config::operator=(receiver_config const&)
9        4.2e-05  std::ostream& std::ostream::_M_insert<double>(double)
9        4.2e-05  workunit_grp::operator=(workunit_grp const&)
8        3.7e-05  __strcpy_chk
7        3.3e-05  _IO_setb
7        3.3e-05  __mpn_rshift
6        2.8e-05  _IO_default_xsputn
6        2.8e-05  _IO_un_link
6        2.8e-05  __cxxabiv1::__vmi_class_type_info::__do_dyncast(int, __cxxabiv1::__class_type_info::__sub_kind, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info::__dyncast_result&) const
6        2.8e-05  boinc_fopen
6        2.8e-05  xml_indent(int)
5        2.3e-05  _IO_doallocbuf
5        2.3e-05  _IO_link_in
5        2.3e-05  boinc_resolve_filename_s(char const*, std::string&)
5        2.3e-05  checkpoint(unsigned char)
5        2.3e-05  floorf
5        2.3e-05  mmap
5        2.3e-05  munmap
5        2.3e-05  recorder_config::operator=(recorder_config const&)
5        2.3e-05  sqlblob<unsigned char>::operator=(sqlblob<unsigned char> const&)
5        2.3e-05  std::__convert_from_v(__locale_struct* const&, char*, int, char const*, ...)
5        2.3e-05  std::basic_string<char, std::char_traits<char>, std::allocator<char> >::~basic_string()
5        2.3e-05  std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > >::do_put(std::ostreambuf_iterator<char, std::char_traits<char> >, std::ios_base&, char, double) const
5        2.3e-05  std::string::_Rep::_S_create(unsigned int, unsigned int, std::allocator<char> const&)
5        2.3e-05  std::string::_S_construct(unsigned int, char, std::allocator<char> const&)
5        2.3e-05  vsnprintf
4        1.9e-05  MFILE::MFILE()
4        1.9e-05  _IO_getline_info
4        1.9e-05  _IO_new_file_fopen
4        1.9e-05  __pthread_disable_asynccancel
4        1.9e-05  bool std::has_facet<std::num_get<char, std::istreambuf_iterator<char, std::char_traits<char> > > >(std::locale const&)
4        1.9e-05  fclose
4        1.9e-05  memchr
4        1.9e-05  read
4        1.9e-05  strstr
3        1.4e-05  __mpn_cmp
3        1.4e-05  boinc_time_to_checkpoint
3        1.4e-05  data_description_t::operator=(data_description_t const&)
3        1.4e-05  fgets
3        1.4e-05  std::__num_base::_S_format_float(std::ios_base const&, char*, char)
3        1.4e-05  std::basic_ostream<char, std::char_traits<char> >& std::operator<< <std::char_traits<char> >(std::basic_ostream<char, std::char_traits<char> >&, char const*)
3        1.4e-05  std::basic_string<char, std::char_traits<char>, std::allocator<char> >::basic_string(unsigned int, char, std::allocator<char> const&)
3        1.4e-05  std::basic_stringbuf<char, std::char_traits<char>, std::allocator<char> >::overflow(int)
3        1.4e-05  std::locale::id::_M_id() const
3        1.4e-05  std::num_get<char, std::istreambuf_iterator<char, std::char_traits<char> > > const& std::use_facet<std::num_get<char, std::istreambuf_iterator<char, std::char_traits<char> > > >(std::locale const&)
3        1.4e-05  std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > > const& std::use_facet<std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > > >(std::locale const&)
3        1.4e-05  std::string::_M_mutate(unsigned int, unsigned int, unsigned int)
3        1.4e-05  std::string::assign(char const*, unsigned int)
3        1.4e-05  strchrnul
3        1.4e-05  strcmp
2        9.3e-06  PULSE_INFO::operator=(PULSE_INFO const&)
2        9.3e-06  _IO_file_doallocate
2        9.3e-06  _IO_new_file_seekoff
2        9.3e-06  _IO_new_file_xsputn
2        9.3e-06  __cxxabiv1::__si_class_type_info::__do_dyncast(int, __cxxabiv1::__class_type_info::__sub_kind, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info const*, void const*, __cxxabiv1::__class_type_info::__dyncast_result&) const
2        9.3e-06  bool std::has_facet<std::num_put<char, std::ostreambuf_iterator<char, std::char_traits<char> > > >(std::locale const&)
2        9.3e-06  char* std::string::_S_construct<char*>(char*, char*, std::allocator<char> const&, std::forward_iterator_tag)
2        9.3e-06  fcntl
2        9.3e-06  initialize_for_wu()
2        9.3e-06  result::operator=(result const&)
2        9.3e-06  std::basic_ios<char, std::char_traits<char> >::_M_cache_locale(std::locale const&)
2        9.3e-06  std::basic_stringbuf<char, std::char_traits<char>, std::allocator<char> >::_M_sync(char*, unsigned int, unsigned int)
2        9.3e-06  std::ctype<char> const& std::use_facet<std::ctype<char> >(std::locale const&)
2        9.3e-06  std::locale::_S_initialize()
2        9.3e-06  std::locale::locale()
2        9.3e-06  std::string::_Rep::_M_clone(std::allocator<char> const&, unsigned int)
2        9.3e-06  tape::operator=(tape const&)
1        4.7e-06  MFILE::open(char const*, char const*)
1        4.7e-06  _IO_default_uflow
1        4.7e-06  _IO_file_seek
1        4.7e-06  _IO_file_stat
1        4.7e-06  _IO_new_file_close_it
1        4.7e-06  _IO_new_file_init
1        4.7e-06  _IO_no_init
1        4.7e-06  _IO_str_init_static_internal
1        4.7e-06  __fopen_internal
1        4.7e-06  __fxstat64
1        4.7e-06  __mpn_extract_double
1        4.7e-06  bool std::has_facet<std::ctype<char> >(std::locale const&)
1        4.7e-06  char* std::string::_S_construct<char const*>(char const*, char const*, std::allocator<char> const&, std::forward_iterator_tag)
1        4.7e-06  fwrite
1        4.7e-06  memmove
1        4.7e-06  parse_str(char const*, char const*, char*, int)
1        4.7e-06  parse_str(char const*, char const*, std::string&)
1        4.7e-06  seti_init_state()
1        4.7e-06  std::basic_string<char, std::char_traits<char>, std::allocator<char> >::basic_string(char const*, std::allocator<char> const&)
1        4.7e-06  std::basic_stringbuf<char, std::char_traits<char>, std::allocator<char> >::str() const
1        4.7e-06  std::ios_base::_M_init()
1        4.7e-06  std::ios_base::ios_base()
1        4.7e-06  std::ios_base::~ios_base()
1        4.7e-06  std::locale::operator=(std::locale const&)
1        4.7e-06  std::locale::~locale()
1        4.7e-06  std::ostream::sentry::sentry(std::ostream&)
1        4.7e-06  std::string x_xml_values_encode<coordinate_t>(coordinate_t const*, unsigned int)
1        4.7e-06  std::string::_M_replace_safe(unsigned int, unsigned int, char const*, unsigned int)
1        4.7e-06  strcpy
1        4.7e-06  subband_description_t::operator=(subband_description_t const&)
1        4.7e-06  workunit_header::operator=(workunit_header const&)
user41@ca9-natty:~/seti_boinc/client$

```




&lt;script type="text/javascript" src="//ajax.googleapis.com/ajax/static/modules/gviz/1.0/chart.js"&gt;

 {"dataSourceUrl":"//docs.google.com/spreadsheet/tq?key=0AmQeO7G668E3dHd6VU16X3lqMWhST1hIRk9namN1blE&transpose=1&headers=-1&range=A30%3AG31&gid=6&pub=1","options":{"vAxes":[{"min":null,"title":null,"max":null}],"hAxis":{"maxAlternation":1},"hasLabelsColumn":true,"isStacked":false,"width":600,"height":371},"state":{},"chartType":"ColumnChart","chartName":"Chart 1"} 

&lt;/script&gt;

