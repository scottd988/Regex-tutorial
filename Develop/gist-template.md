# Regex Statement Breakdown - HTML Tags

## Summary
The regex statement below is meant to match to HTML tags and their content:
`/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`


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

Caret (^): The caret anchor indicates the start of a line. When using it in the beginning of a regex segment, the beginning of the string should match. For example, the regex `^<([a-z]+)` signifies a string that begins with `<` followed by one or more lowercase letters like an `<h1>` or `<img`.
The dollar sign anchor `$` indicates the end of a line. 

### Quantifiers
Asterisks `*` match 0 or more occurrences of the element that comes before. 
Plus sign `+` matches 1 or more occurrences of the preceding element. So the snippet `[a-z]+` would match one or more lowercase letter. Or `([^<]+)*` matches 0 or more characters that are not `<`. This part could represent attributes within the tag.

### Grouping Constructs
Prenthesis are used for grouping. For example, the regex `(?:>(.*)<\/\1>|\s+\/>)` is a non capturing group. It matches either `>(.*)<\/\1>` or `\s+\/>`. They are seperated by the OR operator. The first section describes the end of the opening tag `>` then any characters `(.*)` until encountering a closing tag `<\/\1>`. Or `\s+\/>` which matches a whitespace character followed by `/>` for self closing tags.

### Bracket Expressions
Bracket expressions match any character inside brackets or a range of letters. For example, `([a-z]+)` captures one or more lowercase letters. 

### Character Classes
Character classes are special notations that match any symbol from a certain set. Some common character classes include:
- `\s` Matches any white space; as in `\s+\/>` which indicates a space followed by a closing tag.
- `\1` Refers to the first capturing group. 

### The OR Operator
The pipe symbol `|` is the logical "OR" operator between expressions. The regex `(?:>(.*)<\/\1>|\s+\/>)` signifies that either `>(.*)<\/\1>` or `\s+\/>` should be matched. Opening and closing tags with content or self closing tags are captured by these expressions.

### Flags

### Character Escapes
To match characters that are "special" in regex syntax (like ., *, ?, etc.), you need to escape them with a backslash \. For example `<\/\1>` escapes the `/` for closing HTML tags and `1` to signify the first capturing group.

## Author

My name is Scott, I am a software developer trying to learn more everyday. 
