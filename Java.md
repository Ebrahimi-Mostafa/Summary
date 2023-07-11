# Java
Source: https://www.youtube.com/watch?v=xk4_1vDrzzo&t=3305s

## 📋 Table of Contents  
0. [Run a simple Java program](#run-a-simple-java-program)
1. [Java tutorial for beginners](#java-tutorial-for-beginners)
    - [Print to the console](#print-to-the-console) 
    - [Escape sequences](#escape-sequences) 
    - [Comments](#comments)
2. [Variables](#variables)
    - [Data types](#data-types)
3. [Swap two variables](#swap-two-variables)
4. [:keyboard: User input](#user-input)
5. [expressions](#expressions)

<a id="run-a-simple-java-program"></a>
## 0. Run a simple Java program
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
## 1. Java tutorial for beginners

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


<a id="variables"></a>
## 2. Variables
<a id="data-types"></a>
- Data types:
    - Primitive data types:
        - `boolean`: 1 byte
        - `byte`: 1 byte
        - `short`: 2 bytes
        - `int`: 4 bytes
        - `long`: 8 bytes
        - `float`: 4 bytes
        - `double`: 8 bytes
        - `char`: 2 bytes
    - Reference data types:
        - `String`
        - `Array`
        - `Interface`
        - `Class`
        - `Enum`
        - `...`

| Data type | Size | Description |
| --------- | ---- | ----------- |
| `boolean` | 1 bit | Stores `true` or `false` values |
| `byte` | 1 byte | Stores whole numbers from `-128` to `127` |
| `short` | 2 bytes | Stores whole numbers from `-32,768` to `32,767` |
| `int` | 4 bytes | Stores whole numbers from `-2,147,483,648` to `2,147,483,647` |
| `long` | 8 bytes | Stores whole numbers from `-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807` |
| `float` | 4 bytes | Stores fractional numbers. Sufficient for storing `6` to `7` decimal digits |
| `double` | 8 bytes | Stores fractional numbers. Sufficient for storing `15` decimal digits |
| `char` | 2 bytes | Stores a single character/letter or ASCII values |
| `String` | varies | Stores a sequence of characters |

> **Note:** `String` is not a primitive data type. It is a reference data type. However, it is one of the most used data types in Java.

| Primitive | Reference |
| --------- | --------- |
| 8 types | unlimited (user-defined) |
| Stores data | Stores address of the data stored somewhere else in memory |
| can only hold 1 value | could hold more than 1 value |
| less memory | more memory |
| faster | slower |

> **Note:**   
> `Primitives` &rarr; starts with `lowercase` letter.  
> `Reference` &rarr; starts with `uppercase` letter.

> **Note:** String + Number = String
```java
String x = "Your number is: "
int y = 10;
String z = x + y; // z = "Your number is: 10"
```

> **Note:** We can't give multi-argument to `System.out.println()` method.  
> We need to use `+` operator to concatenate the arguments.
```java
System.out.println("Hello", "World"); // Error
System.out.println("Hello" + "World"); // HelloWorld
```

In java, for assignment long and float, we need to add `L`(or `l`) and `F`(or `f`) respectively at the end of the number.
```java
long x = 10000000000L;
float y = 5.75F;
```


<a id="swap-two-variables"></a>
## 3. Swap two variables

```java
String x = "Water";
String y = "Milk";
System.out.println("x: " + x + "\n" + "y: " + y);

String temp;
temp = x;
x = y;
y = temp;
System.out.println("After SWAP");
System.out.println("x: " + x + "\n" + "y: " + y);
```


<a id="user-input"></a>
## 4. :keyboard:User input 
First, we need to import `Scanner` class from `java.util` package:
```java
import java.util.Scanner;
```

Then, we need to create a `Scanner` object that takes input from `System.in`:
```java
Scanner scanner = new Scanner(System.in);
```

Finally, we can use `Scanner` object to take input from user:
- `nextLine()` &rarr; takes input as a `String`
```java
String name = scanner.nextLine();
```
- `nextInt()` &rarr; takes input as an `int`
```java
int age = scanner.nextInt();
```

> **Note:** `nextLine()` method takes the whole line as input. but `nextInt()` method takes only the first token as input, and the rest of the line is ignored.  

> **Note:** After use `nextInt()` method, we need to use `nextLine()` method to take the rest of the line as input and `clear the input buffer`.


<a id="expressions"></a>
## 5. Expressions