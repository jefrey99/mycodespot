## Setup sequence to configure and run SPEC on ARMv7 with NEON ##

first download spec



```
$ tar -jxvf cpu2006.v1.1.tar.bz2
```

### The SPEC Tool Set ###


| **SPEC Tool** | **Description** |
|:--------------|:----------------|
|specdiff       |examines results to see if the correct answer was obtained|
|specinvoke     |invokes benchmarks for CPU2006|
|specmake       |GNU make (Calling it "specmake" avoids possible conflicts with versions of make that may already be on your system. SPEC requires that published results use the versions of the tools that it supplies, so that if SPEC applies patches or extensions from time to time, all users run with a consistent tool set. Similar considerations apply to other tools in this list.)|
|specbzip2      |Julian Seward's bzip2|
|specmd5sum     |md5sum from GNU textutils, with enhancements|
|spectar        |GNU tar          |
|specperl       |Perl             |

### Building the toolset ###
SPEC does not include ARM binaries, as such they will need to be built.

  * First apply this patch to fix the problem in the tools sources. All other systems where builds were done silently ignored the problem but on my build system it is strict.  This patch should fix it:
```
Index: specinvoke/unix.c

===================================================================
--- specinvoke/unix.c	(revision 1385)
+++ specinvoke/unix.c	(working copy)
@@ -124,7 +124,7 @@
 		fprintf (stderr, "Can't create zero-length temporary filename\n ");
 		specinvoke_exit (1, si);
 	      }
-	      infd = open(tmpfile, O_RDWR|O_CREAT|O_TRUNC);
+	      infd = open(tmpfile, O_RDWR|O_CREAT|O_TRUNC, 0666);
 	      if (infd < 0) {
 		fprintf (stderr, "Can't create %s for stdin: %s(%d)\n",
 			 tmpfile, STRERROR(errno), errno);


```
  * Then this patch
```
diff -ur orig/tools/src/perl-5.8.8/makedepend.SH t/tools/src/perl-5.8.8/makedepend.SH
--- orig/tools/src/perl-5.8.8/makedepend.SH     2008-04-03 13:15:08.000000000 -0400
+++ debug/tools/src/perl-5.8.8/makedepend.SH    2011-12-13 17:30:56.000000000 -0500
@@ -21,7 +21,8 @@
 echo "Extracting makedepend (with variable substitutions)"
 rm -f makedepend
 $spitshell >makedepend <<!GROK!THIS!
-$startsh
+$startsh -x
+set -x
 # makedepend.SH
 #
 MAKE=$make
```
  * Run this script
    * The problem in a nutshell is that standard libraries aren't in standard locations, so this tells Perl's Configure to look in the same places that GCC already knows to look. (say setup.sh)
```
#!/bin/bash
PERLFLAGS=-Uplibpth=
for i in `gcc -print-search-dirs | grep libraries | cut -f2- -d= | tr ':' '\n' | grep -v /gcc`; do
  PERLFLAGS="$PERLFLAGS -Aplibpth=$i"
done
export PERLFLAGS
echo $PERLFLAGS


```
  * Now build the tools
```
$ cd $SPEC/tools/src/
$ export CFLAGS="-O2 -mtune=cortex-a9 -mfpu=neon"
$ ./setup.sh
$ ./buildtools
```

  * **Notes**
    * I had build issues if I forgot to set the current system time / date
