
# Markdown
[Source](https://commonmark.org/help/tutorial/)

## Contents :clipboard:
- [Intro](#intro)
- [Emphasis](#emphasis)
- [Paragraphs](#paragraphs)
- [Headings](#headings)
- [Blockquotes](#blockquotes)
- [Lists](#lists)
- [Links](#links)
- [Images](#images)
- [Code](#code)
- [Nested Lists](#nested-lists)



## Intro
Markdown is a lightweight markup language used to format and style text documents.


## Emphasis
`*` and `_` for italic text.  
`**` and `__` for bold text.

\*Mostafa\* --> *Mostafa*  
\_Mostafa\_ --> _Mostafa_  
\*\*Mostafa\*\* --> **Mostafa**  
\_\_Mostafa\_\_ --> __Mostafa__

## Paragraphs
`one` or `more blank lines` for separate paragraphs.  
`\` or `two spaces` for line break.

This is the first paragraph  
This is the second paragraph  
<!-- second paragraph is separated from the first one by a blank line -->

This is the first paragraph\
This is the second paragraph

## Headings
Starting a line with a hash `#` and a `space` makes a header.  
You can optionally add more `#` at the end to close the header. You don’t need to match the number of `#` used at the beginning.  
`#` for heading 1  
`##` for heading 2  
`###` for heading 3  
...  


## Heading 2 ###
### Heading 3
...

## Blockquotes
To create a blockquote, start a line with greater than `>` followed by an optional space.  
`>` for blockquotes.  
`>>` for nested blockquotes.  
`>>>` for nested blockquotes.  

> This is a blockquote
>
>> This is a nested blockquote
>>
>>> This is a nested blockquote

## Lists
`*` or `-` or `+` --> unordered list.  
`.` or `)` --> ordered list.

- Item 1  
- Item 2
    - Item 2a
    - Item 2b
- Item 3

7. Item 7
8. Item 8
    * Item 8a
    * Item 8b


## Links

In Markdown, URLs might not automatically become links until they are enclosed within angle brackets `< >`. For example:

- `google.com` becomes <http://google.com>

Structured links provide more control:

1. Using the format `[link text](url "title")`:
   - The title is optional.
   - Example: [Google](https://google.com "Google")

2. Using reference-style links `[link text][id]`:
   - Define the link with `[id]: url "title"`.
   - The title is optional.
   - Example: [Google][google]

These approaches allow for organized and customizable linking.


[google]: https://google.com "Google"  


## Images
Images are almost identical to links, but they have an exclamation point `!` in front of them:

1. Using the format `![alt text](url "title")`:
   - The title is optional.
   - Example:  
   ![Google](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png "Google")
2. Using reference-style links `![alt text][id]`:
   - Define the link with `[id]: url "title"`.
   - The title is optional.
   - Example:  
   ![Github][github]

[github]: https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png "Github"

## Code
1. Inline code:  
   - Surround the code with a backtick character `.
   - Example: `print("Hello World")`
2. Code blocks:
    - Indent each line of the block by at least 4 spaces or 1 tab.
    - Example:  

            print("Hello World")  
            print("Hello World")  
            print("Hello World")   

    - Alternatively, you can use three backticks ``` to enclose the code block:
    - Example:  
    ``` python
    print("Hello World")
    print("Hello World")
    print("Hello World")
    ```

## Nested Lists