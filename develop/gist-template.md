# The Elusive Names Regex

This is a short but descriptive tutorial explaining and examining a specific 'regex' or regular expression. A regex is a sequence of characters that soecifies a search pattern in a string. This tutorial will show how a specific regex functions by breaking down each part of the expression and describing what it does for the purpose of understanding the search pattern the regex defines.

## Summary

The regex that will be covered in this tutorial is a name pattern as shown in the following snip of code: '/^[A-Za-z][A-Za-z\'\-]+([\ A-Za-z][A-Za-z\'\-]+)*/'

This regex is used to verify and validate a name input. It verifies that it is a word character, does not allow number characters or underscores, allows multiple words (for example people with two first names: Mary Jo or two or more last names), apostrophes, and hyphens.

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
A anchor in a regex expression is a token that matches a determined location to the engines current position in the string. The only anchor in our regex is the carat '^' which matches at the beginning of the string. It can be identified in the first section: /^[A-Za-z]. The anchor in this section checks that the name starts with either a uppercase or lowercase word character.

### Quantifiers
Quantifiers repeat the preceding token a certain number of times. The first quantifier in our regex is the '+', which matches the preceding pattern one or more times. In our case we want to allow the word character to have one or more words. The second quantifier in the expression is the '*' which matches its preceding pattern for zero or more times so both first and last name can have multiple words such as 'Eddie Van Halen'

### OR Operator
Regex has two OR operators (|) and ([]). This regex uses [] as shown in the snippet '[A-Za-z][A-Za-z\'\-]'. This means that our names can be either just word characters or they can include apostrophes and hyphens.

### Character Classes
Common character classes are '\d', '\w', '\s', and '.' and are used to match a symbol depending on which class used.
* '\d' matches a digit which is a character from 0 to 9. 
* '\w' matches a word character, alphanumeric plus underscore.
* '\s' matches a whitespace character and includes spaces, tabs, newlines, and some other rare characters.
* '.' matches any character except a newline.
This regex in this tutorial does not include any of the character classes shown above. 

### Flags
There are a total of six flags for a javascript regex. A flag changes the default searching behavior by making the regex search in a way the flag denotes.
* i - ignores the case 
* g - searches for all occurances 
* s - dotall, which makes the wild character '.' match newlines 
* m - makes '^' and '$' match the beginning and ending of every line instead of the beginning and ending of the entire string 
* y - makes the expression search from the index indicated in its 'lastindex' property
* u - unicode support, which means the regex will treat characters that are outside the UTF-16 encoding normally
This regex in this tutorial does not include any flags.

### Grouping and Capturing
Grouping or capturing in regex is exactly what the name sounds like and uses round brackets or parentheses. The regex above contains one grouping set as noted in this code snippet: '([\ A-Za-z][A-Za-z\'\-]+)'. This groups the content together to form a name, which is especially useful if the name has hyphens or three words like "De Le Hoya".

### Bracket Expressions
Bracket expressions, '[]', perform matches in a string. In our case the '[A-Za-z]','[A-Za-z\'\-], '[\ A-Za-z]', and '[A-Za-z\'\-]', all say that the input data must match either a word character, apostrophe, or hyphen. 

### Greedy and Lazy Match
A greedy match will match a quantified character or pattern as many times as possible. Quantifiers '*, +, and {}' are considered greedy and the '*' and '+' are found in our expression. They repeat the word characters as many times as the user needs. 

A lazy match is the exact opposite and will only repeat a quantified character or pattern a minimal number of times. This is accomplished by putting the '?' in front of the quantifier. The regex in this tutorial does not use the lazy match. 

### Boundaries
Boundaries are, in a essence, the child of anchors like '$' and '^'. A boundary is represented by either a '/b' or '/B'. The '/b' is similar to a anchor where on one side is a word character and the other side is not a word character. The '/B' is the negation event and matches all positions where '/b' does not match. Our regex above does not include boundaries. 

### Back-references
Back-references are the backslash character '\'. They match the same text as previously matched in a grouping event. We see this above in the snip '\ '. This puts a space in between the end of the first name(s) and beginning of the last name(s). 

### Look-ahead and Look-behind
Lookarounds are called assertions because they do not consume characters in the string but only assert whether a match is possible or not. The is helpful when you want to match something not followed by something else. The syntax of this is 'X(?=Y)' and the expression above does not use this. 

## Author
The author of this regex tutorial is a paramedic with over fifteen years of service trying her hand at some coding. Her bio can be found at https://github.com/youngff43. 
