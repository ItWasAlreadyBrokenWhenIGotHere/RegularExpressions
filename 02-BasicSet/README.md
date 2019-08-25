# RegularExpressions

This module is
*  02-Basic Set

---

###  The Wild Card Symbol (.)

Below is the input file 02 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
fooabar *
fooxbar *
baryfoo
foobar
fooxybar
foocbar *

# Starts with foo, followed by one char and ends with bar
# Following pattern returns matching words from the input text:
foo.bar
```

--- 

### Wildcard Asterisk Combo (.*)

Below is the input file 03 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foobar *
barfoo
fooabcbar *
foobxcbar *
barcbyfoo
foozbar *
barafoo
barabfoo

# Starts with foo, ends with bar and have any number of any char between
# Following pattern returns matching words from the input text:
foo.*bar
```

--- 

### Representing Whitespaces (\s*)

Below is the input file 04 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
fooxxxbar
foo   bar *
fooxbar
fooxxbar
foo bar *
foo      bar *
foobar *
fooyyybar

# Starts with foo, ends with bar and have amount of whitespace between
# Following pattern returns matching words from the input text:
foo\s*bar
```

--- 

### Character Classes ([abc] or [^abc])

Below is the input file 05 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foo *
moo
coo *
doo
poo
loo *
boo
hoo

# Starts with f, c or l and ends with oo
# Following pattern returns matching words from the input text:
[fcl]oo
```

Below is the input file 06 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foo *
moo
coo * 
doo *
poo *
loo *
boo *
hoo

# Starts with f, c, d, p, l or b and ends with oo
# Following pattern returns matching words from the input text:
[fcdplb]oo
```
--- 

Below is the input file 07 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foo *
moo
coo * 
doo *
poo *
loo *
boo *
hoo

# Ends with oo and does not start with m or h
# Following pattern returns matching words from the input text:
# [^] (carrot in side []) has special meaning - it reverses the char list
[^mh]oo
```
--- 

### Character Classes With Range ([a-c]xx) or ([a-cz]xx)

Below is the input file 08 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
joo *
boo
koo *
loo *
woo
moo *
zoo
coo

# Starts with j,k,l or m  (chars between j to m) and ends with oo
# Following pattern returns matching words from the input text:
[j-m]oo
```

Below is the input file 09 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
joo *
boo
koo *
loo *
woo
moo *
zoo *
coo 

# Starts char is between j to m + z (outliar z) and ends with oo
# Following pattern returns matching words from the input text:
[j-mz]oo
```

Below is the input file 10 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
joo *
boo
Koo *
Loo *
woo
moo *
zoo *
coo

# Starts char is from j to m and z (outliar z) with one uppercase K and ends with oo
# Following pattern returns matching words from the input text:
[j-mJ-Mz]oo
```

--- 

### Escape With Backslash (\.)

Below is the input file 11 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
xxx.yy *
xx.yyyy *
x.yy *
xy
xxyy
yyxx
yx
yxxx

# Starts with 0-n x, end 0-n y and in between is char .
# As . meand anychar in regex, it needs to be escaped with \
# Following pattern returns matching words from the input text:
x*\.y*
```

--- 

Below is the input file 12 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
x#y *
x:y *
x.y *
x&y
x%y

# Starts with x, ends y and in between is char #, :, or . char
# Special chars in Class (between []) needs not to be escaped
# Following pattern returns matching words from the input text:
x[#:.]y
```

--- 

Below is the input file 13 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
x#y *
x:y *
x^y *
x&y
x%y

# Starts with x, ends y and in between is char #, :, or ^ char
# Special chars in Class (between []) needs not to be escaped
# Exception for the previous statement are ^ special char
# Following pattern returns matching words from the input text:
x[#:\^]y
```

--- 

Below is the input file 14 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
x#y *
x\y *
x^y *
x&y
x%y

# Starts with x, ends y and in between is char #, \, or ^ char
# Special chars in Class (between []) needs not to be escaped
# Exception for the previous statement are ^ and \ special characters
# Following pattern returns matching words from the input text:
x[#\\\^]y
```

--- 

### Anchors (^) or ($)

Below is the input file 15 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foo bar baz *
bar foo baz
baz foo bar
bar baz foo
foo baz bar *
baz bar foo

# Starts with foo and exclude sentences with foo somewhere else that in the beginning
# ^ is special char that indicate beginning of the line, stands for negation
# Following pattern returns matching words from the input text:
^foo.*
```

--- 

Below is the input file 16 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foo bar baz
bar foo baz
baz foo bar *
bar baz foo
foo baz bar *
baz bar foo

# Ends with bar and bar in other positions are not included
# $ is special char that signifies end of the line
# Following pattern returns matching words from the input text:
.*bar$
```

Below is the input file 17 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
foo *
foo bar
baz foo
foo bar baz
baz bar foo

# Line which starts and ends with foo
# ^ is special char that indicate beginning of the line, stands for negation
# $ is special char that signifies end of the line
# Following pattern returns matching words from the input text:
^foo$
```