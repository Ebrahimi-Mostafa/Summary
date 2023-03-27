<!-- source: https://commonmark.org/help/tutorial/ -->

<!-- other: 
https://commonmark.org/help/
https://www.markdowntutorial.com
https://itsfoss.com/markdown-guide/ -->

# Contents
- [Intro](#intro)
- [Emphasis](#emphasis)
- [Paragraphs](#paragraphs)
- [Headings](#headings)
- [Blockquotes](#blockquotes)
- [Lists](#lists)
- [Links](#links)


# Intro
Markdown is a lightweight markup language used to format and style text documents.


# Emphasis
`*` and `_` for italic text.  
`**` and `__` for bold text.

\*Mostafa\* --> *Mostafa*  
\_Mostafa\_ --> _Mostafa_  
\*\*Mostafa\*\* --> **Mostafa**  
\_\_Mostafa\_\_ --> __Mostafa__

# Paragraphs
`one` or `more blank lines` for separate paragraphs.  
`\` or `two spaces` for line break.

This is the first paragraph  
This is the second paragraph  
<!-- second paragraph is separated from the first one by a blank line -->

This is the first paragraph\
This is the second paragraph

# Headings
Starting a line with a hash `#` and a `space` makes a header.  
You can optionally add more `#` at the end to close the header. You don’t need to match the number of `#` used at the beginning.  
`#` for heading 1  
`##` for heading 2  
`###` for heading 3  
...  


## Heading 2 ###
### Heading 3
...

# Blockquotes
To create a blockquote, start a line with greater than `>` followed by an optional space.  
`>` for blockquotes.  
`>>` for nested blockquotes.  
`>>>` for nested blockquotes.  

> This is a blockquote
>
>> This is a nested blockquote
>>
>>> This is a nested blockquote

# Lists
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


# Links