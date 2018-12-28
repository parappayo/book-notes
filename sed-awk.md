
# About

* [sed & Awk, 2nd Edition: UNIX Power Tools](http://shop.oreilly.com/product/9781565922259.do)
* by Dale Dougherty, Arnold Robbins
* published by O'Reilly, 2010

# Thoughts

I will happily study classic Unix command-line tools with barely any excuse for doing do. It is good to have widely available, well-documented tools for data processing.

On the other hand, sed is a good example of an overly terse domain-specific language; all but the most elegant sed programs are difficult to follow. I get the impression that sed does not lend itself to self-documenting code, and that sed puts the user at risk for brittle legacy systems.

# Take-Aways

* There's a natural learning progression from grep to sed to awk, all based on ed commands.
* g/re/p - global, regex, print - the origin of grep's name, prints all lines that match re.
* sed & awk instructions are comprised of a pattern (regex) and a procedure to run on lines that match the pattern.
* sed commands are implicitly global (unlike ed) and automatically print after each line (unlike awk).
* sed & awk scripts often have portability issues, maybe consider nawk.
* Multi-line matches are challenging and best avoided where possible.
* The 80 char limit was hard-coded into some systems that stored all text in a fixed-width format.
* Older System V man pages are often in nroff format and it may be necessary to strip special chars in order to make them human-readable in plaintext.

# Concepts

* `-` hyphen operator - lets you specify a range of characters inside of a character class
* `|` pipe operator (regex) - "or" in a group, either regex can match
* Basic Regular Expressions (BRE) - specified by Posix
* character class - regex `[]`, hypen first or last in a character class is just a char in the class, same with ] first
* equivalence class, eg. `[=e=]`, allows è to be matched using the same rules if the locale supports it (such as in French)
* Extended Regular Expressions (ERE) - specified by Posix, eg. `[:alpha:]`, `[:space:]`, `[:digit:]`

# Techs

* awk - Aho, Weinberger, Kernighan lang
* MKS Toolkit - DOS ports of Unix tools
* nawk - new awk, introduced by Unix System V
* sed - Stream Editor
* sqtroff - formatting software
* troff - Unix document formatting software
* Verion 7 Unix (V7) - introduced sed & awk
* XView - Sun Microsystems - X Window System toolkit

# Grep Quick Reference

* `\{n\}` matches n occurrences of previous char, `{n,}` match at least n, `{n,m}` match >=n <=m
* `^` caret / circumflex operator - invert a character class

## CLI Flags

* `-c` - count matching lines

## Examples

* `grep -c '^$' file` - count the number of empty lines in a file
* `grep -c '[ \t]$' file` - count the number of lines ending with a space or tab

# Sed Quick Reference

## Take-Aways

* Multi-line commands are capitalized.
* sed is often sensitive to extraneous whitespace; it can mess up a filename or branch label.
* New users sometimes expect sed to run each command on the entire input stream before progressing to the next command, rather than running each command on the current line before progressing to the next line of input.
* sed characters cannot be matched by ASCII or octal values, but you can find a key combination in vi and use Ctrl-V to quote the char; eg `^[` matches the Escape char code.
* General pattern for multi-word substitution that splits across lines: match the first word, load the next line with N, substitute newlines for spaces, then replace (but how to restore line breaks?)

## Concepts

* `!` operator - invert address
* `#n` comment that also suppresses line output
* `:` operator - label, for branching to
* `{}` braces operator - group commands that share an address, can be nested
* address - restricts a command to only run on matching lines, default without an address is for a command to run on every input line; two addresses specify a range where commands start when a line matches the first address and stop when a subsequent line matches the second address
* append command (a)
* branch command (b) - jump control to label; default is to return control to top
* change command (c)
* delete command (d)
* embedded newline - when a buffer (pattern or hold space) contains more than one line of input; logcially this is still considered as one line and `$` matches the end of the buffer
* get command (g) - copy hold space to pattern space
* hold command (h) - copy pattern space to hold space
* hold space - alternate buffer, operated on by hold (h,H), get (g,G), and swap (x)
* insert command (i)
* list command (l)
* next command (n) - output pattern space, read next line into pattern space without returning control to top; multi-line version (N) appends next line to pattern space instead of replacing the pattern space
* pattern space - working buffer, commands typically operate on this
* print command (p) - output pattern space; multi-line (P) prints only the first line of the pattern space
* quit command (q) - immediate exit
* read command (r) - insert file contents into input stream
* substitution command (s)
* swap command (x) - swap pattern space and hold space
* test command (t) - conditional branch; only jump control if a match occurred on the currently addressed line
* transform command (y) - character set substitution, used like a cipher
* write command (w)

## CLI Flags

* `-n` - suppress automatic output, require p command instead
* `-f` - read script from file instead of as an argument
* `-i` - in-place editing of a file, will not read from stdin

## Examples

* `sed 's/from/to/' input` - all lines are output whether substitution occurred or not
* `s!/usr/mail!/usr2/mail!` - substitution using `!` as a separator rather than `/`, helpful for working with paths
* `sed '/---/!s/--/\\(em/g'` - su double dash for emdash, but skip more than double
* `sed '/^$/d'` - delete empty lines
* `sed '12,$d'` - head 12 lines
* `sed '12q'` - head 12 lines
* `(*+?)` - span of undetermined length
* `\{n,m\}` - span of given length
* `$a\` - append to end of file

```
#n print lines containing "if" along with line number
/if/{
  =
  p
}
```

```
#n delete empty line if it follows a .H1 line
/^\.H1/{
  n
  /^$/d
}
```

```
#n replace a multi-word phrase
/Edmonton/{
  $!N
  s/ *\n/ /
  s/Edmonton Oilers */Oilers/
}
```

```
# wrap paragraphs of text in p tags, using empty lines as delimiters
${
  /^$/!{
    H
    s/.*//
  }
}
/^$/!{
  H
  d
}
/^$/{
  x
  s/^\n/<p>/
  s/$/<\/p>/
  G
}
```

# Awk Quick Reference

* `address { command }` - general building block of awk programs, if a line matches the regex address, run commands on it

## CLI Flags

* `-F` - sets the field delimiter, defaults to whitespace

# Books

* "Mastering Regular Expressions" by Jeffrey Friedl (O'Reilly)
* "SED - A Non-Interactive Text Editor," article by Lee McMahon 1978
* "The GNU Awk User's Guide" - Arnold Robbins 1996, now "Effective Awk Programming"
* "The UNIX Programming Environment" - Brian Kernighan and Rob Pike, 1984
* "UNIX Text Processing" - Dale Dougherty & Tim O'Reilly 1987
