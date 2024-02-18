# JavaScript
Source: https://www.youtube.com/watch?v=8dWL3wF_OMw

## 📋 Table of Contents
0. [Setup](#Setup)
1. [JavaScript tutorial for beginners](#JavaScript-tutorial-for-beginners)
2. [Variables](#Variables)
3. [Arithmetic expressions](#Arithmetic-expressions)
    1. [Augmented assignment operator](#Augmented-assignment-operator)
    2. [Operator precedence](#Operator-precedence)
4. [User input](#User-input)
    1. [Window prompt](#Window-prompt)
    2. [HTML textbox](#HTML-textbox)
5. [Type conversion](#Type-conversion)
6. [Const](#Const)
7. [Math](#Math)
<!-- 8. Counter program -->


<a id="Setup"></a>  
## Setup
- Install live server extension in VS Code
- Create a folder for the project
- Create an index.html file like this:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lesson</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <script src="index.js"></script>
</body>
</html>
```
or you can use the shortcut `!` and press `Tab` in VS Code to generate the above code.  
- Create a style.css
- Create a index.js
- In VS Code, right click on the index.html file and select "Open with Live Server"


<a id="JavaScript-tutorial-for-beginners"></a>
## 1. JavaScript tutorial for beginners
- Print to console
```javascript
console.log("Hello World");
```
> **Note:** The semicolon is optional in JavaScript.

- Alert box
```javascript
window.alert("HELLO WORLD");
```

- Comments
    - Single line comment
    ```javascript
    // This is a single line comment
    ```
    - Multi line comment
    ```javascript
    /*
        This
        is
        a
        multi
        line
        comment
    */
    ```


<a id="Variables"></a>
## 2. Variables
- Declare a variable
    - `var` is the old way of declaring a variable
    - `let` is the new way of declaring a variable
    - `const` is the new way of declaring a constant
    <br> <br>


    - `let`

    ```javascript
    let name = "John";
    console.log(name);
    ```

    or
 
    ```javascript
    let name;
    name = "John";
    console.log(name);
    ```
    > **Note:** single quotes `'` and double quotes `"` are the same for representing a string in JavaScript.  

    > **Note:** For boolean values, use `true` and `false`

    String + Number &rarr; String

    ```javascript
    let name = "John";
    let age = 25;
    age = age + name;
    console.log(age);
    ```
    > **Note:** The result is `25John` because JavaScript converts the number to a string and concatenates the two strings.

    We can also give some arguments to the `console.log()` function:

    ```javascript
    let name = "John";
    console.log("Hello", name); // or console.log("Hello " + name);

    // output: Hello John
    ```

    ### DOM Manipulation
    - `document` is the DOM object in JavaScript that represents the HTML document.
    - `document.getElementById()` is a function that returns the element with the specified ID.
    - `innerHTML` is a property that sets or returns the HTML content (inner HTML) of an element.  
    If this is used to set the HTML content, it will `overwrite` the existing content.
    In HTML, if we have:

    ```html
    <p id="demo"> This is a paragraph </p>
    ```
    then in JavaScript, we can do:

    ```javascript
    document.getElementById("demo").innerHTML = "Hello World";
    ```
    and in page, we will see `Hello World` instead of `This is a paragraph`.



    <a id="Arithmetic-expressions"></a>
    ## 3. Arithmetic expressions
    Arithmetic expressions is a combined of
    * Operand (values, variables, etc.)
    * Operators (+, -, *, /, %, etc.)

    ```javascript
    let x = 5;
    let y = 3;

    console.log(x + y); // 8
    ```
    <a id="Augmented-assignment-operator"></a>
    > **Augmented assignment operator**:   
    > `x += y` &rarr; `x = x + y`   
    > `x -= y` &rarr; `x = x - y`  
    > `x *= y` &rarr; `x = x * y`  
    > ...

    > **NOTE**  
    > x++ &rarr; x = x + 1  
    > x-- &rarr; x = x - 1


    <a id="Operator-precedence"></a>
    > **Operator precedence**:  
    > 1. Parentheses &rarr; `()`
    > 2. Exponentiation &rarr; `**`
    > 3. Multiplication and division &rarr; `* /`
    > 4. Addition and subtraction &rarr; `+ -`
    > 5. Left to right


    <a id="User-input"></a>
    ## 4. User input

    <a id="Window-prompt"></a>
    ### 1. Window prompt
    ```javascript
    let name = window.prompt("Enter your name: ");
    console.log(name);
    ```

    > **Note:** The return value of `window.prompt()` is a `string`.

    <a id="HTML-textbox"></a>
    ### 2. HTML textbox

    ```html
    <input type="text" id="myText"> <br>
    <button type="button" id="myButton">submit</button>
    ```

    ```javascript
    let username;

    document.getElementById("myButton").onclick = function(){

        username = document.getElementById("myText").value;
        console.log(username);
    }
    ```

    <a id="Type-conversion"></a>
    ## 5. Type conversion
    ```javascript
    let age = window.prompt("How old are you?"); // assume the user enters 25

    age += 1;

    console.log("Happy Birthday!! You are " + age + " years old"); // Happy Birthday!! You are 251 years old
    ```
    > **Note:** The result is `251` because the return value of `window.prompt()` is a `string`.

    Fix this by converting the `string` to a `number`:

    ```javascript
    let age = window.prompt("How old are you?");
    console.log(typeof age);

    age = Number(age);
    age += 1;

    console.log(typeof age);

    console.log("Happy Birthday!! You are " + age + " years old");
    ```

    Another example:

    ```javascript
    let x;
    let y;
    let z;

    x = Number("3.14");
    y = String(3.14);
    z = Boolean("Hello");

    console.log(x, typeof x);
    console.log(y, typeof y);
    console.log(z, typeof z);
    ```

    <a id="Const"></a>
    ## 6. Const    
    - `const` is a variable that cannot be reassigned.
    ```javascript
    const PI = 3.14;
    ```

    <a id="Math"></a>
    ## 7. Math
    `Math` is a built-in object that has properties and methods for mathematical constants and functions.

    ```javascript   
    let x = 4.6
    let y = 1.1
    let z = -8.3
    let maximum
    let minimum

    x = Math.round(x) // Found the nearest integer
    x = Math.floor(x) // Found the largest integer less than or equal to x
    x = Math.ceil(x) // Found the smallest integer greater than or equal to x
    x = Math.pow(x, 2)  // x^2
    x = Math.sqrt(x) // square root of x
    x = Math.abs(x) // absolute value of x
    maximum = Math.max(x, y ,z) // maximum = 4.6
    minimum = Math.min(x, y, z) // minimum = -8.3

    x = Math.PI // 3.141592653589793
    x = Math.E  // 2.718281828459045
    ```