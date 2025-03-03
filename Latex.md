# LaTeX

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Basic Document](#basic-document)
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

## Basic Document
* A basic LaTeX document:
    ```latex
    \documentclass{article}
    \begin{document}
    Hello, world!
    \end{document}
    ```

* `LaTeX` Logo:
    ```latex
    \LaTeX\
    ```
    Output:  
    $\LaTeX$

    The second backslash is used to show a space after the logo.

* New Line:
    * Hard return:  
        Add a blank line between lines. It will be rendered as a new paragraph.
        ```latex
        Hello, world!

        This is a new paragraph.
        ```
    * Soft return:  
        Add `\\` at the end of the line. It will be rendered as a new line.
        ```latex
        Hello, world!\\
        This is a new line.
        ```

* Math Mode:
    ```latex
    $x^2 + y^2 = z^2$
    ```
    Output:  
    $x^2 + y^2 = z^2$

    * To ensure an equation remains on a single line within a sentence, use `{$equation$}`.
        ```latex
        The equation {$x^2 + y^2 = z^2$} is the Pythagorean theorem.
        ```
    * Display the equation on a _separate_ line:
        ```latex
        The equation $$x^2 + y^2 = z^2$$ is the Pythagorean theorem.
        ```
        Output:  
        The equation $$x^2 + y^2 = z^2$$ is the Pythagorean theorem.

## Common Mathematical Notation
