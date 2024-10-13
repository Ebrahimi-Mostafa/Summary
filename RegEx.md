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
    * `[^abc]` &rarr; Matches anything that is not `a`, `b`, or `c`.    
    * `[0-9]` &rarr; Matches any digit.
    * `[a-z]` &rarr; Matches any lowercase letter.
    * `[A-Z]` &rarr; Matches any uppercase letter.
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
* Regex is `Greedy` by default.
    * `*?` &rarr; Matches zero or more of the preceding character in a non-greedy way.
    * `+?` &rarr; Matches one or more of the preceding character in a non-greedy way.