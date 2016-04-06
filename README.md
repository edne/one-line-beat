# One Line Beat
Bash utility to generate [byte-beats](http://canonical.org/~kragen/bytebeat/)
compiling on the fly a single line C program.

Usage
-----
    $ ./olb t
    $ ./olb t*2
    $ ./olb t*(t>>2)
    $ ./olb t*(t>>8)&(t>>13)

and so on...

Than:

    $ ./olb --kill  # or simply -k
