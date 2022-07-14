# Title (replace with your title)

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

Anchors are the meta keytags ^ and $. They set a regex match to the beginning or end of the line of text.

The ^ anchor tag sets our match to the beginning of the line.

The $ anchor tag sets our match to the end of the line.

<pre>
Here we have /^cat/      Here we have /cat$/      /^cat$/

<mark style="font-weight: bold; background-color: #B0D0E9;">cat</mark>                      <mark  style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>                      <mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>

<mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>astrophe              catastrophe              catastrophe

wildcat                  wild<mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>                  wildcat

I love my cat            I love my <mark style="font-weight: bold; background-color: rgb(176, 208, 233);">cat</mark>            I love my cat

...
</pre>

You can combine both ^ and $ to find a match that is only at the beginning and end of the line. This will produce only the first string above.

### Quantifiers

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

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