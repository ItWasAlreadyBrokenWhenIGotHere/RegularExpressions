# RegularExpressions

This module is
*  01-Foundation

```console
# Input text: 
fooabar
fooaaaabar
foobar
fooxbar
fooxxxbar

# Regex to get all words start with foo, ends with bar and can have 0-n a in between
fooa*bar

a* means 0-n occureance of letter a
```

---

###  Grep regex engine

On linux based systems, you can use Grep regex engine in the following wey:

```console
# Following command returns matching words from the input file:
grep 'fooa*bar' filename.txt
```

--- 
