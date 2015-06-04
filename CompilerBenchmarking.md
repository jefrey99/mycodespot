## A quest to find the best compiler for ARM processors ##

This project is to try to get to the bottom of all of the bold claims by compiler developers as to which compiler yeilds the best performance on an ARM Cortex-A9.

#### Compilers to evaluate ####

  * Linaro
  * CodeSourcery
  * GCC
  * ARM

Compiling whetstone with Linaro
```
$ export CFLAGS="-o2 -mtune=cortex-a9 -mfpu=neon"
$ export CROSS_COMPILE=arm-linux-gnueabihf-
$ export PATH=/home/jeff/toolchains/linaro/gcc-linaro-arm-linux-gnueabihf-2012.05-20120523_linux/bin/:$PATH
$ arm-linux-gnueabihf-gcc -o whetstone_arm whetstone.c -lm
$ file whetstone_arm

```