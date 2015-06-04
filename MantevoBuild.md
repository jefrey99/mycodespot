# How I built Sandia's Mantevo benchmark for multiple platforms #

Add your content here.


# Details #

```

Install mpich2

sudo apt-get install mpich2
sudo apt-get install build-essential
chmod 600 .mpd.conf

miniFE:

1) change makefile to add optimization flags for the cortex-a9

ARM Cortex-A9
CFLAGS = -O3 -mtune=cortex-a9 -mfpu=neon
CXXFLAGS = -O3 -mtune=cortex-a9 -mfpu=neon

ARM Cortex-A8
CFLAGS = -O3 -mtune=cortex-a8 -mfpu=neon
CXXFLAGS = -O3 -mtune=cortex-a8 -mfpu=neon

On Intel Atom

CFLAGS = -O3 -mtune=atom
CXXFLAGS = -O3 -mtune=atom

On Intel Core i3 (Nehalem)

CFLAGS = -O3 -mtune=core2
CXXFLAGS = -O3 -mtune=core2

2) type "make"

3) run $ mpirun -np 2 ./miniFE.x 

beam:

1) run "configure" and add the compiler flags for ARM cortex-A9

./configure CXXFLAGS= "-O3 -mtune=cortex-a9 -mfpu=neon" CFLAGS="-O3 -mtune=cortex-a9 -mfpu=neon"


2) type "make"
Error - Missing file "fei_iostream.hpp"

HPCCG:

1) change "Makefile"

CPP_OPT_FLAGS = -O3 -funroll-all-loops -malign-double -mtune=cortex-a9 -mfpu=neon

on Cortex-A8
CPP_OPT_FLAGS = -O3 -funroll-all-loops -malign-double -mtune=cortex-a8 -mfpu=neon


on Core i3:

CPP_OPT_FLAGS = -O3 -funroll-all-loops -malign-double -mtune=core2

2) type "make"

3) run $ mpirun -np 2 ./test_HPCCG  20 30 10


pHPCCG:
1) change "Makefile" to:
CPP_OPT_FLAGS = -O3 -funroll-all-loops -mtune=cortex-a9 -mfpu=neon

Cortex-A8
CPP_OPT_FLAGS = -O3 -funroll-all-loops -mtune=cortex-a8 -mfpu=neon
corei3:

CPP_OPT_FLAGS = -O3 -funroll-all-loops -mtune=core2

2) type "make"

3) run "$ mpirun -np 2 ./test_pHPCCG 20 30 10 "


miniMD
1) $ make
2) change "Makefile.mpicxx" and add:

ARM: (CCFLAGS?)
CFLAGS = -O3 -funroll-all-loops -mtune=cortex-a9 -mfpu=neon

CCFLAGS =	-O3 -funroll-all-loops -mtune=cortex-a8 -mfpu=neon -DMPICH_IGNORE_CXX_SEEK

corei3:
CCFLAGS =	-O3 -funroll-all-loops -mtune=core2 -DMPICH_IGNORE_CXX_SEEK

Atom:
CCFLAGS =	-O3 -funroll-all-loops -mtune=atom -DMPICH_IGNORE_CXX_SEEK


3) $ make clean_mpicxx
4) $ make mpicxx
5) $ mpirun -np 2 ./miniMD_mpicxx

miniMD (single precison)
1) $ make
2) change "Makefile.mpicxx" and add:

ARM: (CCFLAGS?)
CCFLAGS =	-O3 -funroll-all-loops -mtune=cortex-a9 -mfpu=neon -DMPICH_IGNORE_CXX_SEEK

CCFLAGS =	-O3 -funroll-all-loops -mtune=cortex-a8 -mfpu=neon -DMPICH_IGNORE_CXX_SEEK

corei3:
CCFLAGS =	-O3 -funroll-all-loops -mtune=core2 -DMPICH_IGNORE_CXX_SEEK


Atom:
CCFLAGS =	-O3 -funroll-all-loops -mtune=atom -DMPICH_IGNORE_CXX_SEEK


3) $ make clean_mpicxx
4) $ make mpicxx
5) $ mpirun -np 2 ./miniMD_mpicxx

phdMesh: (make dir before untar)

./configure --with-cxxflags=-O3 --with-cxxflags-mtune=cortex-a9 --with-cxxflags-mfpu=vfpv3 --with-cflags=-O3 --with-cflags=-mtune=cortex-a9 --with-cflags=-mfpu=vfpv3

corei3
./configure --with-cxxflags=-O3 --with-cxxflags-mtune=core2 --with-cflags=-O3 --with-cflags=-mtune=core2



EpetraBenchmarkTest:

./configure -C CXXFLAGS="-O3 -funroll-all-loops -mtune=cortex-a9 -mfpu=vfpv3" CFLAGS="-O3 -funroll-all-loops -mtune=cortex-a9 -mfpu=vfpv3" FFLAGS="-O5 -funroll-all-loops" --prefix=/home/mheroux/trilinos-7.0.9/EPETRA_OPT --enable-mpi --with-mpi-compilers --disable-default-packages --disable-tests --disable-examples --enable-epetra --with-gnumake

```