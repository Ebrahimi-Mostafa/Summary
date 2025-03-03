# LaTeX

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Basic document](#basic-document)
4. [Common Mathematical Notation](#common-mathematical-notation)


## Introduction
LaTeX is a typesetting system commonly used for technical and scientific documentation.

Source: [YouTube Video](https://www.youtube.com/watch?v=ydOTMQC7np0)

## Installation
* MacTeX is a popular distribution of LaTeX for macOS.
```bash
brew install --cask mactex
```
* Install the _LaTeX Workshop_ extension in VS Code.

## Basic document
* A basic LaTeX document:
    ```latex
    \documentclass{article}
    \begin{document}
    Hello, world!
    \end{document}
    ```

* `LaTeX`:  
    It starts and ends with a backslash. It shows LaTeX logo.
    ```latex
    \LaTeX\
    ```
    output:  
    $\LaTeX$

    The second backslash is used to show a space after the logo.

* `New line`:  
    * Hard return:  
    add blank line between lines. It will be rendered as a new paragraph.  
    ```latex
    Hello, world!

    This is a new paragraph.
    ```

    * Soft return:  
    add \\\\ at the end of the line. It will be rendered as a new line.
    ```latex
    Hello, world!\\
    This is a new line.
    ```

* `Math mode`:  
    ```latex
    $x^2 + y^2 = z^2$
    ```
    output:  
    $x^2 + y^2 = z^2$

    * If you write the equation in a sentence, and you want to display it in a line(not part in a line, another part in next line), you can use `{$equation$}`.
        ```latex
        The equation {$x^2 + y^2 = z^2$} is the Pythagorean theorem.
        ```
    * Show the equation in a _separate_ line:
        ```latex
        The equation $$x^2 + y^2 = z^2$$ is the Pythagorean theorem.
        ```
        output:  
        The equation $$x^2 + y^2 = z^2$$ is the Pythagorean theorem.


## Common Mathematical Notation