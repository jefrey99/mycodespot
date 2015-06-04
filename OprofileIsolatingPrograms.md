# Profiling Firefox Load #

### Details ###
`opscript.sh`
```
#!/bin/bash
sudo opcontrol --init
sudo opcontrol --vmlinux=/boot/vmlinux-2.6.35.3-850-gbc67621-g91e9da8
sudo opcontrol --start
sudo opcontrol --status
export DISPLAY=:0
firefox www.yahoo.com &
sudo opcontrol --dump
sudo opcontrol --stop
opreport --symbols
#opreport -l /usr/bin/firefox
```

### opreport output ###

```
lucid@lucid-desktop:~$ ./opscript.sh 
Profiler running.
Daemon running: pid 5802
Separate options: none
vmlinux file: /boot/vmlinux-2.6.35.3-850-gbc67621-g91e9da8
Image filter: none
Call-graph depth: 0
Stopping profiling.
Overflow stats not available
CPU: CPU with timer interrupt, speed 0 MHz (estimated)
Profiling through timer interrupt
samples  %        app name                 symbol name
88       16.0584  libxul.so                /usr/lib/firefox-3.6.12/libxul.so
46        8.3942  libmozjs.so              /usr/lib/firefox-3.6.12/libmozjs.so
30        5.4745  bash                     /bin/bash
23        4.1971  ld-2.11.1.so             do_lookup_x
17        3.1022  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 mmc_vddrange_to_ocrmask
16        2.9197  libc-2.11.1.so           strcmp
15        2.7372  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 queue_attr_show
13        2.3723  firefox-bin              /usr/lib/firefox-3.6.12/firefox-bin
12        2.1898  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __flush_dcache_page
9         1.6423  libc-2.11.1.so           _nl_make_l10nflist
9         1.6423  libglib-2.0.so.0.2400.1  /lib/libglib-2.0.so.0.2400.1
8         1.4599  libc-2.11.1.so           _dl_addr
8         1.4599  libc-2.11.1.so           memcpy
8         1.4599  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __iounmap
7         1.2774  libpthread-2.11.1.so     pthread_mutex_lock
6         1.0949  ld-2.11.1.so             __tls_get_addr
5         0.9124  libc-2.11.1.so           strnlen
5         0.9124  libpthread-2.11.1.so     __pthread_mutex_unlock_usercnt
5         0.9124  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 vfp_double_multiply_accumulate
4         0.7299  ld-2.11.1.so             _dl_lookup_symbol_x
4         0.7299  libc-2.11.1.so           __gconv_transform_utf8_internal
4         0.7299  libnspr4.so              /usr/lib/firefox-3.6.12/libnspr4.so
4         0.7299  libsqlite3.so            /usr/lib/firefox-3.6.12/libsqlite3.so
4         0.7299  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 blk_release_queue
4         0.7299  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 default_idle
4         0.7299  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 xscale1pmu_handle_irq
3         0.5474  ld-2.11.1.so             __udivsi3
3         0.5474  ld-2.11.1.so             _dl_map_object
3         0.5474  ld-2.11.1.so             _dl_name_match_p
3         0.5474  ld-2.11.1.so             check_match.8384
3         0.5474  libc-2.11.1.so           getenv
3         0.5474  libc-2.11.1.so           memset
3         0.5474  libc-2.11.1.so           stpcpy
3         0.5474  libc-2.11.1.so           strlen
3         0.5474  libgobject-2.0.so.0.2400.1 /usr/lib/libgobject-2.0.so.0.2400.1
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __dabt_usr
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 hw_perf_event_destroy
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 ll_back_merge_fn
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 param_set_invbool
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 perf_lock_task_context
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 posix_cpu_timer_get
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 rb_advance_reader
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 sys_perf_event_open
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 sys_swapon
3         0.5474  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 vfp_double_fsub
2         0.3650  ld-2.11.1.so             _dl_map_object_from_fd
2         0.3650  ld-2.11.1.so             _dl_relocate_object
2         0.3650  libX11.so.6.3.0          /usr/lib/libX11.so.6.3.0
2         0.3650  libc-2.11.1.so           _int_malloc
2         0.3650  libc-2.11.1.so           malloc
2         0.3650  libgdk-x11-2.0.so.0.2000.1 /usr/lib/libgdk-x11-2.0.so.0.2000.1
2         0.3650  libgtk-x11-2.0.so.0.2000.1 /usr/lib/libgtk-x11-2.0.so.0.2000.1
2         0.3650  libpthread-2.11.1.so     ____pthread_enable_asynccancel_veneer
2         0.3650  libpthread-2.11.1.so     pthread_mutex_unlock
2         0.3650  libxcb.so.1.1.0          /usr/lib/libxcb.so.1.1.0
2         0.3650  python2.6                /usr/bin/python2.6
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 blk_unregister_queue
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 free_unmap_vmap_area_noflush
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 get_swap_page
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 isolate_lru_page
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 putback_lru_page
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shmem_link
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shrink_page_list
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 soc_pcm_prepare
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 truncate_pagecache
2         0.3650  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 unmap_area_sections
1         0.1825  grep                     /bin/grep
1         0.1825  ld-2.11.1.so             __aeabi_read_tp
1         0.1825  ld-2.11.1.so             __sigsetjmp
1         0.1825  ld-2.11.1.so             _dl_check_map_versions
1         0.1825  ld-2.11.1.so             _dl_fixup
1         0.1825  ld-2.11.1.so             _dl_init_internal
1         0.1825  ld-2.11.1.so             _dl_protect_relro
1         0.1825  ld-2.11.1.so             _dl_sort_fini
1         0.1825  ld-2.11.1.so             strcmp
1         0.1825  libc-2.11.1.so           Laligned
1         0.1825  libc-2.11.1.so           __gconv_compare_alias
1         0.1825  libc-2.11.1.so           __udivsi3
1         0.1825  libc-2.11.1.so           _dl_mcount_wrapper_check
1         0.1825  libc-2.11.1.so           _int_free
1         0.1825  libc-2.11.1.so           _nl_find_locale
1         0.1825  libc-2.11.1.so           _nl_normalize_codeset
1         0.1825  libc-2.11.1.so           argz_stringify
1         0.1825  libc-2.11.1.so           ferror
1         0.1825  libc-2.11.1.so           fflush
1         0.1825  libc-2.11.1.so           fork
1         0.1825  libc-2.11.1.so           mbrtowc
1         0.1825  libc-2.11.1.so           memcmp
1         0.1825  libc-2.11.1.so           rawmemchr
1         0.1825  libc-2.11.1.so           strchr
1         0.1825  libc-2.11.1.so           strverscmp
1         0.1825  libc-2.11.1.so           vfprintf
1         0.1825  libcairo.so.2.10800.10   /usr/lib/libcairo.so.2.10800.10
1         0.1825  libexpat.so.1.5.2        /lib/libexpat.so.1.5.2
1         0.1825  libpixman-1.so.0.16.4    /usr/lib/libpixman-1.so.0.16.4
1         0.1825  libpopt.so.0.0.0         /lib/libpopt.so.0.0.0
1         0.1825  libpthread-2.11.1.so     __aeabi_read_tp
1         0.1825  libpthread-2.11.1.so     accept
1         0.1825  librsvg-2.so.2.26.2      /usr/lib/librsvg-2.so.2.26.2
1         0.1825  librt-2.11.1.so          call_gmon_start
1         0.1825  libstdc++.so.6.0.13      /usr/lib/libstdc++.so.6.0.13
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __add_to_swap_cache
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __blk_complete_request
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __do_fault
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __isolate_lru_page
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __pabt_usr
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __purge_vmap_area_lazy
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 __sched_setscheduler
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 add_swap_count_continuation
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 blk_add_timer
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 blk_execute_rq
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 blk_queue_bounce
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 changed_ioprio
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 check_irq_resend
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 check_move_unevictable_page
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 child_wait_callback
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 copy_strings
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 deadline_dispatch_requests
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 deadline_merged_requests
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 do_DataAbort
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 do_mpage_readpage
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 do_sync_write
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 do_syslog
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 get_dcookie
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 get_sb_single
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 gpu_probe
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 gsl_kmod_ioctl
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 inherit_event
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 iov_iter_advance
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 klist_remove
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 kmem_cache_open
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 kmsg_dump_register
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 ll_rw_block
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 mark_files_ro
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 path_init
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 perf_event_task_sched_out
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 perf_set_overcommit
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 pipe_write
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 ptrace_notify
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 queue_max_segment_size_show
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 read_swap_cache_async
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 rfkill_alloc
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 rfkill_register
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 rfkill_set_sw_state
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 search_binary_handler
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shmem_reserve_inode
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shmem_swp_entry
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shmem_truncate_range
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shmem_writepage
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shrink_slab
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 shrink_zone
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 strndup_user
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 thread_group_cputime
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 vector_swi
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 vfs_link
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 wait_consider_task
1         0.1825  vmlinux-2.6.35.3-850-gbc67621-g91e9da8 wakeup_kswapd
lucid@lucid-desktop:~$
```