# Script Example ##!/bin/bash
# iMX53 - ARM Cortex A8 Oprofile Script
SleepSeconds=180 #profiles for 180 seconds

sudo rm -r /var/lib/oprofile
sudo rm -r /root/.oprofile/daemonrc

# Running next event
sudo opcontrol --init
sudo opcontrol --vmlinux=/home/lucid/vmlinux-2.6.38-00462-gc38d9c7-dirty
sudo opcontrol --reset
sudo opcontrol --event=CPU_CYCLES:200000:0x0:0:1 --event=INSTR_EXECUTED:200000:0x0:0:1 --event=L2_ACCESS:200000:0x0:0:1 --event=L2_CACH_MISS:200000:0x0:0:1
sudo opcontrol --start
sudo opcontrol --status
// Do Stuff Here
sleep $SleepSeconds
sudo opcontrol --dump
date >> mx53_Oprofile.txt
sudo opreport >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt
sudo opreport -l /home/" path to profiled binary" >> mx53_Oprofile.txt
sudo opcontrol --shutdown
echo " " >> mx53_Oprofile.txt
echo " " >> mx53_Oprofile.txt

}}```