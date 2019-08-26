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
sed -r 's/([0-9]+)x([0-9]+)/\1 pix by \2 pix/g' regex25.txt
```

---

###  The Fist name - Last Name Problem

Below is the input file 26 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
John Wallace
Steve King
Martin Cook
Adam Smith
Irene Peter
Alice Johnson


# Aim is to swap place of fisrt name and last name and also add , between
# To separate names: ([a-zA-Z]+)\s([a-zA-Z]+)
# [] separates character class for english letters and + means one or more occurances and \s is the space between names
# First group of character class is named as \1 and seconf \2
# Following pattern does the name swap and adds , between:
sed -r 's/([a-zA-Z]+)\s([a-zA-Z]+)/\2,\1 /g' regex26.txt 
```

---

###  The Time Format Problem

Below is the input file 27 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
7:32
6:12
12:23
1:23
11:33
4:21

# Aim is to format given times to following format: 32min past 7
# To separate groups: ([0-9]{1,2}):([0-9]{2})
# {1-2} indicate 1-2 occurances of digits and : is the hour and minute separator
# {2} indicate that minute have always 2 digits
# First group of character class is named as \1 and seconf \2
# Following pattern does the formation of time:
sed -r 's/([0-9]{1,2}):([0-9]{2})/\2 mins past \1 /g' regex27.txt 
```

---

###  The Phone Number Problem

Below is the input file 28 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
914.582.3013
873.334.2589
521.589.3147
625.235.3698
895.568.2145
745.256.3369

# Aim is to format given times to following format: xxx.xxx.3013
# Only one group is needed and it's the last digits of the string: [0-9]{3}\.[0-9]{3}\.([0-9]{4})
# First two set of digits are defined but not captured to character class group
# \. is escaped capture for .
# Following pattern does the formation of time:
sed -r 's/[0-9]{3}\.[0-9]{3}\.([0-9]{4})/xxx.xxx.\1 /g' regex28.txt 
```

--- 

###  The Date Format Problem

Below is the input file 29 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
Jan 5th 1987
Dec 26th 2010 
Mar 2nd 1923
Oct 1st 2008
Aug 3rd 2009
Jun 10th 2001

# Aim is to format dates to 5-Jan-87
# This requires to capture three groups
# ([a-zA-Z{3}])\s([0-9]{1-2})[a-z]{2}\s[0-9}{2}([0-9]{2})
# In the goup \3, year is splitted in the way that only last two digits are capture
# Following pattern does the formation of time:
sed -r 's/([a-zA-Z]{3})\s([0-9]{1,2})[a-z]{2}\s[0-9]{2}([0-9]{2})/\2-\1-\3/g' regex29.txt 
```

--- 

###  The Phone Number Problem

Below is the input file 30 content, with pattern to get correct output:

```console
# Input text (* indicate desired output):
(914).582.3013
(873).334.2589
(521).589.3147
(625).235.3698
(895).568.2145
(745).256.3369


# Aim is to format dates to 914.582.3013
# This requires two capture groups
# As ( is special characted, it needs escape char to be handled
# \(([0-9]{3})\)(\.[0-9]{3}\.[0-9]{4})
# Following pattern does the formation of time:
sed -r 's/\(([0-9]{3})\)(\.[0-9]{3}\.[0-9]{4})/\1\2/g' regex30.txt 
```

---