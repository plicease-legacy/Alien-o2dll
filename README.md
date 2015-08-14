# Alien::o2dll

Make dynamic link library on Windows (Deprecated)

# SYNOPSIS

From perl:

    use Alien::o2dll qw( o2dll );
    
    o2dll( -o => 'foo.dll', -l => 'otherlib', 'foo.o', '-version-info' => '0:0:0' );

From command line:

    C:\> po2dll -o foo.dll -l otherlib foo.o -version-info 0:0:0

# DESCRIPTION

**Note**: The idea was that I (or someone else) might end up using this somewhere else.
I didn't realize that libbz2 was special, and that there are better ways of doing
this.  Please consider using [Alien::MSYS](https://metacpan.org/pod/Alien::MSYS) or `libtool` or something like that.

o2dll is a shell script that is used in some build scripts used to create DLL files
on Windows.  Installing this module provides a perl interface to that command, as 
well as a command line interface `po2dll` (it has a p prefix so as not to interfere
with o2dll if you have installed it yourself).

# FUNCTIONS

These functions are exported to the callers namespace only by request.

## o2dll

    o2dll( -o => 'foo.dll', -l => 'otherlib', 'foo.o', '-version-info' => '0:0:0' );

Run o2dll with the given arguments.  It will die if there is a failure.

## o2dll\_path

    my $dir = o2dll_path;

Returns the path to the o2dll executable shell script.

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2013 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
