### Quick and dirty port to Mac of the posixshmcontrol utility
- Ripped from https://github.com/freebsd/freebsd/tree/master/usr.bin/posixshmcontrol
- tested on Mojave and built with XCode 10.3

Problems:
- The ls subcommand doesn't work because the Mac kernel doesn't support it.
- disabled humanized formatting of numbers (ie appending K, M, G etc) because I couldn't immediately find stdutil.h anywhere.  Although the dylib exists so maybe it can be made to work.
