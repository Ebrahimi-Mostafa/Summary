# MATLAB

# Table of Contents
  - [SESSION 1](#session-1)
    - [Basic Commands](#basic-commands)
    - [Matrix and Transpose](#matrix-and-transpose)
    - [Help and Documentation](#help-and-documentation)
    - [File I/O](#file-io)
    - [Commenting](#commenting)
    - [Random Numbers](#random-numbers)
    - [Generating Sequences](#generating-sequences)
    - [Script Execution](#script-execution)
    - [String Formatting](#string-formatting)
    - [Figure and Plot](#figure-and-plot)
    - [Comparison](#comparison)
    - [Function](#function)
    - [Arrays](#arrays)
    - [Rounding](#rounding)
    - [Looping](#looping)
  - [SESSION 2](#session-2)
    - [Matrix and Indexing](#matrix-and-indexing)
    - [Strings and Concatenation](#strings-and-concatenation)
    - [Cells and Structs](#cells-and-structs)
    - [File and Image Operations](#file-and-image-operations)
    - [User Interface](#user-interface)
    - [Image Processing](#image-processing)
    - [Image Processing - Finding Coordinates](#image-processing-finding-coordinates)
    - [Array Operations](#array-operations)
    - [File Writing](#file-writing)

## SESSION 1
Source: [YouTube](https://www.youtube.com/watch?v=En4wcQnY2Og&list=WL&index=7&t=651s)

### Basic Commands:
- `clc`: Clear the console
- `;`: Don't print

- `clear`: Clear all variables
- `clear x y`: Clear variables x and y
- `clearvars`: Clear all variables
- `clearvars x y`: Clear variables x and y
- `clearvars -except x y`: Clear all variables except x and y

### Matrix and Transpose:
- `[x, y; z, w]`: Create a matrix with rows x y and z w
- `size(Matrix)`: Get the size of the matrix (rows, columns)
- `length(Matrix)`: Get the maximum size of the matrix (rows or columns)
- `x'`: Transpose the matrix x

### Help and Documentation:
- `command + f1`: Access help

### File I/O:
- `save('address/filename')`: Save all variables
- `save('address/filename', 'x', 'y')`: Save variables x and y
- `load('address/filename')`: Load variables from address/filename
- `load('address/filename', 'x', 'y')`: Load specific variables from address/filename

### Commenting:
- `%`: Single-line comment
- `%{ comment %}`: Multi-line comment
- `%%`: New section

### Random Numbers:
- `rand(x,y)`: Random matrix x by y
- `randn(x,y)`: Random matrix x by y with normal distribution

### Generating Sequences:
- `x:y`: Generate a sequence from x to y with step 1
- `x:k:y`: Generate a sequence from x to y with step k

### Script Execution:
- `filename`: Run filename.m

### String Formatting:
- `sprintf("sum = %d", sum)`: Print "sum = sum"

### Figure and Plot:
- `figure`: Open a new figure
- `figure('Name', 'abc')`: Open a new figure with title 'abc'
- `hold on`: Hold on the current plot on the figure
- `close all`: Close all figures
- `subplot(2,3,1)`: Create a 2x3 grid and select the 1st plot
- `plot(x,y)`: Plot x and y on the figure
- `stem(x,y)`: Plot x and y with stem on the figure
- Arguments for plot or stem:
  - `'Color', 'r'`: Show red wave
  - `'LineWidth', 2`: Show wave with width 2
- `xlim([0, 10])`: Set x-axis limit from 0 to 10
- `ylim([0, 10])`: Set y-axis limit from 0 to 10

### Comparison:
- `~=`: Not equal

### Function:
- `function [x, y] = function_name(a, b)`: Function with 2 inputs and 2 outputs

### Arrays:
- `zeros(x,y)`: Create a matrix of size x by y with all zeros
- `ones(x,y)`: Create a matrix of size x by y with all ones

### Rounding:
- `round(x)`: Round x
- `round(x, n)`: Round x with n digits after the decimal point

### Looping:
- `Loop from start to end with step`:
```matlab
for i = start:step:end
  % do something
end
```

## SESSION 2

### Matrix and Indexing:
- `matrix = [1 2 3; 4 5 6; 7 8 9]`: Create a 3x3 matrix
- `matrix(1, 2)`: Access the 2nd element of the 1st row

### Strings and Concatenation:
- `address = 'address'`: Store the address in a variable
- `name = 'filename'`: Set the name to filename
- `path = [address, '/', name]`: Concatenate strings to form a path

### Cells and Structs:
- `cell = {1, 2, 3; 4, 5, 6; 7, 8, 9}`: Create a 3x3 cell array
- `cell{1, 2}`: Access the 2nd element of the 1st row in the cell
- `struct = struct('name', 'ali', 'age', 20)`: Create a struct with fields (name and age) and values (ali and 20)
- `st.name = 'ali'`: Add a name field to the struct st with the value ali
- `st.age = 20`: Add an age field to the struct st with the value 20

### File and Image Operations:
- `dir('address')`: List files in the address

- `cell2mat(cell)`: Convert a cell to a matrix

- `imread('address')`: Read an image from the address
- `imshow(image)`: Show the image

- `imresize(pic, [x, y])`: Resize the picture to x by y scale
- `rgb2gray(pic)`: Convert the picture to grayscale
- `im2bw(pic)`: Convert the picture to black and white

### User Interface:
- `uigetfile`: Open a file dialog
- `uigetfile({'*.jpg;*.png})`: Open a file dialog with filter (jpg and png)
- `uigetfile({'*.jpg;*.png}, 'Select an image')`: Open a file dialog with filter and title

### Image Processing:
- `graythresh(pic)`: Find the threshold of pic (a number between 0 and 1) for making pic binary
- `im2bw(picture, threshold)`: Convert picture to binary with the threshold
- `bwareaopen(BW, P)`: Remove connected components (objects) with fewer than P pixels from the binary image BW
- `regionprops(BW, "BoundingBox")`: Find the bounding box of objects in BW
- `rectangle('Position', [x, y, w, h], "EdgeColor", "r")`: Draw a rectangle with x, y, w, h and red color

### Image Processing - Finding Coordinates:
- `[r, c] = find(BW == number)`: Find the row and column of number in BW
- `corr2(pic1, pic2)`: Calculate the correlation of pic1 and pic2 (2D)

### Array Operations:
- `[value, index] = max(array)`: Find the maximum value and index of array
- `[value, index] = min(array)`: Find the minimum value and index of array
- `matrix = [matrix 3]`: Append 3 to the matrix

### File Writing:
- `file = fopen('address', 'wt')`: Open a file in address with write and text mode
- `fprintf(file, "text")`: Write text to the file
