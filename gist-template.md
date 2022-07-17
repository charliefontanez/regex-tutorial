# Regex Tutorial

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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

Anchors are the meta keytags ^ and $. They set a regex match to the beginning or end of the line of text. Anchors are unique in that they don't specify the character itself but rather the location in where to find the match.

The ^ anchor tag sets our match to the beginning of the line.

The $ anchor tag sets our match to the end of the line.

Combining both ^ and $ will find the match that is only at the beginning and end of the line.

<pre>
Here we have /^cat/      Here we have /cat$/      /^cat$/

<mark style="font-weight: bold; background-color: #B0D0E9;">cat</mark>                      <mark  style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>                      <mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>

<mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>astrophe              catastrophe              catastrophe

wildcat                  wild<mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>                  wildcat

I love my cat            I love my <mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>            I love my cat

...
</pre>


### Quantifiers

Quantifiers allow us to specify a match of a certain amount of characters in sequence in our regular expression.

`*` &ensp; &ensp; &ensp;Matches 0 or more times.

`+` &ensp; &ensp; &ensp;Matches 1 or more times.

`?` &ensp; &ensp; &ensp;Matches 0 or 1 time.

`{n}` &ensp; Matches n number of times

<pre>/x{n}/</pre>

Finds a sequence of characters in our string of exactly n amount. Other characters of different amounts are ignored.


### OR Operator

The OR operator is used to create an alternate keyword or character set to search for in a string of text. If we use `/cat|love/` in our regular expression, this would find all matching instances of cat and love in our string.

`|` 

<pre>a(b|c)  matches a string that has <strong> a  followed by  b or c</strong>

a[bc]   same as previous</pre>


### Character Classes

Character classes are used to match a specific class of character in a string. Some character classes are:


`.` &ensp; &ensp; &ensp;Matches any character

`\w` &ensp; &ensp; Matches a word character (alphanumeric character plus underscore)

`\s` &ensp; &ensp; Matches a whitespace character (includes tabs and line breaks)

`\d` &ensp; &ensp; Matches a single character that is a digit

In order for some character classes to be taken literally they must be escaped with a `\` as they have a special meaning. The character class `$`, for example, needs to be escaped with a `\` like `\$` because the `$` character also represents an anchor tag. All `^.[$()|*+?{\` characters need to be escaped.

<pre>\$\d   Matches a string that has a <strong>$ before one digit</strong>    <span>$2</span>

\$\d\d\.\d\d  Matches a string that has <strong>$ before two digits</strong> followed by a <strong>. and two more digits</strong>    <span>$20.00</span></pre>

Without the escape before the `$` above, the regular expression would be read as an invalid expression with the `$` anchor tag being on the wrong side of the `\d` character class.



Character classes have inverse patterns as well, such as `\D`, `\S`, `\W` which are the character class negations.

`\D` &ensp; &ensp; Matches a single non-digit character

`\S` &ensp; &ensp; Matches a non-whitespace character

`\W` &ensp; &ensp; Matches a non  word character


You can also match non-printable characters like tabs `\t`, newlines `\n`, carriage returns `\r`.


### Flags

Flags are modifiers that change how our expression is interpreted.

`g` &ensp; Global flag &ensp; &ensp; Does not return after the first match. Restarts for subsequent searches after each match

`m` &ensp; Multi-line &ensp; &ensp; When enabled ^ and $ will start at the end of a line instead of the whole string.

`i` &ensp; case-insensitive &ensp; &ensp; Makes the whole expression case insensitive.

### Grouping and Capturing

`( )` Groups allow us to create a capture group with the specified characters and extract them. The captured values can be reused and accessed like an array.

### Bracket Expressions

Bracket expressions are a special kind of character classes. Bracket expressions match one character out of a set of characters.

Bracket expressions are a list of characters or character classes enclosed in brackets. They are used to match single characters or a range of characters in a list

<pre>/[a-zA-Z]/   a through z and A through Z</pre>

If the first character of the list is a carat ^ then the expression matches characters the that are not in the list.

<pre>/[^a-z]/    any character except a through z</pre>

Character classes can also be used to select characters in a bracket expression according to the CisXXX library functions. This feature may not work in non C based environments such as a javascript.

<pre>
[[:alpha:]]   All Alphabetic characters (function isAlpha())

[[:digit:]]   All Digits (function isDigit())

[[:space:]]   All whitespace characters (function isSpace())</pre>

### Greedy and Lazy Match

Quantifiers &ensp;`*` &ensp;`+` &ensp;`{}` &ensp; are naturally greedy operators. They expand the match as far as they can through a provided text.

In order to make the match lazy we can add a `?` to make the match lazy.

`*?`

`+?`

`{ }?`

### Boundaries

`\b` and `\B` represents an anchor like a caret. Boundaries specify the ends of a word in a string.

`\b` &ensp; Matches the postiion where one side is a word character and the other side is a non word character. In other words, mathces where the boundaries of a word are.

`\B` &ensp; The negation matches all the positions where `\b` does not match. Can be used to find a search pattern fully surrounded by word characters.

### Back-references

Uses the values from a matched catpured group. 

`a([bc])\1` &ensp; Back references the same text that was matched from the first capture group.

### Look-ahead and Look-behind

`(?=)` and `(?<=)`

Look ahead and look behind are similar to character class expressions. The main difference between the two is the look ahead and look behind values are not returned in the overall match.

`/ab/`  Basic expression that finds all instances of an a character followed by a b character.

#### Look-ahead

<pre>/a(?=b)/  Look-ahead finds all instances of <strong>a</strong> followed by <strong>b</strong> but only returns the a character in the match</pre>

#### Look-behind

<pre>/a(?<=b)/ Look-behind finds all instances of <strong>a</strong> with a <strong>b</strong> before it but only returns the a character in the match</pre>

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

<!-- # hello world

you can write text [with links](http://example.com) inline or [link references][1].

* one _thing_ has *em*phasis
* two __things__ are **bold**

[1]: http://example.com

---

hello world
===========

<this_is inline="xml"></this_is>

> markdown is so cool

    so are code segments

1. one thing (yeah!)
2. two thing `i can write code`, and `more` wipee! -->
