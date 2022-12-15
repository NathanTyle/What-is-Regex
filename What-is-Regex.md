# What-is-Regex

Regex is a series of characters that are used to define a search pattern in text. In this example we will be looking a regex and its many pieces. 

## Summary

With this challenge I will be explaining the Regex pattern of matching an email – /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This specific example reads as follows. (name) @ (domain).(extention)

The a-z means that you may use any letter between a and z. The 0-9 means you may use any character from 0 through 9. The \.- means you can use a literal . or - thanks to the \ that comes before it. The + after allows you to make your email name as long as you'd like. The () that all these characters are in means that all of these characters are stringed together to form a specific portion of the email such as name, domain or extenion.

The @ after the () means that the next character after th (name) portion must be an @ symbol.

The \. after the () means that the next character after the (domain) portion must be a . symbol.

In the extention portion we already covered what a-z and \. meanbut now lets cover the {2,6} part. The curly brackets here refer to a quantifier {2,6} in this case the 2 is the minimum amount of characters this portion can be and 6 is the maximum charcter count, look at it as {min,max}.

The final part I'd like to explain in this summary are the ^ and $ symbols found near the beginning and end of the expression these are called postion anchors. In this example the ^ refers to the beginning of the line, while the $ refers to the end of the expression line. 

## Table of Contents

- [What-is-Regex](#what-is-regex)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [Author](#author)

## Regex Components

### Anchors
In regex we use anchors to match positions of the expresion. For an example ^ meaning before characters, $ meaning after characters, and \b meaning a word boundry, or between characters.

### Quantifiers
Quatifiers are a meta-character that will modify the privious character in the regex and allow you to put however many of those you want in a row.
Some examples are,  * which means 0 or more, + which means 1 or more, ? which means 1 or 2, {min,max} like stated before meaning a minimum and maximum amount of characters alloted to this section.

### OR Operator
OR Operator is often represented by the | symbol and is also refered to as Alteration. The | expression is used to represent either or as in (com|net) meaning the Operator will match either com OR net in this instance.

### Character Classes
Character Classes are characters that appear between square brackets []. Anything inside of a character class becomes a literal-character so [*] just means the * symbol.

### Flags
Flags are optional parameters to a regex that changes it's search behavior. A flag is recognised by its use of a single lowercase letter. Some examples are i which means to ignore casing which ignores case sensitivity in searches. There is also g which means to search globally for all occurences.
As well as s which means to match the wild character of . or dot, with newlines as well.


### Grouping and Capturing
Grouping and Capturing is a way of seperating parts of the expression into groups and searching for or replacing said captured groups. In our example /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ is our #group0, with ([a-z0-9_\.-]+) being our #group1, ([\da-z\.-]+) being our #group2, and ([a-z\.]{2,6}) being our #group3, with the () symbols representing diferent groups, and the entire expression being #group0.

In order to replace a captured group you would use a $ symbol followed by the group number, and you would use / followed by the group number to refer to the captured group.

### Bracket Expressions
Bracket Expressions can be used to determine different meanings such as characters insde of () are usually asigned to a group. You also have {} which we covered earlier as quantifier brackets like {min, max}. You may also use [] thes brackets means anything inside become literal characters instead of meta.

### Greedy and Lazy Match
In Regex Greediness and Laziness determines the order in which the engines will try the permutations of that specific pattern. 

That being said a greedy quantifier will always try to repeat the first tokens as many times as it can, as it gives up on matches, then backtracks to find a match

A lazy quantifier will only match the first part of the tokens and might not bring back the exact match you were actually looking for but return more and usually faster.

### Boundaries
A word boundary is the place in which a word begins or ends usually depicted as \b.

if we were to search for an email that starts with h we would type \bh, with the \b being at the front means we are looking for words starting with h . If we were to use h\b this would mean to only find the letter h at the end of a word. 

If we were instead to use a capitol B we would be looking for a non word boundary, for example if we typed \Bh it would find words with the letter h that are not found at the beginning of a word, in turn if we used h\B it would find words with the letter h that are not found at the end of the word.

### Back-references
Back-references in regex are commands that call back and refer to a previous part of a matched regex. They refer to the subexpression which is found inside of (). They are specified by \ followed by a single digit like(\3).

### Look-ahead and Look-behind
Look-ahead is a form of regex that allow you to match one element so long as its followed by the next coresponding element. For example to match A it must be followed by B like. A (?=B).

Look-behind is a form of regex that allows you to match one element so long as there is another coresponding element before it. For example to match B it must be proceeded by A like. (?<=B) A



## Author

Hi I'm Tyler an entry level programmer, and I hoped this tutorial helped in some small part with your understanding of regex in coding.

https://github.com/NathanTyle/What-is-Regex
