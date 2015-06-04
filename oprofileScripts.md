# Some oprofile scripts #

```
#!/bin/bash
SleepSeconds=15

sudo opcontrol --init
sudo opcontrol --reset
sudo opcontrol --no-vmlinux
sudo opcontrol --list-events
sudo opcontrol --status

#      Choose an event. May be specified multiple times. Of the form
#      "default" or "name:count:unitmask:kernel:user", where :
#
#      name:     event name, e.g. CPU_CLK_UNHALTED or RTC_INTERRUPTS
#      count:    reset counter value e.g. 100000
#      unitmask: hardware unit mask e.g. 0x0f
#      kernel:   whether to profile kernel: 0 or 1
#      user:     whether to profile userspace: 0 or 1

sudo opcontrol --start
sudo opcontrol --status
sleep $SleepSeconds

# do stuff you want profiled for SleepSeconds=15

sudo opcontrol --stop
sudo opcontrol --dump
opreport -lt1
sudo opcontrol --shutdown
sudo opcontrol --deinit
```