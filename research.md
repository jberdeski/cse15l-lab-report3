# Researching Commands

`grep`

The command `grep` is a command-line utility which is used to search for text paterns in files. 
This command can be used to look into one or multiple files.
The layout of this command can be simplified to `grep [OPTION]... PATTERN [FILE]...`

* Option in this instance is how `grep` will run
  > We'll look into some of the options that can be used below.

* Pattern refers to the thing you are searching for, may it be a word in a file or part of a file name.

* File is pretty self explanitroy, as it referes to the file or files you want `grep` to search in.

## Options for `grep`

1) -v

> prints only names of files containing **no** match

2) -n

>  prints the line number with output lines

3) -i

> ignore case distinctions

4) -c

> prints *only* a count of matching lines per file





*All these options were found by using `grep --help` in my terminal*

