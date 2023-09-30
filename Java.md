# Java :computer:
Source: https://www.youtube.com/watch?v=xk4_1vDrzzo&t=3305s

## Table of Contents :clipboard:

0. [Run a simple Java program :card_file_box:](#run-a-simple-java-program)
1. [Java tutorial for beginners :book:](#java-tutorial-for-beginners)
    - [Print to the console :printer:](#print-to-the-console) 
    - [Escape sequences :arrow_right_hook:](#escape-sequences)
    - [Comments :speech_balloon:](#comments)
2. [Variables :1234:](#variables)
    - [Data types :floppy_disk:](#data-types)
3. [Swap two variables :arrows_counterclockwise:](#swap-two-variables)
4. [User input :keyboard:](#user-input)
5. [Expressions :abacus:](#expressions)
6. [GUI intro](#gui-intro)
7. [Math class](#math-class)
8. [Random numbers](#random-numbers)
9. [If statement](#if-statement)
10. [Switches](#switches)
11. [Logical Operators](#logical-operators)
12. [While loop](#while-loop)
13. [For loop](#for-loop)
14. [Nested loops](#nested-loops)
15. [Arrays](#arrays)
16. [2D Arrays](#2d-arrays)
17. [String methods](#string-methods)
18. [Wrapper classes](#wrapper-classes)
19. [ArrayList](#arraylist)
20. [2D ArrayList](#2d-arraylist)
21. [For each loop](#for-each-loop)
22. [Methods](#methods)
23. [Overloaded Methods](#overloaded-methods)
24. [Printf](#printf)
25. [Final Keyword](#final-keyword)
26. [Object](#object)  
27. [Object Constructors](#object-constructors)
28. [Variable Scope](#variable-scope)
29. [Overloading Constructors](#overloading-constructors)
30. [ToString Method](#tostring-method)
31. [Array of Objects](#array-of-objects)
32. [Object Passing](#object-passing)

<a id="run-a-simple-java-program"></a>
## 0. Run a simple Java program :card_file_box:
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
## 1. Java tutorial for beginners :book:

<a id="print-to-the-console"></a>
### Print to the console :printer:
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
### Escape sequences :arrow_right_hook:
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
### Comments :speech_balloon:
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
## 2. Variables :1234:
<a id="data-types"></a>
- Data types :floppy_disk:: 
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
## 3. Swap two variables :arrows_counterclockwise:

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
## 4. User input :keyboard:
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
## 5. Expressions :abacus:

- `Expression`: operands & operators
- `Operands`: values, variables, numbers, quantity
- `Operator`: + - * / %

```java
int x = 10;
x = x + 1; // 11
x += 1; // 12
x++; // 13
```


<a id="gui-intro"></a>
## 6. GUI intro :computer:

- `GUI`: Graphical User Interface
```java
import javax.swing.JOptionPane;

String name = JOptionPane.showInputDialog("Enter your name: "); // takes input as a String

JOptionPane.showMessageDialog(null, "Hello " + name); // shows a message
```

> **Note:** `JOptionPane` returns a `String` value.  

- Convert `String` to:
    - `int`: `Integer.parseInt(String)`
    - `double`: `Double.parseDouble(String)`


<a id="math-class"></a>

## 7. Math class
```java
double x = 3.14;
double y = -10;

Math.max(x, y); // 3.14
Math.min(x, y); // -10
Math.abs(y); // 10
Math.sqrt(x); // 1.772004514666935
Math.round(x); // 3
Math.ceil(x); // 4
Math.floor(x); // 3
Math.pow(x, 2); // 9.8596
```

<a id="random-numbers"></a>

## 8. Random numbers
```java
import java.util.Random;

Random random = new Random();

int x = random.nextInt()
int y = random.nextInt(10); // 0 <= y < 10

double z = random.nextDouble(); // 0 <= z < 1

boolean b = random.nextBoolean();
```


<a id="if-statement"></a>

## 9. If statement
```java
int time = 14;

if (time <= 10)
    System.out.println("Good morning!");
else if (time <= 18)
    System.out.println("Good day!");
else
    System.out.println("Good evening!");
```


<a id="switches"></a>

## 10. Switches
```java
int number= 20;  

switch(number){  
    case 0, 10: 
        System.out.println("0, 10");
        break;
    case 20: 
        System.out.println("20");  
        break;
    case 30: 
        System.out.println("30");
        break;  
    default:
        System.out.println("Not in 0, 10, 20 or 30"); 
}
```


<a id="logical-operators"></a>

## 11. Logical Operators

Used to connect two or more expressions.

| Operator | Description |
| -------- | ----------- |
| `&&` | AND |
| `\|\|` | OR |
| `!` | NOT |


<a id="while-loop"></a>

## 12. While loop

- while
```java
String name = "";
while (name.isBlank()) {
    name = scanner.nextLine();
}
System.out.println("Hello " + name);
```

- do while
```java
String name = "";
do {
    name = scanner.nextLine();
} while (name.isBlank());
System.out.println("Hello " + name);
```


<a id="for-loop"></a>

## 13. For loop

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```


<a id="nested-loops"></a>

## 14. Nested loops

```java
Scanner scanner = new Scanner(System.in);
int rows;
rows = scanner.nextInt();
scanner.close();

for (int i = 0; i < rows; i++) {
    for (int j = 0; j < (rows - i); j++)
        System.out.print('*');
    System.out.println();
}
```


<a id="arrays"></a>

## 15. Arrays
- Declaration
```java
String[] name = new String[3];
name[0] = "John";
name[1] = "Bob";
name[2] = "Alice";

// or 

String[] name = {"John", "Bob", "Alice"};
```
- Iteration
```java
for (int i = 0; i < name.length; i++) {
    System.out.println(name[i]);
}

// or

for (String i : name) {
    System.out.println(i);
}
```


<a id="2d-arrays"></a>

## 16. 2D Arrays
- Declaration
```java
int[][] int_array = {{1, 2, 3}, {4, 5, 6}};

// or

int[][] int_array = new int[2][3];

int_array[0][0] = 1;
int_array[0][1] = 2;
int_array[0][2] = 3;
int_array[1][0] = 4;
int_array[1][1] = 5;
int_array[1][2] = 6;
```
- Iteration
```java
for (int i = 0; i < int_array.length; i++) {
    for (int j = 0; j < int_array[i].length; j++)
        System.out.print(int_array[i][j] + " ");
    System.out.println();
}

// or

for (int[] a : int_array) {
    for (int b : a){
        System.out.print(b + " ");
    }
    System.out.println();
}
```

<a id="string-methods"></a>

## 17. String methods
```java
String name = "Java";
```

| Method | Return type | Output |
| ------ | ------- | ------ |
| `name.equals("java")` | `boolean` | `false` |
| `name.equalsIgnoreCase("java")` | `boolean` | `true` |
| `name.length()` | `int` | `4` |
| `name.charAt(0)` | `char` | `J` |
| `name.indexOf('a')` | `int` | `1` |
| `name.indexOf('a', fromIndex:2)` | `int` | `3` |
| `name.indexOf('j', fromIndex:1)` | `int` | `-1` |
| `name.indexOf("va")` | `int` | `2` |
| `name.lastIndexOf('a')` | `int` | `3` |
| `name.isEmpty()` | `boolean` | `false` |
| `name.toUpperCase()` | `String` | `JAVA` |
| `name.toLowerCase()` | `String` | `java` |
| `name.replace('a', '$')` | `String` | `J$v$` |
| `"    Java  JDK    ".trim()` | `String` | `Java  JDK` |

> **Note:**
>- `indexOf()` method returns `-1` if the character is not found.
>- `trim()` method removes white spaces from both sides of the string. " Java JDK " &rarr; "Java  JDK"


<a id="wrapper-classes"></a>

## 18. Wrapper classes
Wrapper classes provide a way to use primitive data types as objects.  
Advantage of wrapper classes is that, we can use them with `collections` (like ArrayList and HashMap) and also they provide many `useful methods`.  
Disadvantage of wrapper classes is that, it is `slower` than primitive data types.

| Primitive | Wrapper |
| --------- | ------- |
| `byte` | `Byte` |
| `short` | `Short` |
| `int` | `Integer` |
| `long` | `Long` |
| `float` | `Float` |
| `double` | `Double` |
| `boolean` | `Boolean` |
| `char` | `Character` |

* `Autoboxing`: Converting a primitive value into an object of the corresponding wrapper class is called autoboxing.
```java
int a = 20;
Integer x = Integer.valueOf(a);//converting int into Integer explicitly  
Integer j = a;//autoboxing, now compiler will write Integer.valueOf(a) internally
```

* `Unboxing`: Converting an object of a wrapper type to its corresponding primitive value is called unboxing.
```java
Integer a=new Integer(3);    
int i=a.intValue();//converting Integer to int explicitly  
int j=a;//unboxing, now compiler will write a.intValue() internally    
```


<a id="arraylist"></a>

## 19. ArrayList
ArrayList is a resizable array.

```java
import java.util.ArrayList;

ArrayList<String> cars = new ArrayList<String>();

cars.add("Volvo");
cars.add("BMW");
cars.add("Ford");

System.out.println(cars); // [Volvo, BMW, Ford]

cars.set(1, "Benz"); // set -> replace

for (int i = 0; i < cars.size(); i++) {
    System.out.println(cars.get(i));
} // Volvo Benz Ford

cars.remove(1); // remove by index

for (String i : cars) {
    System.out.println(i);
} // Volvo Ford

cars.add(1, "Benz"); // add by index
// Volvo Benz Ford

cars.clear(); // remove all elements
```

> **Note:** `ArrayList` stores objects. If we want to store other types of data, we need to use `wrapper classes`.


<a id="2d-arraylist"></a>

## 20. 2D ArrayList
```java
import java.util.ArrayList;

ArrayList<ArrayList<Integer>> list = new ArrayList<ArrayList<Integer>>();

ArrayList<Integer> row1 = new ArrayList<Integer>();
row1.add(1);
row1.add(2);
row1.add(3);

list.add(row1);
// list = [[1, 2, 3]]


list.add(new ArrayList<Integer>(Arrays.asList(4, 5, 6)));
// list = [[1, 2, 3], [4, 5, 6]]


list.add(new ArrayList<Integer>());
ArrayList<Integer> row3 = list.get(2);
row3.add(7);
row3.add(8);
row3.add(9);
// list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

System.out.println(list.get(1).get(2)); // 6
```

> **Note:** `ArrayList` stores objects. If we want to store other types of data, we need to use `wrapper classes`.


<a id="for-each-loop"></a>

## 21. For each loop
For each loop is used to iterate through an array or collection.

```java
ArrayList<String> cars = new ArrayList<String>();
cars.add("Volvo");
cars.add("BMW");
cars.add("Ford");

for (String i : cars) {
    System.out.println(i);
}
/*
Volvo
BMW
Ford
*/
```

```java
int[][] int_array = {{1, 2, 3}, {4, 5, 6}};

for (int[] a : int_array) {
    for (int b : a){
        System.out.print(b + " ");
    }
    System.out.println();
}
/*
1 2 3
4 5 6
*/
```


<a id="methods"></a>

## 22. Methods
```java
public static void main(String[] args) {
    System.out.println(sum(5, 10));
}

static int sum(int a, int b) {
    return a + b;
}
```
    
```java
public static void main(String[] args) {
    int x = 5;
    change(x);
    System.out.println(x); // 5
}

static void change(int x) {
    x = 10;
}
```

```java
public static void main(String[] args) {
    int[] x = {1, 2, 3};
    change(x);
    System.out.println(x[0]); // 10
}

static void change(int[] x) {
    x[0] = 10;
}
```

```java
public static void main(String[] args) {
    int[] x = {1, 2, 3};
    change(x);
    System.out.println(x[0]); // 1
}

static void change(int[] x) {
    x = new int[3];
    x[0] = 10;
}
```


<a id="overloaded-methods"></a>

## 23. Overloaded Methods

- Overloaded methods are methods with the same name but different parameters.
- method signature `=` method name `+` parameter list

```java
public static void main(String[] args) {
    System.out.println(sum(5, 10)); // #1# 15
    System.out.println(sum(5, 10, 15)); // #2# 30

    System.out.println(sum(5.5, 10.5)); // #3# 16.0
    System.out.println(sum(5.5, 10.5, 15.5)); // #4# 31.5
}

static int sum(int a, int b) {
    System.out.print("#1# ");
    return a + b;
}
static int sum(int a, int b, int c) {
    System.out.print("#2# ");
    return a + b + c;
}

static double sum(double a, double b) {
    System.out.print("#3# ");
    return a + b;
}
static double sum(double a, double b, double c) {
    System.out.print("#4# ");
    return a + b + c;
}
```


<a id="printf"></a>

## 24. Printf
```java
System.out.printf("Hello John, your age is %d", 20);
// Hello John, your age is 20
```

* two arguments &rarr; format string + (object, variable, value)
* `%[flags][width][.precision]conversion-character`

| Conversion Character | Description |
| -------------------- | ----------- |
| `d` | decimal integer |
| `f` | floating-point number |
| `c` | character |
| `s` | string |
| `b` | boolean |

| Flag | Description |
| ---- | ----------- |
| `-` | left-justify |
| `+` | output a plus ( + ) or minus ( - ) sign for a numeric value |
| `0` | numeric values are zero-padded |
| `,` | comma grouping separator if numbers > 1000 |

| Width | Description |
| ----- | ----------- |
| `number` | minimum number of characters to be written as output |
| `*` (In C language) | width is not specified in the format string, but as an additional integer value argument preceding the argument that has to be formatted |

| Precision | Description |
| --------- | ----------- |
| `number` | for floating point number, it specifies the number of digits to be printed after the decimal point |
| `.*` (In C language) | precision is not specified in the format string, but as an additional integer value argument preceding the argument that has to be formatted |

```java
System.out.printf("The value of x is %+d\n", 5);
// The value of x is +5

System.out.printf("The value of x is %05d\n", 5);
// The value of x is 00005

System.out.printf("The value of x is %10d\n", 5);
// The value of x is          5

System.out.printf("The value of x is %,d\n", 12345678);
// The value of x is 12,345,678

System.out.printf("The value of x is %.2f\n", 5.14614);
// The value of x is 5.15

System.out.printf("The value of x is %.2f\n", 5.1);
// The value of x is 5.10

System.out.printf("The value of x is %c\n", 65);
// The value of x is A
```


<a id="final-keyword"></a>

## 25. Final Keyword
- `final` keyword is used to make a variable `constant`.

```java
final double PI = 3.14;
PI = 3.1415; // Error
```


<a id="object"></a>

## 26. Object

```java
// Car.java
public class Car {
    String make = "Ford";
    String model = "Mustang";
    String color = "Black";
    int year = 2020;

    void drive() {
        System.out.println("You drive the car");
    }
    void brake() {
        System.out.println("You step on the brakes");
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        System.out.println(myCar.make); // Ford
        System.out.println(myCar.model); // Mustang
        myCar.drive(); // You drive the car

        Car myCar2 = new Car();
        myCar2.make = "BMW";
        myCar2.model = "X5";
        myCar2.color = "White";
        myCar2.year = 2021;
        System.out.println(myCar2.make); // BMW
        System.out.println(myCar2.model); // X5
        myCar2.drive(); // You drive the car
    }
}
```

> **Note:** `new` keyword is used to create an object.


<a id="object-constructors"></a>

## 27. Object Constructors
* A constructor in Java is a special method that is used to initialize objects.
* The constructor is called when an object of a class is created.
* It can be used to set initial values for object attributes.

```java
// Human.java
public class Human {
    String name;
    int age;

    public Human(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("Hello, my name is " + name + " and I am " + age + " years old.");
    }
    // Or
    public void introduce_v2() {
        System.out.println("Hello, my name is " + this.name + " and I am " + this.age + " years old.");
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Human john = new Human("John", 20);
        john.introduce(); // Hello, my name is John and I am 20 years old.
        john.introduce_v2(); // Hello, my name is John and I am 20 years old.

        Human bob = new Human("Bob", 25);
        bob.introduce(); // Hello, my name is Bob and I am 25 years old.
    }
}
```

> **Note:** `this` keyword is used to refer to the current object.


<a id="variable-scope"></a>

## 28. Variable Scope
* The scope of a variable is the part of the program where the variable is accessible.
* Variables declared within a method are `local` variables.
* Variables declared outside a method are 'global' variables.

```java
public class Main {
    int x = 5; // global variable

    public static void main(String[] args) {
        int y = 10; // local variable
        System.out.println(x); // 5
        System.out.println(y); // 10
    }
}
```


<a id="overloading-constructors"></a>

## 29. Overloading Constructors
* Overloaded constructors allow us to have more than one constructor with different parameters.
* name + parameter list = method signature

```java
// Human.java
public class Human {
    String name;
    int age;

    public Human() {
        name = "John";
        age = 20;
    }

    public Human(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("Hello, my name is " + name + " and I am " + age + " years old.");
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Human john = new Human();
        john.introduce(); // Hello, my name is John and I am 20 years old.

        Human bob = new Human("Bob", 25);
        bob.introduce(); // Hello, my name is Bob and I am 25 years old.
    }
}
```


<a id="tostring-method"></a>

## 30. ToString Method
* The `toString()` method returns the string representation of the object.
* If we print an object, java compiler internally invokes the `toString()` method on the object.
* We can call `toString()` method implicitly or explicitly.

```java
// Human.java
public class Human {
    String name;
    int age;

    public Human(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String toString() {
        return "Hello, my name is " + name + " and I am " + age + " years old.";
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Human john = new Human("John", 20);

        // Implicitly
        System.out.println(john); // Hello, my name is John and I am 20 years old.

        // Explicitly
        System.out.println(john.toString()); // Hello, my name is John and I am 20 years old.
    }
}
```


<a id="array-of-objects"></a>

## 31. Array of Objects
```java
// Food.java
public class Food {
    String name;
    
    Food (String name) {
        this.name = name;
    }
}
```

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Food[] foods1 = {new Food("Pizza"), new Food("Hamburger"), new Food("Hotdog")};

        for (int i = 0; i < foods1.length; i++) {
                System.out.println(foods1[i].name);
        }
        /*
        Pizza
        Hamburger
        Hotdog
        */
    }
}
```
or
```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Food[] foods2 = new Food[3];
        foods2[0] = new Food("Pizza");
        foods2[1] = new Food("Hamburger");
        foods2[2] = new Food("Hotdog");

        for (int i = 0; i < foods2.length; i++) {
                System.out.println(foods2[i].name);
        }
        /*
        Pizza
        Hamburger
        Hotdog
        */
    }
}
```
or
```java
// Main.java
public class Main {
    public static void main(String[] args) {
        Food[] foods3 = new Food[3];
        Food food1 = new Food("Pizza");
        Food food2 = new Food("Hamburger");
        Food food3 = new Food("Hotdog");

        foods3[0] = food1;
        foods3[1] = food2;
        foods3[2] = food3;

        for (Food i : foods3) {
                System.out.println(i.name);
        }
        /*
        Pizza
        Hamburger
        Hotdog
        */
    }
}
```


<a id="arraylist-of-objects"></a>

## 32. ArrayList of Objects
