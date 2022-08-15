# Regex-Tutorial

This tutorial is to explain what the regular expression is and describe how a specific regular expression, or regex, functions by breaking down each part of the expression.

## Summary

To start off to explain regex components, I'm going to shortly explain what the regular expression is. A *regex*, which is short for *regular expression*, is a sequence of characters that specifies a search pattern in text. Usually, regex is used to find or find and replace a certain pattern of string. And sometimes regex is used to verify that a string has a certain pattern.

There are two ways to create a regular expression in Javascript. It can be created with *RexExp constructor* or by using *forward slashes* to open and close the pattern.

In the below, I'm going to walk through some regular expression components. And when you click the links in the table of contents, it will direct you to each section.

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
The characters `^` and `$` are both considered to be **anchors**.

The `^` anchor signifies a string that begins with the characters that follow its pattern. It will check either the first character or first substring to have a certain pattern of string. And this is also case-sensitive.

The `$` anchor signifies a string that ends with the characters that precede it. It will check either the last character or the last substring to have a certain pattern of string. Just as with the `^` chacater, it can be preceded by an exact string or a range of possible matches.

### Quantifiers
**Quantifiers** specify how many instances of a character, group or character class must be present in the input for a match to be found. The following is a list of some **greedy** quantifiers.

- `*` - Matches zero or more times.
- `+` - Matches one or more times.
- `?` - Matches zero or one time.
- `{n}` - Matches exactly *n* times.
- `{n, }` - Matches at least *n* times.
- `{n, m}` - Matches from *n* to *m* times.

Ordinarily, quantifiers are greedy. They cause the regular expression engine to match as many occurences of particular pattern as possible. Each of these quantifiers can be made **lazy** by adding the `?` symbol after it, meaning it will match as few occurrences as possible.

### OR Operator
An OR operator means it will check a string matches either one of given regex patterns. A character for an OR operatior is `|`. If two regex patterns, for example, are given `(abc)|(xyz)`, the regex engine will find if a string has `adc` or `xyz`.

### Character Classes (Greedy and Lazy Match)
A **character class** in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match.

The below are some general character classes with descriptions.

- `.` - As a wildcard, a dot will match any character except the newline character.
- `\d` - Matches any numberal digit. This is equivalent to the bracket expression `[0-9]`.
- `\w` - Matches any alphanumeric character. This is equivalent to the bracket expression `[a-zA-Z0-9]`.
- `\s` - Matches a single whitespacing chacater, including tabs and line breaks.

### Flags
**Flags** are placed at the end of a regex, after the closed slash, and flags add an functionality or limits for the regex. There are six general flags, but the three flags below are commonly used.

- `g` - Global search: the regex should be tested against all possible matches in a string.
- `i` - Case insensitive search: case should be ignored while attempting a match in a string.
- `m` - Multi-line search: a multi-line input string should be treated as multiple lines.

### Grouping and Capturing // Back-references
Capturing groups are a way to treat multiple characters as as single unit. They are created by placing the characters to be grouped inside of a set of parentheses.

The portion of the input string that matches the capturing group will be saved in memory for later recall via **backreferences**. A backreference is specified in the regular expression as a backslash (\) followed by a digit indicating the number of the group to be recalled.

### Bracket Expressions
A bracket expression is an regular expression that shall match a specific set of single characters or a specific set of multi-characters.

- `[]` - Square brackets indicate a set of characters to match. Any individual character between the brackets will match. 
- `{}` - Curly brackets are used to specify an exact amount of things to match. They are used after an expression, such as `\abc{2}\` will match `abc` twice.

### Boundaries
The word boundary `\b` matches positions where one side is a word character (usually a letter, digit, or underscore-but see below for variations across engines) and the other side is not a word character.

The regex `\bcat\b` would therefore match *cat* in *a black cat*, but it wouldn't match it in *catatonic*, *tomcat*, or *certificate*.

### Look-ahead and Look-behind
Lookahead and lookbehind is collectively called "lookaround". A sign for lookahead is (?=foo) which asserts that following string of the current position would be *foo*. A sign for lookbehind is (?<=foo) which asserts that preceding string of the current position would be *foo*.

## Author

If you have any questions about the repo, open an issue or contact me directly at my email address kbjss071@gmail.com.

More of my works can be found at my GitHub account kbjss071.

## References
- rexegg.com
- javascript.plainenglish.io/regular-expression
- developer.mozilla.org
- docs.oracle.com
- coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial