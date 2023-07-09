# JavaScript
Source: https://www.youtube.com/watch?v=8dWL3wF_OMw

## 📋 Table of Contents
0. [Setup](#Setup)
1. [JavaScript tutorial for beginners](#JavaScript-tutorial-for-beginners)
2. [Variables](#Variables)
3. [Arithmetic expressions](#Arithmetic-expressions)


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
    <title>Document</title>
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

    > **Note:** For boolean values, use `true` and `false` (without quotes).

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
    console.log("Hello", name);

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