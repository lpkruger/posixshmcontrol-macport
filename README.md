### Quick and dirty port to Mac of the posixshmcontrol utility
- Ripped from https://github.com/freebsd/freebsd/tree/master/usr.bin/posixshmcontrol
- tested on Mojave and built with XCode 10.3

Problems:
- The ls subcommand doesn't work and can't work because the Mac kernel doesn't support it.
  - The source code for the Mac Kernel (XNU) Posix SHM shows there is no possible way to export the hashtable of segment names without modifying the kernel:
  - https://github.com/apple/darwin-xnu/blob/master/bsd/kern/posix_shm.c
- The same kernel source code also shows that reading and writing won't work.  The only thing you can is mmap it into the address space.  As a TODO this utility could be modified to support reading and writing through that mechanism.
- disabled humanized formatting of numbers (ie appending K, M, G etc) because I couldn't immediately find stdutil.h anywhere.  Although the dylib exists so maybe it can be made to work.
