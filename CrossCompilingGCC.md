# Using Codesourcery Toolchain #

Quick guide to cross compile source code for ARM


# Details #


  1. Download toolchain from mentor
  1. Open terminal (This assumes linux)
  1. Install 32 bit libraries if needed
```
$ sudo apt-get install ia32-libs
```
  1. Install Sourcery Code bench
```
$ sudo dpkg-reconfigure -plow dash
$ ./sourceryg++-2012.03-47-arm-none-linux-gnueabi.bin
```

  1. Set up environment variables and add tools to the Linux host path
```
$ export CROSS_COMPILE=arm-none-linux-gnueabi-
$ export PATH=/home/jeff/toolchains/Sourcery_CodeBench_for_ARM_GNU_Linux/bin:$PATH
```