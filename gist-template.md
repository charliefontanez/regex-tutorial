# Regular Expression Tutorial

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


### Character Classes

Character classes are used to match a specific class of character in a string. Some character classes are:


`.` &ensp; &ensp; &ensp;Matches any character

`\w` &ensp; &ensp; Matches a word character (alphanumeric character plus underscore)

`\s` &ensp; &ensp; Matches a whitespace character (includes tabs and line breaks)

`\d` &ensp; &ensp; Matches a single character that is a digit

In order for some character classes to be taken literally they must be escaped with a `\` as they have a special meaning. For example, the character class `$` needs to be escaped like `\$` because the `$` character represents an anchor tag. `^.[$()|*+?{\` characters need to be escaped.

<pre>\$\d   Matches a string that has a <strong>$ before one digit</atrong></pre>



Character classes have inverse patterns as well, such as `\D`, `\S`, `\W` which are the character class negations.

`\D` &ensp; &ensp; Matches a single non-digit character

`\S` &ensp; &ensp; Matches a non-whitespace character

`\W` &ensp; &ensp; Matches a non  word character


You can also match non-printable characters like tabs `\t`, newlines `\n` or carriage returns `\r`.


### Flags

### Grouping and Capturing

### Bracket Expressions

Bracket expressions are a special kind of character classes. Bracket expressions match one character out of a set of characters.

Bracket expressions are a list of characters or character classes enclosed in brackets. They are used to match single characters or a range of characters in a list

<pre>/[a-zA-Z]/   a through z and A through Z</pre>

If the first character of the list is a carat ^ then it matches characters that are not in the list.

<pre>/[^a-z]/    any character except a through z</pre>

Character classes can also be used to select characters in a bracket expression according to the CisXXX library functions.

<pre>
[[:alpha:]]   All Alphabetic characters (function isAlpha())

[[:digit:]]   All Digits (function isDigit())

[[:space:]]   All whitespace characters (function isSpace())</pre>

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

# hello world

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
2. two thing `i can write code`, and `more` wipee!