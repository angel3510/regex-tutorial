## Regex Tutorial!

Regular expressions, or regex, are a sequence of characters that can be used for finding certain patterns of a string.  When applied to code or search algorithms, regex will find and replace a character or sequence of characters within a string.  The main purpose of regex is to validate input.

## Summary

In this tutorial, I will go over the following regular expression example that can be used to verify that user input is a valid email address:
</br> ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

The anchors that are used to contain this regular expression are ```^```(start) and ```$```(finish).

### Quantifiers

```+``` is used to communicate there is another sequence to be matched as a greedy quantifier. ```{2,6}``` is another greedy quantifer used to specify the input that there should be a minimum of 2 characrtors to a maximum of 6 characters.

### OR Operator

Alternation and grouping are essential features of the modern regular expression, or regex library. You will be able to provide as many terms as you want, as long as they are separated with the pipe character: ```|```. This character separates each term contained within each ```(...)``` group.

Use the ```|``` operator (logical OR) to match characters or expression of either the left or right of the ```|``` operator.

### Character Classes

```/d``` is a character class that is used in Javasctipt which classifies the use of any digit from 0 to 9.

### Flags

Flags are an optional parameter to a regex that changes its behavior of searching; flags are denoted using a single lowercase alphabetic character. To give multiple flags to a regex, we write them one after another (without any spaces or other delimiters). For example, if we were to give both the flags ```i``` and ```g``` to the regex ```/a/```, we'd write ```/a/ig``` (or equivalently ```/a/gi```, since the order doesn't matter) By default, a regular expression does a case-sensitive search. That is, ```/a/``` matches only ```a```. However, by using the flag ```i```, which stands for 'ignore casing', we can make the expression carry out a case-insensitive search. That is, ```/a/i``` would match ```a```, as well as ```A```.

By default a regex stops it search after finding the first match for a given pattern. However, using the flag ```g```, which stands for 'global', we can get it to find all matches for the pattern without stopping at the first one.

In regex for JavaScript, there's a total of 6 flags, with each having a different purpose.

### Grouping and Capturing

There are three groups that are being captured in this example. The first group is the username of the e-mail account ```[a-z0-9_\.-]```. The second group captures the domain name or e-mail service being used ```[\da-z\.-]```.  The third group captures the domain extention, ".com" for example ```[a-z\.]{2,6}```.

### Bracket Expressions

Much like the groups in this example, there are also 3 bracket expressions. The information in the bracket expressions is opened and closed between brackets ```[]```. This indentifies which information is allowed to be matched.

*1st Expression:* ```[a-z0-9_\.-]``` - this bracket includes case sensitive characters from a-z and also numbers from 0-9 an underscore along with periods and hyphens.

*2nd Expression:* ```[\da-z\.-]``` - this bracket includes all digits, case sensitive characters from a-z, periods, and hyphens

*3rd Expression:* ```[a-z\.]``` - this bracket includes case sensitive characters from a-z and periods.

### Greedy and Lazy Match

So far in this example, we have only used greedy quantifiers ```+``` and ```{}```, meaning it will allow the match to expand as long as it is required to go. If these quantifiers were lazy quantifiers, they would appear as ```+?``` or ```{}?``` meaning it will direct the system to make the shortest match possible.

### Boundaries

Boundaries ```\b``` make assertions about what can be matched to the left and right of the current position. In non-Unicode mode, it matches a position where only one side is an ASCII letter, digit or underscore. But in Unicode mode, it matches a position where only one side is a Unicode letter, digit or underscore. ```\B```

This is easily done with a pair of word boundaries. Replace both ```^``` and ```$``` with ```\b```. 
</br>

For instance, ```^[A-Z0-9+_.-]+@[A-Z0-9.-]+$``` becomes ```\b[A-Z0-9+_.-]+@[A-Z0-9.-]+\b```

### Back-references

Back-references are regex commands which refer to a previous part of the matched regular expression. Back-references are specified with backslash and a single digit: ```\1```. The part of the regular expression they refer to is called a subexpression, and is designated with parentheses. Back-references and subexpressions are used in two cases:
</br>

*First*, in the regular expression search pattern, and in the replacement part of the 's' command
*Second*, in a regular expression pattern, back-references are used to match the same content as a previously matched subexpression.

### Look-ahead and Look-behind

Lookahead and lookbehind, also known as lookaround, are zero-length assertions just like the start and end of line, and start and end with word anchors explained earlier in this tutorial. The key difference is that lookaround actually matches characters, but then gives up the match, returning only the result: match or no match. That is why they are called “assertions”. They don't consume characters in the string, but only assert whether a match is possible or not. Lookaround allows you to create regular expressions that are impossible to create without them.

## Author

Made by Angel Sandoval

<a href="https://github.com/angel3510">My GitHub Repository</a>