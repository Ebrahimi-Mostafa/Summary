# HTML & CSS
Source: https://www.youtube.com/watch?v=HGTJBPNC-Gw&list=PLZPZq0r_RZOPP5Yjt6IqgytMRY5uLt4y3&index=1

## 📋 Table of Contents
1. [Introduction to HTML](#introduction-to-html)
2. [Index.html](#index.html)
3. [HTML Basics](#html-basics)
4. [Hyperlinks](#hyperlinks)
5. [Images](#images)


## Introduction to HTML
- HTML stands for `Hyper Text Markup Language`
- CSS stands for `Cascading Style Sheets`

## Index.html
- HTML file is saved with `.html` extension
- The home page of a website is called `index.html`

## HTML Basics
```html
<!DOCTYPE html>
<html>
    <head>
        <title> Hello Friends </title>
    </head>
    <body>
    </body>
</html>
```

- `<!DOCTYPE html>`: Tells the browser that this is an HTML5 document
- `<html>`: Root element of the HTML page
- `<head>`: Contains meta information about the HTML page
- `<title>`: Title of the HTML page
- `<body>`: Contains the visible page content

### Some HTML Tags in Body
- Heading:
    - `<h1></h1>`: Heading 1
    - `<h2></h2>`: Heading 2
    - `<h3></h3>`: Heading 3
    - `<h4></h4>`: Heading 4
    - `<h5></h5>`: Heading 5
    - `<h6></h6>`: Heading 6
- Paragraph:
    - `<p></p>`: Not sensitive to white spaces
    - `<pre></pre>`: Sensitive to white spaces
- `<br>`: Line Break
- `<hr>`: Horizontal Rule
- `<!-- -->`: Comment

## Hyperlinks
- `<a></a>`: Anchor tag
- Some attributes of Anchor tag:
    - `href`: Hyperlink reference   
    ```html
    <a href="https://www.google.com">Google</a>
    <a href="./about.html">About</a>
    ```
    - `target`: Where to open the link(blank means new tab or window)
    ```html
    <a href="https://www.google.com" target="_blank">Google</a>
    ```
    - `title`: Title of the link(appears when hovered over the link)
    ```html
    <a href="https://www.google.com" title="Go to Google">Google</a>
    ```
    - Email link: Opens the default email client with the email address
    ```html
    <a href="mailto:test@fake.com">Email</a>
    ```

## Images