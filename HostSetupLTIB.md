## Setting up your host ##

Use this script to install host dependencies for LTIB
```
#!/bin/bash
# Install packages needed by LTIB
sudo aptitude -y install gettext libgtk2.0-dev rpm bison m4 libfreetype6-dev
sudo aptitude -y install libdbus-glib-1-dev liborbit2-dev intltool
sudo aptitude -y install ccache ncurses-dev zlib1g zlib1g-dev gcc g++ libtool
sudo aptitude -y install uuid-dev liblzo2-dev
sudo aptitude -y install tcl dpkg
# Packages required for 64-bit Ubuntu
# Do "uname -a" and see if the word "x86_64" shows up.
if uname -a|grep -sq 'x86_64'; then
sudo aptitude -y install ia32-libs libc6-dev-i386 lib32z1
fi
# The following recommended for Linux development.
# They are not required by LTIB.
sudo aptitude -y install gparted emacs22-nox openssh-server
sudo aptitude -y install nfs-common nfs-kernel-server lintian
sudo aptitude -y install git-core git-doc git-email git-gui gitk
sudo aptitude -y install diffstat indent tofrodos fakeroot doxygen uboot-mkimage
sudo aptitude -y install sendmail mailutils meld atftpd sharutils
sudo aptitude -y install manpages-dev manpages-posix manpages-posix-dev linux-doc
sudo aptitude -y install vnc4server xvnc4viewer
```