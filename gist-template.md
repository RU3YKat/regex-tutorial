# Email Searching with RegEx

Regular Expressions, known as RegEx, is a tool common to many programming languages that allows defineable search and replacements in text. In JavaScript, regular expressions are considered objects. Using regex capabilities, it is easier to identify emails in data strings.

## Summary

This gist will discuss, explain, and provide examples for the regex code

```
 /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

that is used to match email address patterns within a string in JavaScript programming.

It will match the following example emails, as well as many others meeting the regex specifications:

```
stephen_king@author.com
e.dickinson1886@poet.net
```

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

First, note that a `\` is an escape character, meaning the character immediately following is a literal character, not metacharacter, unless it represents an existing regex component. Slashes `/` denote to JavaScript that the characters are regex metacharacters.

### Anchors

Anchors are regex tokens that aren't used to match certain characters, but instead specify (or assert) something about the string in question. An anchor is used to assert where the matching characters will be matched, e.g. the beginning or the end of the string.

`^` denotes the start of a string, or the start of a line, generally. The regex above uses `^` to denote the start of the email string to match.
`$` denotes the end of a string, of end of a line, generally. The regex above uses `?` to denote the end of the email string to match.

```

```
