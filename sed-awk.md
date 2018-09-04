
# About

[sed & Awk, 2nd Edition: UNIX Power Tools](http://shop.oreilly.com/product/9781565922259.do)
by Dale Dougherty, Arnold Robbins
O'Reilly, 2010

# Thoughts

I will happily study classic Unix command-line tools with barely any excuse for doing do. It is good to have widely available, well-documented tools for data processing.

# Take-Aways

* There's a natural learning progression from grep to sed to awk, all based on ed commands
* g/re/p - global, regex, print - the origin of grep's name, prints all lines that match re
* sed & awk instructions are comprised of a pattern (regex) and a procedure to run on lines that match the pattern
* sed commands are implicitly global (unlike ed) and automatically print after each line (unlike awk)
* sed & awk scripts often have portability issues, maybe consider nawk
* Multi-line matches are challenging and best avoided where possible

# Concepts

* `-c` flag - for grep, count matching lines
* `-f` flag - cli option for sed and awk, read script from file
* `-F` Flag - for awk, sets the field delimiter, defaults to whitespace
* `-n` flag - for sed, suppress automatic input, require p command instead
* `\{n\}` matches n occurrences of previous char, `{n,}` match at least n, `{n,m}` match >=n <=m
* Basic Regular Expressions (BRE) - specified by Posix
* caret / circumflex operator (regex) - invert a character class
* character class - regex `[]`, hypen first or last in a character class is just a char in the class, same with ] first
* equivalence class, eg. `[=e=]`, allows è to be matched using the same rules if the locale supports it (such as in French)
* Extended Regular Expressions (ERE) - specified by Posix, eg. `[:alpha:]`, `[:space:]`, `[:digit:]`
* hyphen operator (regex) - lets you specify a range of characters inside of a character class
* pipe operator (regex) - "or" in a group, either regex can match

# Techs

* awk - Aho, Weinberger, Kernighan lang
* nawk - new awk, introduced by Unix System V
* sed - Stream Editor
* sqtroff - formatting software
* troff - Unix document formatting software
* Verion 7 Unix (V7) - introduced sed & awk
* XView - Sun Microsystems - X Window System toolkit

# Books

* "Mastering Regular Expressions" by Jeffrey Friedl (O'Reilly)
* "SED - A Non-Interactive Text Editor," article by Lee McMahon 1978
* "The GNU Awk User's Guide" - Arnold Robbins 1996, now "Effective Awk Programming"
* "The UNIX Programming Environment" - Brian Kernighan and Rob Pike, 1984
* "UNIX Text Processing" - Dale Dougherty & Tim O'Reilly 1987

# Code

* `sed 's/from/to/' input` - all lines are output whether substitution occurred or not
* `address { command }` - general building block of awk programs, if a line matches the regex address, run commands on it
* `grep -c '^$' file` - count the number of empty lines in a file
* `grep -c '[ \t]$' file` - count the number of lines ending with a space or tab
