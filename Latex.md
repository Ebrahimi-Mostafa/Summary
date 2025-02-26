# LaTeX

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Basic document](#basic-document)

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
```latex
\documentclass{article}
\begin{document}
Hello, world!
\end{document}
```


## Fundamental LaTeX Syntax
* LaTeX:  
It starts and ends with a backslash. It shows LaTeX logo.
```latex
\LaTeX\
```
The second backslash is used to show a space after the logo.

* New line:  
    * Hard return: add blank line between lines. It will be rendered as a new paragraph.  
    ```latex
    Hello, world!

    This is a new paragraph.
    ```

    * Soft return: add \\\\ at the end of the line. It will be rendered as a new line.
    ```latex
    Hello, world!\\
    This is a new line.
    ```
