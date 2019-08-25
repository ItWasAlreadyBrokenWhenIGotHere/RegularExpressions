# RegularExpressions

This module is
*  03-Extended Set

---

###  Curly Braces Repeated (a{m}) or (a{m,n})

Below is the input file 18 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
834 *
519 *
4874
5
89
45687
25
645 *

# Contains three digits numbers
# Repeater is a{x} where x is time to repeat and a is what to repeat
# Following pattern returns matching words from the input text:
^[0-9]{3}$
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