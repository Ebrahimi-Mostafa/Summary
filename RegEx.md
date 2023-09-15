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
    * `[0-9]` &rarr; Matches any digit.

<!-- See until 07:07 -->



<!-- 
    * `[abc]` &rarr; Matches `a`, `b`, or `c`.
    * `[a-z]` &rarr; Matches any lowercase letter.
    * `[A-Z]` &rarr; Matches any uppercase letter.
    * `[0-9]` &rarr; Matches any digit.
    * `[a-zA-Z0-9]` &rarr; Matches any alphanumeric character.
    * `[^abc]` &rarr; Matches anything that is not `a`, `b`, or `c`. -->