# RegularExpressions

This module is
*  04-Find And Replace With Capture Group

Find and replace cannot be done by grep in linux environment as it is two statement action.
In linux command for Find and replace is:
sed -r 's/pattern/replacement/g' inputfile
g means global is not limiting return to first find item

---

###  The Monitor Resolution Problem

Below is the input file 25 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
1280x720
1920x1080
1600x900
1280x1024
800x600
1024x768

# This should be converted to: 1280 pix by 720 pix

# Capturing groups is done by using ()() where first () is referred as Group 1 and second as Group2
# Inside (), we need to to specify what we want to capture
# in this case Group 1 is numbers from 3 to 4 followed by x and contiung with Group 2
# Group 1 can be captured by [0-9]+ (at least one instance of number between 0-9)
# Now we have two groups and we can refer to those groups by \1 and \2
# Following pattern returns matching words from the input text:
sed -r 's/([0-9]+)x([0-9]+)/\1 pix by \2 pix/g' filename
```

Below is the input file 19 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
lion *
tiger *
leopard
fox
kangaroo
bat
mouse *
cuckoo *
deer *

# Contains 4-6 chars from a-z, no shorter or longer words
# Repeater is a{m,n} where m is atleast and n is most of repeat of char
# Following pattern returns matching words from the input text:
^[a-z]{4,6}$
```

--- 

### Single Ended Curly Braces Repeater (a{m,n}) or ((ab){,n}) 

Below is the input file 20 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
ha
hahahahaha *
hahaha
hahahaha *
haha

hahahahahaha *
hahahahahahahaha *
hahahahahahahahaha *

# Should include 'ha' 4-9 times
# As we are looking 'ha' we need to point that for the repeater by using () around the word we are looking
# Repeater is (ha){m,} where m is atleast and most is open
# Following pattern returns matching words from the input text:
(ha){4,}
```
---

Below is the input file 21 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
ha *
haha *
hahahahaha
hahahaha
hahaha
hahahahahahaha
hahahahahaha

# Should include 'ha' 4-9 times
# As we are looking 'ha' we need to point that for the repeater by using () around the word we are looking
# Repeater is (ha){,n} where n is the maximum number of match but 
# Following pattern returns matching words from the input text:
^(ha){,2}$
```
---  

### The Plus Repeated (a+)

Below is the input file 22 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
fooaaaabar *
fooabar *
foobar
fooaabar *  
fooxxxbar
fooxbar

# Starts with foo, ends with bar and have repetition of letter a in between
# As a must occur between start and end, we cannot use a*
# Instead we can use +, which expexts at least one instance of letter
# Following pattern returns matching words from the input text:
fooa+bar
```

--- 

### The Question Mark Binary (a?)

Below is the input file 23 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
https://website *
http://website *
httpss://website
httpx://website
httpxx://website


# Starts with http or https - Starts with http and follows 0-1 s letter
# Regex symbol ? means 0-1 instance of letter
# Following pattern returns matching words from the input text:
https?://
```
---

### Making Choices With Pipe (a|b)

Below is the input file 24 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
sapwood
rosewood
logwood *
teakwood
plywood *
redwood

# Ends with wood and start with log or ply
# Choise symbol in regex is | (pipe)
# Following pattern returns matching words from the input text:
(log|ply)wood
```
---