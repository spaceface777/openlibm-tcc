## OpenLibm-tcc


### Building
Since this fork is specific to tcc on Windows, building it is now much simpler, and we do not need in makefiles or similar anymore.
```sh
$ tcc -O3 -Iinclude -Isrc -r -o openlibm.o src/*.c
```

If you want a `.dll` (dynamically linked):
```sh
$ tcc -O3 -Iinclude -Isrc -shared -o openlibm.dll src/*.c
```

The original README is attached below.

## OpenLibm

OpenLibm is an effort to have a high quality, portable, standalone
C mathematical library ([`libm`](http://en.wikipedia.org/wiki/libm)).
It can be used standalone in applications and programming language
implementations. 

The project was born out of a need to have a good `libm` for the
[Julia programming langage](http://www.julialang.org) that worked
consistently across compilers and operating systems, and in 32-bit and
64-bit environments.

### History

The OpenLibm code derives from the [FreeBSD
msun](http://svnweb.freebsd.org/base/head/lib/msun/) implementation,
which in turn derives from [FDLIBM
5.3](http://www.netlib.org/fdlibm/). As a result, it includes a number
of fixes and updates to FDLIBM that have accumulated over the years in
`msun`, and optimized versions of many functions.

### Platform support

OpenLibm builds on Linux, Mac OS X, and Windows, and with little
effort, should build on FreeBSD as well. It builds with both GCC and
clang. Although largely tested on x86, it also includes experimental
support for ARM. The original `msun` also includes support for mips,
sparc64, powerpc, ia64, and alpha. These are present in the OpenLibm
source tree, but no attempt has been made to build any of these.

### Build instructions

1. `make` or `make USEGCC=1` to build with GCC. This is the default on
   Linux and Windows.  
2. `make USECLANG=1` to build with clang. This is the default on OS X.
