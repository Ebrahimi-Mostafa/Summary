# Java
Source: https://www.youtube.com/watch?v=xk4_1vDrzzo&t=3305s

## 📋 Table of Contents  
0. [Run a simple Java program](#run-a-simple-java-program)
1. [Java tutorial for beginners](#java-tutorial-for-beginners)
    - [Print to the console](#print-to-the-console) 
    - [Escape sequences](#escape-sequences) 
    - [Comments](#comments)

<a id="run-a-simple-java-program"></a>
## `0.` Run a simple Java program
Assume that is structure of our project:
```
.
├── README.md
├── bin
│   └── Main.class
├── lib
└── src
    └── Main.java
```

Compile the source code:
```bash
javac -d bin src/Main.java
```

Run the program:
```bash
java -cp bin Main
```
> **Note:** `-cp` is short for `--class-path` which is used to specify where to find classes files.


<a id="java-tutorial-for-beginners"></a>
## `1.` Java tutorial for beginners

<a id="print-to-the-console"></a>
### Print to the console
This line just print out a string to the console `without a new line`:

```java
System.out.print("Hello World");
```
These lines print out a string to the console `with a new line`:

```java
System.out.println("Hello World");
System.out.print("Hello World\n");
```
The two lines above are equivalent.

> **Trick:** Instead of typing `System.out.println()`, we can type `sout` or `sysout` then press `Tab` key.

<a id="escape-sequences"></a>
### Escape sequences
| Escape sequence | Description |
| --------------- | ----------- |
| `\n` | New line |
| `\t` | Tab |
| `\\` | Backslash |
| `\"` | Double quote |
| `\'` | Single quote |
| `\r` | Carriage return |

> **Note:** `\r` is used to move the cursor to the beginning of the line.  

> **Note:** For print meaningful characters, we need to use escape sequences. For example, if we want to print a double quote, we need to use `\"` instead of `"` or if we want to print a backslash, we need to use `\\` instead of `\`.


<a id="comments"></a>
### Comments
- `Single line` comment:
```java
// This is a single line comment
```

- `Multi-line` comment:
```java
/*
This is a multi-line comment
*/
```
or
```java
/*
 * This is a multi-line comment
 */
```

- `Documentation` comment:
```java
/**
 * This is a documentation comment
 */
```

> **Note:** Documentation comment is used to generate documentation for our code.