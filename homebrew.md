Conda/Macports/Homebrew may conficts with each other. Choose one of them and stick to it.
If you are using Homebrew for ISCE installation (works for 2.1.0 and 2.2.0)...

Some helpful notes:
1. make sure brew-installed python are linked correctly 
2. make sure brew-installed gcc are linked correctly
3. for c++ libraries, use brew ones in "/usr/local/Cellar*" instead of "/usr/local/gfortran/lib"
4. before do "scons install", delete your build folder "\rm -rf config.log .sconsign.dblite .sconf_temp build/", also delete your install folder (important, sometimes if the files exists it will not overwrite)
5. install scipy using "pip3 install scipy"

Below are my SConfigISCE file:

PRJ_SCONS_BUILD=/Users/yuexinli/ISCE/ISCE_SRC/isce-2.2.0/build
PRJ_SCONS_INSTALL=/Users/yuexinli/ISCE/isce_201808/isce

LIBPATH=/usr/local/lib /opt/X11/lib /usr/local/Cellar/gcc@6/6.4.0_2/lib/gcc/6
CPPPATH=/usr/local/Cellar/python/3.7.0/Frameworks/Python.framework/Versions/3.7/include/python3.7m /usr/local/include /opt/X11/include
FORTRANPATH=/usr/local/include 

FORTRAN=/usr/local/bin/gfortran-6
CC=/usr/local/bin/gcc-6
CXX=/usr/local/bin/g++-6

MOTIFLIBPATH=/usr/local/lib
MOTIFINCPATH=/usr/local/include
X11LIBPATH=/opt/X11/lib
X11INCPATH=/opt/X11/include
