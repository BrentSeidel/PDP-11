# PDP-11 Assembly Language
This is a collection of routines that I've written in PDP-11 assembly
language.  These are primarily fairly low level I/O and string handling.
The main data structure defined is the string.  It consists of two bytes
representing the maximum and actual length followed by a series of bytes
containing the string.  The routines and data are spread across a number
of files.

## FILES.MAC
This file contains routines relating to the RSTS/E file system.

## GLOBAL.MAC
This file contains global data that is used by some of the routines.

## MACROS.MAC
†his contains a series of macros that wrap the various functions and
provide, perhaps, a more convenient way of calling them.  The macros
take care of putting parameters on the stack and cleaning up the stack
afterwards.  Two additional macros are provided for strings: "text" for
defining a text string, and "string" for defining a string variable.

The macros defined are:
* put - Low level write data to console
* puts - Writes a string to console
* gets - Gets a string from console
* putsln - Writes a string followed by a cr/lf
* putln - Low level write to console followed by cr/lf
* putoct - Write an octal number for debugging purposes
* putdec - Write a decimal number for debugging purposes
* puthex - Write a hexidecimal number for debugging purposes
* string - Create and allocate space for a string variable
* text - Created a string variable containing specified text
* trim - Can specify trimming of leading or trailing spaces or zeros of a string
* strlen - Get the current length of a string
* strmac - Get the maximum length of a string
* strchr - Extract a specific character from a string
* chrstr - Convert a character to a string
* repchr - Create a string of repeated characters
* sfindc - Search a string for a specific character
* octstr - Converts a number to an octal string
* decstr - Converts a number to a decimal string
* hexstr - Converts a number to a hexidecimal string
* stroct - Converts an octal string to a number
* strdec - Converts a decimal string to a number
* strhex - Converts a hexidecimal string to a number
* cpstr - Copies a string
* appstr - Appends one string to another
* upcase - Converts a string to uppercase
* locase - Converts a string to lowercase
* streq - Compares two strings for equality
* r50str - Converts RAD50 to a string
* strr50 - Converts a string to RAD50
* cvtfqb - Parses FIRQB contents into a filespec
* geterr - Gets a specific system error message
* setnam - Sets the program's name
* sleep - Suspends processing for a specified number of seconds
* parsef - Parse a filespec string into the FIRQB
* chanck - Check status of an I/O channel
* filbuf - Create and allocate space for an I/O buffer
* close - Close an I/O channel

## STR50.MAC
This contains routines to convert between strings and RAD50.  RAD50 is a
way of packing 3 characters into 2 bytes and is used by a number of system
services.

## STRING.MAC
This contains all the string routines except those that convert between
strings and numbers

## STRNUM.MAC
Contains routines to convert between strings and numbers.  Numbers may
be signed or unsigned 16 bit integers with optional leading zeros.

## SYSTEM.MAC
Contains routines to interface with the RSTS/E monitor.  These are generally
not file or I/O related functions.

## TEXTIO.MAC
This contains the I/O routines.  Note that RSTS/E system calls are used.
This is really the only file that is O/S dependent.

## TEST.MAC
This is not part of the library of routines.  It is a test program that
demonstrates many of the routines.  It is subject to change as new
routines are added.
