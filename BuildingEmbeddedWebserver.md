## How to build a web server using an embedded system ##

#### What is a webserver ####

A web server is a computer program that delivers (serves) content, such as web pages, using the Hypertext Transfer Protocol (HTTP), over the World Wide Web

#### Why use an embedded processor ####

There are many reasons that you might want a web server running on an i.MX embedded processor. This tutorial will instruct you how to build the neccessary packages with LTIB and configure the device to host a website.

#### Running a LAMP stack on i.MX ####

LAMP is an acronym for a solution stack of free, open source software, originally coined from the first letters of Linux (operating system), Apache HTTP Server, MySQL (database software), and PHP, principal components to build a viable general purpose web server.

#### Adding the LAMP packages to LTIB ####

Adding the packages to LTIB is very easy and should build fine without any issues.
!building\_apache\_LTIB\_cropped.png|align=right,thumbnail!
# Simply reconfigure the BSP with LTIB to add the packages
```
$ ./ltib -c
```
# Now add the following packages to the BSP

  * httpd (Apache webserver)
  * mysql
  * php, python, or perl

#### Starting/Running the Web Server on your i.MX device ####

You simply to need to execute the binary "httpd". Typically, this is done when the system starts up,  you can do this manually from the command line
```
$ /usr/sbin/httpd &
```

You can set up the system to do this automatically at start up in one of the rc files.I suggest starting httpd after most other services have started (i.e.: put it in rc.local).
Edit rc.local and add:
```
/usr/sbin/httpd &
```


#### Test you web server ####

# Find the ip address on your i.MX device
```
$ ifconfig
eth0      Link encap:Ethernet  HWaddr 00:22:19:06:b3:c1
          inet addr:10.81.4.63  Bcast:10.81.7.255  Mask:255.255.252.0
          inet6 addr: fe80::222:19ff:fe06:b3c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:10228404 errors:0 dropped:0 overruns:0 frame:0
          TX packets:3843568 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:3334983106 (3.3 GB)  TX bytes:3344815017 (3.3 GB)
          Interrupt:17
```
# Now open a browser and point to the ip address
```
http://10.81.4.63/
```

**You should see the Apache welcome page**
{note} If you have any issues at this point, remove the proxy setting in your browser or add the i.MX ip address to your exceptions list{note}

#### Configuring apache on i.MX ####

You can find an enormous amount of documentation for configuring Apache webserver on the Apache website http://httpd.apache.org/docs/
Here we will start with the very basic setup.

If you want to point Apache to serve files located in /home/public\_html/ then...
# On the i.MX target cd into the /user/conf directory
```
$ cd /usr/conf
```
# Edit httpd.conf
```
$ vi httpd.conf
```
# Change the following lines:
```
DocumentRoot "/usr/htdocs"
```
to
```
DocumentRoot "home/public_html"
```
and
```
<Directory "/usr/htdocs">
```
to
```
<Directory "home/public_html">
```

#### Adding a secure socket layer (SSL) ####


# In ltib built kernel and fs with minimum configuration - no httpd and no openssl. So if the httpd package is selected then you must first remove it and then rebuild
# Edited httpd spec file to add "--enable-ssl"  to configure arguments
```
$ gedit dist/lfs-5.1/httpd/httpd.spec
```
# Add link in /lib to link libssl.so to libssl.so.0.9.8
```
$ cd /lib
$ ln -s libssl.so.0.9.8 libssl.so
```
# Extract httpd from package pool
```
$  ./ltib -m prep -p httpd
```
# Extract openssl from package pool
```
$  ./ltib -m -prep -p openssl
```

# Link /usr/include/openssl
```
/home/jeff/fsl/10_05/mx51/ltib/rpm/BUILD/openssl-0.9.8g/include/openssl
 $ cd /usr/include
 $ ln -s /home/jeff/fsl/10_05/mx51/ltib/rpm/BUILD/openssl-0.9.8g/include/openssl openssl
```
# Now Patch httpd-2.0.54/modules/ssl/ssl\_toolkit\_compat.h with the the following patch
```
#ifdef OPENSSL_VERSION_NUMBER

+#if (OPENSSL_VERSION_NUMBER >= 0x0090800fL) #ifndef PEM_F_DEF_CALLBACK
+#define PEM_F_DEF_CALLBACK PEM_F_PEM_DEF_CALLBACK #endif #endif
+
/*
 * rsa sslc uses incomplete types for most structures
 * so we macroize for OpenSSL those which cannot be dereferenced
```
{note}This is supposedly fixed in later verstions 2.0.55.{note}
# Build openssl
```
$  ./ltib -m scbuild -p openssl
```
# Deploy openssl
```
$  ./ltib -m scdeploy -p openssl
```
# Build httpd
```
$  ./ltib -m scbuild -p httpd
```
# Deploy httpd
```
$  ./ltib -m scdeploy -p httpd
```