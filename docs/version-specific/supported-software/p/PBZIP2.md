# PBZIP2

PBZIP2 is a parallel implementation of the bzip2 block-sorting  file compressor that uses pthreads and achieves near-linear speedup on SMP  machines. The output of this version is fully compatible with bzip2 v1.0.2 or  newer (ie: anything compressed with pbzip2 can be decompressed with bzip2).  PBZIP2 should work on any system that has a pthreads compatible C++ compiler   (such as gcc). It has been tested on: Linux, Windows (cygwin & MinGW), Solaris,  Tru64/OSF1, HP-UX, OS/2, OSX, and Irix.

*homepage*: <http://compression.great-site.net/pbzip2>

version | toolchain
--------|----------
``1.1.13`` | ``GCCcore/12.3.0``
