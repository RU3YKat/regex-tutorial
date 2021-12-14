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

### Quantifiers

Quantifiers denote how many times the specified group of characters must be repeated for a successful match.

`+` denotes the character group specified must repeat 1 or more times.

The regex above uses `+` to denote the character string represented and contained by:
`[`

- the range a-z (case specific) and the range 0-9,
- an underscore `_`, which doesn't need to be escaped to be taken literally,
- a period `.`, which requires a backslash `\` to be read literally,
- a hyphen `-`, which also does not require an escape when it is present at the beginning or end of a character class.
  `]`

to be repeated one or more times, having all instances found.

`{}` denotes the number of repetitions to be applied to the character string specified. The comma `,` denotes the range of repeat values.
The above regex uses `{}` to specify the repeat of a single character, between 2 and 6 times, defined by the preceeding metacharacters ().

### OR Operator

The OR operator `|` is not represented in the regex above, but represents possible options delimited by values on either side of the operator.

### Character Classes

A character class is represented by the opening and closing brackets, `[]`. They indicate a match to made with any of the enclosed characters.

The regex above uses `[]` to denote the character class including:
`[`

- the range a-z (case specific) and the range 0-9,
- an underscore `_`, which doesn't need to be escaped to be taken literally,
- a period `.`, which requires a backslash `\` to be read literally,
- a hyphen `-`, which also does not require an escape when it is present at the beginning or end of a character class.

`]`

### Flags

Although they are not applied in the email regex, forward slashes `/`, denote a pattern that can optionally be followed by flags. Seven flags are currently used in JavaScript regex, all reprsenting a boolean `true` for their respective specifications:

`/d` or hasIndices flag, follows the regex start and end specifications for a capture group. It indicates a match of the capture group.
`/g` or global property flag, tests all possible matches in a string.
`/i` or ignoreCase flag, where cases are ignored in a string.
`/m` or multiline flag, where the start `^` and end `$` can match the start and end of any line within the string.
`/s` or dotAll flag, where all Unicode indicating any line terminator is accepted.
`/u` or Unicode flag, accepting any Unicode code point escapes as such.
`/y` or sticky flag, where only the matched index is the first incidence. This flag takes precedence over any global designations.
