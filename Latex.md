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

* __`LaTeX` Logo__
    ```latex
    \LaTeX\
    ```
    Output:  
    $\LaTeX$

    The second backslash is used to show a space after the logo.

* __New Line__
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

* __Math Mode__
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

        * __Page Numbering__
            * To remove page numbering &rarr; `\pagestyle{empty}`.
                ```latex
                \documentclass[]{article}
                \pagestyle{empty}
                ...
                ```
                
## Common Mathematical Notation

> __Note:__ Mathematical modes:
> * __Inline Math Mode__: Used to write formulas that are part of a paragraph.(e.g. $x^2 + y^2 = z^2$)
> * __Display Math Mode__: Used to write expressions that are not part of a paragraph, and are therefore put on separate lines. (e.g. $$x^2 + y^2 = z^2$$)


* __Superscript & Subscript__
    * by default, _only_ the next character is considered. 
    * For multiple characters, enclose them in curly brackets.
    ```latex
    $$2x^34$$
    $$2x^{34}$$

    $$x_12$$
    $$x_{12}$$
    ```

    Output:
    $$2x^34$$  
    $$2x^{34}$$

    $$x_12$$
    $$x_{12}$$

* __Sequence__
    ```latex  
    $$a_1, a_2, ..., a_n$$
    $$a_1, a_2, \ldots, a_n$$
    $$a_1, a_2, \cdots, a_n$$
    ```
    Output:
    $$a_1, a_2, ..., a_n$$
    $$a_1, a_2, \ldots, a_n$$
    $$a_1, a_2, \cdots, a_n$$

* __Greek Letters__
    ```latex
    $$\alpha, \beta, \gamma, \delta, \pi, \sigma$$
    $$\Alpha, \Beta, \Gamma, \Delta, \Pi, \Sigma$$
    ```
    Output:
    $$\alpha, \beta, \gamma, \delta, \pi, \sigma$$
    $$\Alpha, \Beta, \Gamma, \Delta, \Pi, \Sigma$$

* __Trig Functions__
    ```latex
    $$\sin x, \cos x, \tan x, \arcsin x$$
    ```
    Output:
    $$\sin x, \cos x, \tan x, \arcsin x$$

* __Log Functions__
    ```latex
    $$\log x, \ln x, \log_2 x$$
    ```
    Output:
    $$\log x, \ln x, \log_2 x$$

* __Root__
    ```latex
    $$\sqrt{x}$$
    $$\sqrt[3]{x}$$
    ```
    Output:
    $$\sqrt{x}$$
    $$\sqrt[3]{x}$$

* __Fractions__
    ```latex
    $$\frac{3}{5}$$ % Display mode
    About $\frac{3}{5}$ of glass is full. % Inline mode

    About $\displaystyle\frac{3}{5}$ of glass is full. % Add Display mode in Inline mode(Increase size)
    ```
    Output:
    $$\frac{3}{5}$$
    About $\frac{3}{5}$ of glass is full.

    About $\displaystyle\frac{3}{5}$ of glass is full.

    > __Note:__
    You can [6pt] to increase the space between two lines. (pt = point)
    ```latex
    About $\frac{3}{5}$ of glass is full. [6pt]
    About $\displaystyle\frac{3}{5}$ of glass is full.
    ```
