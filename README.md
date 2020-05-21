# NCEPLIBS G2 Library

Utilities for coding/decoding GRIB2 messages. This library
contains Fortran 90 decoder/encoder routines for GRIB edition 2,
as well as indexing/searching utility routines. 
For more detailed documentation see (grib2.doc)

Code Manager : Boi Vuong

# How to build and install G2 library
=====================================

### Installation using CMake
CMake version 3.12 or newer. 
This is the recommended method of installation.

### Prerequisites

Compilers: GNU | Intel | Clang | AppleClang 

### Installing

1. Download G2 Code from GitHub
git clone -b g2_v3.2.0 https://github.com/NOAA-EMC/NCEPLIBS-g2.git
cd NCEPLIBS-g2

2. Create a directory where to build G2 library
mkdir build
cd build

3. Load the following modules 
module purge
module load intel/18.0.5.274                  
module load impi/2018.0.4
module load cmake/3.16.3
module load jasper/1.900.1
module load libpng/1.2.44  zlib/1.2.11

If the chosen compiler is not the default compiler on the system,
set the environment variables: export CC=..., export CXX=..., 
export FC=..., before invoking cmake.
Note that Windows systems and other compilers (e.g. PGI) are not supported at this time.

export CC=icc
export CXX=icpc
export FC=ifort

4. Run cmake
cmake .. -DCMAKE_INSTALL_PREFIX=path_to_install -DCMAKE_PREFIX_PATH="${PNG_LIBDIR};${PNG_INC};${JASPER_LIBDIR};${JASPER_INC}
make 

If -DCMAKE_INSTALL_PREFIX= is omitted, the libraries will be installed in directory install underneath the build directory.

### Version
3.2.0

### Authors

* **[NCEP/EMC](mailto:NCEP.List.EMC.nceplibs.Developers@noaa.gov)**
