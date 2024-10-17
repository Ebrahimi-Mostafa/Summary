# Regular Expressions (Regex)
Source: [YouTube Video](https://www.youtube.com/watch?v=m2zlSAsePNg&list=WL&index=37&t=569s)

## Table of Contents
1. [Regex Syntax](#regex-syntax)
2. [Regex Cheatsheet](#regex-cheatsheet)
    1. [Anchors](#anchors)
    2. [Character Classes](#character-classes)
    3. [Quantifiers](#quantifiers)
    4. [Metacharacters](#metacharacters)
    5. [Assertions (Lookahead/Lookbehind)](#assertions-lookaheadlookbehind)
    6. [Groups and Backreferences](#groups-and-backreferences)

## Regex Syntax
A regular expression (regex) consists of a pattern enclosed between two forward slashes and may have optional flags.  
`/pattern/flags`

### Flags:
- `g` &rarr; Global search (find all matches)
- `i` &rarr; Case-insensitive search
- `m` &rarr; Multi-line mode

## Regex Cheatsheet

### 1. Anchors
Anchors are used to match positions within a string rather than characters.

- `^` &rarr; Start of string or line  
  - Example: `^abc` matches "abc" only at the start of the string.
- `$` &rarr; End of string or line  
  - Example: `abc$` matches "abc" only at the end of the string.

### 2. Character Classes
Character classes define a set of characters to match.

- `[abc]` &rarr; Matches any one of `a`, `b`, or `c`
    - Example: `a[bc]` matches "ab" or "ac".
- `[^abc]` &rarr; Matches any character *except* `a`, `b`, or `c`
- `[0-9]` &rarr; Matches any digit.
- `[a-z]` &rarr; Matches any lowercase letter.
- `[A-Z]` &rarr; Matches any uppercase letter.
- `.` &rarr; Matches any character *except* newline.
- `\.` &rarr; Escapes special characters, e.g., matches a literal period `.`.

### 3. Quantifiers
Quantifiers specify how many times the preceding character or group must occur.

- `{n}` &rarr; Matches exactly `n` occurrences.
    - Example: `a{3}` matches "aaa".
- `{n,}` &rarr; Matches `n` or more occurrences.
    - Example: `a{1,}` matches "a", "aa", "aaa", etc.
- `{n,m}` &rarr; Matches between `n` and `m` occurrences.
    - Example: `a{1,3}` matches "a", "aa", or "aaa".
- `*` &rarr; Matches zero or more occurrences.
    - Example: `ca*t` matches "ct", "cat", or "caat".
- `+` &rarr; Matches one or more occurrences.
    - Example: `sa+` matches "sa", "saa", "saaa", etc.
- `?` &rarr; Matches zero or one occurrence (optional).
    - Example: `colou?r` matches both "color" and "colour".

#### Greediness:
- By default, quantifiers are *greedy*, meaning they try to match as much as possible.
    - Example: `.*` matches as much text as possible.
- Use `*?`, `+?`, `??` to make quantifiers *non-greedy*.
    - Example: `.*?` matches as little text as possible.

### 4. Metacharacters
Metacharacters have special meanings in regex patterns.

- `|` &rarr; OR operator.
    - Example: `a|b|c` matches "a", "b", or "c".
- `\d` &rarr; Matches any digit (equivalent to `[0-9]`).
- `\D` &rarr; Matches any non-digit character.
- `\s` &rarr; Matches any whitespace character (spaces, tabs, line breaks).
- `\S` &rarr; Matches any non-whitespace character.
- `\w` &rarr; Matches any alphanumeric character (letters, digits, and underscores).
- `\W` &rarr; Matches any non-alphanumeric character.
- `\b` &rarr; Matches a word boundary (zero-width assertion, i.e., not a character).

### 5. Assertions (Lookahead/Lookbehind)
Assertions are zero-width checks, meaning they don't consume characters in the string.

- **Lookahead:**
  - `(?=...)` &rarr; Positive lookahead (asserts what *must* follow).
    - Example: `bar(?=bar)` matches "bar" if it is followed by "bar".
  - `(?!...)` &rarr; Negative lookahead (asserts what *must not* follow).
    - Example: `bar(?!bar)` matches "bar" if it is *not* followed by "bar".
- **Lookbehind:**
  - `(?<=...)` &rarr; Positive lookbehind (asserts what *must* precede).
    - Example: `(?<=foo)bar` matches "bar" if preceded by "foo".
  - `(?<!...)` &rarr; Negative lookbehind (asserts what *must not* precede).
    - Example: `(?<!foo)bar` matches "bar" if *not* preceded by "foo".

> **Note:** Assertions do not consume characters, meaning they just "look" at surrounding text without including it in the match.

### 6. Groups and Backreferences
Groups are used to capture sub-patterns within parentheses.

- `()` &rarr; Capturing group.
    - Example: `(\d{1,2})-(\d{1,2})-(\d{4})` matches dates like "dd-mm-yyyy".
- `\1`, `\2`, etc. &rarr; Backreferences to captured groups.
    - Example: `(a|b|cd)\1` matches "aa", "bb", or "cdcd".
- `(?:...)` &rarr; Non-capturing group (groups without storing).
    - Example: `(?:\d{1,2}-){2}(\d{4}):\1` matches dates like "31-08-1994:1994" or "1-3-2010:2010".