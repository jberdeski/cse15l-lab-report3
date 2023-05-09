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

> prints only names of files containing **no** match\

**Ex1:**

```
$ grep -v "e" technical/911report/chapter-1.txt

"WE HAVE SOME PLANES"


INSIDE THE FOUR FLIGHTS

IMPROVISING A HOMELAND DEFENSE

NEADS: On its way towards Washington?


NEADS: Okay.

NATIONAL CRISIS MANAGEMENT


What if?
```
> (I cut outa lot of the extra spaces between lines to make it more readable) 

As you can see this returned lines that did have the letter e but in those lines the e was capitalilzed, therefore it does not count as the same thing that -v is avoiding. But at the end we do see a line that does not have the letter e in it, this is because the purpose of -v is to return the lines that do not have the letter e (lowercase) in them. 

2) -n

>  prints the line number with output lines

3) -i

> ignore case distinctions

4) -c

> prints *only* a count of matching lines per file





*All these options were found by using `grep --help` in my terminal*

