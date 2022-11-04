# Regular Express (Regex)

A regular expression or regex is an expression that describes patterns in a string of data. With regexs you can check a string of characters like an email address or password. 

## Summary

The regex that I will be explaining is: 
```^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2})$```
This regex is an example of an email verification regex.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
Anchors in regexs match a position before or after characters. 
```^```: This is the carrot anchor. This anchor matches the beginning of the text.
```$```: This is the dollar anchor. This anchor matches the end of the text.

For example if we have a variable ```var student = "Alex";``` and we console log ```console.log(/^A/.test(student));``` the output would be ```true``` becuase the variable student is set to ```"Alex"```, which begins with an 'A'.

The same would be the case with the dollar achor, if we have the same variable ```var student = "Alex"``` and if we console log ```console.log(/x$/.test(student));``` the output would also be ```true``` becuase the varible student in this example is set to ```"Alex"```, which ends with 'x'.

In our example of a regex you can see the carrot anchor at the beginning as well as the dollar anchor at the end. 
```^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2})$```

### Quantifiers
Quantifiers match a number of instances of a character in a string. A quantifier is a number or a range of numbers in curly brackets.

For example, here is a regex with a a quantifier. ```/\d{4}/``` if we were to console log this quantifier
```var graduationDate = "I graduated in 2022";```
```var quantifier = /\d{4};```
```var result = graduationDate.match(quantifier);```
```console.log(result)```
The result will be ```2022``` becuase the number in the curly brackets is 4 so any four digit number will be console logged. 

In our email verification example
```^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2})$```
the quantifier is at the very end if the regex ```{2}```. This quantifier is in the ending domain name of the email address (e.g. .com) portion of our regex. The quantifier in our regex is saying that the ending domain name of 

### Grouping Constructs
A regex can have many groups within the one expression. For example, take a look at our regex.
```^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2})$```
There are three groups in our regex. The first group ```[A-Za-z0-9_\-\.]``` is to verify that the the first part of emails (the portion before the @) have either letters A-Z capitalized or lowercase (a-z) or has the numbers 0-9 or has the symbols "_","-", or ".". 

The second part of our regex ```[A-Za-z0-9_\-\.]``` is for verifing the middile part of an email address (the part after the @ but before the ending domain name e.g. '.com'). It is looking to verify the same charaters that the first group is looking for.

The last group of our regex ```[A-Za-z]{2}``` is just looking to verify that the ending part of the email address (after the ".") has the letters A-Z capitalized or lowercase (a-z) and that there are at least 2 characters in that portion of the email address. 

### Bracket Expressions
The square brackets in a regex searchs for any character that is in that set. The square brackets and it contents are a set.

For example ```[abcdefg]``` would match any of the seven characters ```'a'```,```'b'```,```'c'```,```'d'```,```'e'```,```'f'```,```'g'```

In our regex there are three sets of brackets. The first set ```[A-Za-z0-9_\-\.]``` is searching for characters that are A-Z upper or lowercase or 9-0 or the symbols "_","-", or ".". The second set of brackets is searching for the same characters. The last bracket ```[A-Za-z]``` is searching for the characters A-Z upper or lowercase.

### Character Classes
A character class matches any one of the characters enclosed in the brackets. You can specify a range of characters by using a hyphen, but if the hyphen is the first or last character enclosed in the square brackets, it will be taken literally and be included in the character class as a normal character.

For example ```[abcdef]``` equals ```[a-f]```. But ```[-abcdef]``` or ```[abcdef-]```with match the letters ```'a'```,```'b'```,```'c'```,```'d'```,```'e'```,```'f'``` as well as the hyphen charcter ```'-'```

### The OR Operator
The OR operator is represented but the "|" character, this operator lets the regex know that it is only looking for at least one of the compoents of within any given group of the regex.

For example:
```let regex = /Christmas|Thanksgiving|Easter|Valentines Day?/gi;```
```let str = "My favorite holiday is Christmas!";```
```console.log(str.match(regex));```
The output will be ```'Christmas'``` because the regex is using the OR operator, so as long as Christmas, Thanksgiving, Easter, OR Valentines Day appears the regex verification is satisfied. 

### Flags
A flag is an optional parameter in a regex that modifies how the regex searches. A flag changes the default searching behavior of a regex. There are many diiferent types of flags like the i flag, the g flag, or the s flag.

For example if we have the variable ```var greeting = "Hello world!"``` and the regex ```var regex = /hello/i;``` and then we console log ```console.log(greeting.match(regex))``` the output will be still be ```"Hello"``` because the i flag makes the regex ignore the casing of the characters.

### Character Escapes
Charcter Escape is represented in regexs by the backslash "\". This character lets the regex know that the charater that follows should be traken literally. 

For example in our regex 
```^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2})$```
We use the bankslash in the first and second protion of our regex. ```^([A-Za-z0-9_\-\.])``` the backslash after the underscore (_) is escaping that character and letting the regex know that the character that follows, which is a dash (-) should be taken literally and searched for.

## Author
This tutorial was written by Alexandria Rogers. My GitHub is: https://github.com/alexandriarogers
