# Git commands #

### building mx5 kernel from git repo ###
```
$ git clone git://sw-git.freescale.net/linux-2.6-imx.git
$ export CROSS_COMPILE=/opt/freescale/usr/local/gcc-4.4.4-glibc-2.11.1-multilib-1.0/arm-fsl-linux-gnueabi/bin/arm-none-linux-gnueabi-
$ cd linux-2.6-imx/
$ git checkout -b 2.6.38 --track origin/imx_2.6.38
$ make ARCH=arm CROSS_COMPILE=${CROSS_COMPILE} distclean
$ make ARCH=arm CROSS_COMPILE=${CROSS_COMPILE} imx5_defconfig
$ make ARCH=arm CROSS_COMPILE=${CROSS_COMPILE} menuconfig
make ARCH=arm CROSS_COMPILE=${CROSS_COMPILE} uImage
```
load to SD
```
$ sudo dd if=uImage of=/dev/sdx bs=512 seek=2048 &sync
```
pull in the latest source
```
linux-2.6-imx$ git fetch
linux-2.6-imx$ git rebase origin/imx_2.6.38
```