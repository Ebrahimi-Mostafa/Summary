# Regular Expressions
Source: https://www.youtube.com/watch?v=m2zlSAsePNg&list=WL&index=37&t=569s


## Table of Contents
* [Syntax](#syntax)
* [Regex Cheatsheet](#regex-cheatsheet) 


### Syntax
`/regex/flags`  
* The regex is enclosed between two forward slashes.
* The flags are optional and are used to change the way the expression is interpreted.


### Regex Cheatsheet
* `^` &rarr; Start of string
    * `^abc` &rarr; Matches `abc` at the start of each line.
* `$` &rarr; End of string
    * `abc$` &rarr; Matches `abc` at the end of each line.
* `Character classes`
    * `[abc]` &rarr; Matches `a`, `b`, or `c`.
        * `a[bc]` &rarr; Matches `ab` or `ac`.
    * `|` &rarr; OR operator.
        * `a|b|c` &rarr; Matches `a`, `b`, or `c`.
    * `[^abc]` &rarr; Matches anything that is not `a`, `b`, or `c`.    
    * `[0-9]` &rarr; Matches any digit.
    * `[a-z]` &rarr; Matches any lowercase letter.
    * `[A-Z]` &rarr; Matches any uppercase letter.
        * Special characters (., *, +, ?) lose their special meaning inside [].  
    * `.` &rarr; Matches any character except newline.
    * `\.` &rarr; Matches a period.
    * `{}` &rarr; Matches a specific number of occurrences.
        * `a{3}` &rarr; Matches `aaa`.
        * `a{1,3}` &rarr; Matches `a`, `aa`, or `aaa`.
        * `a{1,}` &rarr; Matches `a` one or more times.
        * `a{0,}` &rarr; Matches `a` zero or more times.
    * `+` &rarr; Matches one or more of the preceding character.
        * `sa+` &rarr; Matches `sa`, `saa`, `saaa`, etc.
    * `*` &rarr; Matches zero or more of the preceding character.
    * `?` &rarr; Matches zero or one of the preceding character.
    * `\d` &rarr; Matches any digit.
    * `\D` &rarr; Matches any non-digit.
    * `\s` &rarr; Matches any whitespace character.
    * `\S` &rarr; Matches any non-whitespace character.
    * `\w` &rarr; Matches any alphanumeric character.
    * `\W` &rarr; Matches any non-alphanumeric character.
    * `\b` &rarr; Matches a word boundary, it's non-alphanumeric character(it is a zero-width match).
* Regex is `Greedy` by default.
    * `*?` &rarr; Matches zero or more of the preceding character in a non-greedy way.
    * `+?` &rarr; Matches one or more of the preceding character in a non-greedy way.
* Lookahead and Lookbehind
    * `(?=...)` &rarr; Positive lookahead.
    * `(?!...)` &rarr; Negative lookahead.
    * `(?<=...)` &rarr; Positive lookbehind.
    * `(?<!...)` &rarr; Negative lookbehind.
    > Lookahead and lookbehind assertions are zero-width assertions, they don't consume any characters.
    * lookahead is used in the end of the regex.
        * bar(?=bar)     finds the 1st bar ("bar" which has "bar" after it)  
        * bar(?!bar)     finds the 2nd bar ("bar" which does not have "bar" after it)
    * lookbehind is used in the beginning of the regex.
        * (?<=foo)bar    finds the 1st bar ("bar" which has "foo" before it)
        * (?<!foo)bar    finds the 2nd bar ("bar" which does not have "foo" before it)
* Capturing Groups: treat multiple characters as a single unit.
    * `()` &rarr; Capturing group.
        * (\d{1,2})-(\d{1,2})-(\d{4}) &rarr; Matches a date in the format `dd-mm-yyyy`.
    * `\1`, `\2`, etc. &rarr; Backreferences. reuse the value of a capturing group.
        * (a|b|cd)\1 &rarr; Matches `aa`, `bb`, or `cdcd`.
    * `(?:)` &rarr; Non-capturing group.
    * non-capturing group is used when you don't want to capture the group.
        * (?:\d{1,2}-){2}(\d{4}):\1 &rarr; Matches a date like 31-08-1994:1994, 1-3-2010:2010.