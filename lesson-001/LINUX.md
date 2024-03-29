# touch Command in Linux

## Description
The touch command's primary function is to modify a timestamp. Commonly, the utility is used for file creation, although this is not its primary function. The terminal program can change the modification and access time for any given file. The touch command creates a file only if the file doesn't already exist.


touch <options> <file or directory name>

## Examples:

Create File
touch <filename>

Multiple Files
touch <filename> <filename>

touch <filename{<start>..<finish>}>

Set timestamp
touch -t <timestamp> <filename>

[[CC]YY]MMDDhhmm[.ss]

Change modification time to current
touch -m <filename>

Avoid creating a new file
touch -c <filename>



# cat Command in linux

## Purpose
Concatenates or displays files.

## Syntax
cat [ - q ] [  -r ] [ - s ] [ - S ] [ - u ][ - Z ] [ - n [ - b ] ] [ - v [ - e ] [ - t ] ] [  - | File ... ]

## Description
The cat command reads each File parameter in sequence and writes it to standard output. If you do not specify a file name, the cat command reads from standard input. You can also specify a file name of - (dash) for standard input.

Description
-b	Omits line numbers from blank lines, when specified with the -n flag.
-e	Displays a $ (dollar sign) at the end of each line, when specified with the -v flag.
-n	Displays output lines preceded by line numbers, numbered sequentially from 1.
-q	Does not display a message if the cat command cannot find an input file. This flag is identical to the -s flag.
-r	Replaces multiple consecutive empty lines with one empty line. This flag is identical to the -S flag.
-s	Does not display a message if the cat command cannot find an input file. This flag is identical to the -q flag.
Note: Previously, the -s flag handled tasks now assigned to the -S flag.
-S	Replaces multiple consecutive empty lines with one empty line. This flag is identical to the -r flag.
-t	Displays tab characters as ^I if specified with the -v flag.
-u	Does not buffer output. The default is buffered output.
-v	
Displays nonprinting characters as visible characters, with the exception of tabs, new-lines, and form-feeds. ASCII control characters (octal 000–037) are printed as ^n, where n is the corresponding ASCII character in the octal range 100–137 (@, A, B, C,..., X, Y, Z, [, \, ], ^, and _); the DEL character (octal 0177) is printed as ^?. Other non-printable characters are printed as M-x, where x is the ASCII character specified by the low-order seven bits.

When used with the -v option, the following options may be used:

-e
A $ character will be printed at the end of each line prior to a new line.
-t
Tabs will be printed as ^I and form feeds will be printed as ^L
The -e and -t options are ignored if the -v option is not specified.

-	Allows standard input to the cat command.
Z	Dumps the contents of encrypted files in encrypted format. Access keys to the encrypted file are not required to do cat -Z on the file.

## Examples

cat notes

This command displays the data in the notes file. If the file is more than one less than the number of available display lines, some of the file scrolls off the screen. To list a file one page at a time, use the pg command.

To concatenate several files, enter:
cat section1.1 section1.2 section1.3 >section1

This command creates a file named section1 that is a copy of section1.1 followed by section1.2 and section1.3.

To suppress error messages about files that do not exist, enter:
cat  -q section2.1 section2.2 section2.3 >section2

If section2.1 does not exist, this command concatenates section2.2 and section2.


To append one file to the end of another, enter:
cat section1.4 >> section1

The >> (two carets) appends a copy of section1.4 to the end of section1. If you want to replace the file, use the > (caret).

To add text to the end of a file, enter:
cat >>notes
Get milk on the way home
Ctrl-D

This command adds Get milk on the way home to the end of the file called notes. The cat command does not prompt; it waits for you to enter text. Press the Ctrl-D key sequence to indicate you are finished.

To concatenate several files with text entered from the keyboard, enter:
cat section3.1 - section3.3 >section3

This command concatenates the file section3.1 with text from the keyboard (indicated by the minus sign), and the file section3.3, then directs the output into the file called section3.