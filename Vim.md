# Tutorial Vim

## Table of contents :label:
- [Jadi tutorial Vim](#jadi-tutorial-vim)
    - [Part 1](#part-1)
    - [COMMAND mode](#command-mode)
    - [NORMAL mode](#normal-mode)
    - [Part 2](#part-2)
        - [NORMAL mode](#normal-mode-1)
        - [COMMAND mode](#command-mode-1)
        - [VISUAL mode](#visual-mode)
    - [Part 3](#part-3)
- [Vimtutor](#vimtutor)
  - [Lesson 1](#lesson-1)
  - [Lesson 2](#lesson-2)



### Jadi tutorial Vim
#### Part 1
Source: [YouTube](https://www.youtube.com/watch?v=BnfJJtcVFPo&list=RDLVwwtoRHn9bIA&index=3)  

- `esc` -> change mode from INSERT to COMMAND mode

##### COMMAND mode:
- `:wq` -> write and quit
- `:q!` -> quit without saving

##### NORMAL mode:
- `i` -> insert mode

- `x` -> delete one character and select one
- `X` -> delete one character and the previous one

- `r` -> goto replace mode for one character (listening to a new character for replace)

- `o` -> insert a new line below the current line and goto insert mode
- `O` -> insert a new line above the current line and goto insert mode

- `a` -> insert a new position after the current character and goto insert mode

- `u` -> undo

- `number + COMMAND` -> repeat COMMAND for number times

- `d` -> delete (cut)
- `dw` -> delete (cut) word
- `dd` -> delete (cut) line
- `number + dw` -> delete (cut) number words
- `number + dd` -> delete (cut) number lines
- `d + $` -> delete (cut) to the end of the line
- `d + 0` -> delete (cut) to the beginning of the line
- `d + ^` -> delete (cut) to the beginning of the line
- `d + e` -> delete (cut) to the end of the word

- `^j` -> join two lines
- `number + ^j` -> join number lines

- `G` -> goto the last line
- `number + G` -> goto the number line
- `gg` -> goto the first line
- `number + gg` -> goto the number line
- `$` -> goto the end of the current line
- `^` -> goto the first of the current line
- `0` -> goto the first of the current line

- `yy` -> copy line
- `number + yy` -> copy number lines
- `yw` -> copy word
- `number + yw` -> copy number words
- `p` -> paste after the current line
- `P` -> paste before the current line
- `y + $` -> copy to the end of the line
- `y + 0` -> copy to the beginning of the line
- `y + ^` -> copy to the beginning of the line

- `/` -> search
- `/X` -> search for X
- `n` -> next search
- `N` -> previous search

- `.` -> repeat the last command

#### Part 2
Source: [YouTube](https://www.youtube.com/watch?v=7WB7DGic9nM)

##### NORMAL mode:
- `%(on bracket)` -> goto the matching bracket
- `A` (a + shift) -> go to insert mode and jump to the end of the line
- `shift + .` -> change indent
- `shift + ,` -> change indent

- `control + w` -> switch between windows

- `!!` -> wait for command and run it in the terminal and print the result in Vim

##### COMMAND mode:
- `syntax on` -> enable syntax highlight
- `set number` -> enable line number
- `set nonumber` -> disable line number
- `set autoindent`
- `colorscheme` -> change theme

- `Explore` -> open file explorer
- `Vexplore` -> open file explorer in vertical mode
- `Sexplore` -> open file explorer in horizontal mode

- `split` -> split window
- `vsplit` -> split window in vertical mode

- `!COMMAND` -> run COMMAND in the terminal

- `v` -> visual mode (for select)

##### VISUAL mode:
- Select some lines then type `:sort` -> sort those lines

- Select some lines then type `:normal COMMANDS` -> in normal mode, do COMMANDS in these lines

- In HTML:
  - `i`, `t` -> select inner tag
  - `a`, `t` -> select all tag

#### Part 3
Source: [YouTube](https://www.youtube.com/watch?v=wwtoRHn9bIA&t=3s)

- `m + a` -> mark a position with a
- `' + a` -> go to the position marked with a


### Vimtutor
#### Lesson 1
             ^
             k              Hint:  The h key is at the left and moves left.
       < h       l >               The l key is at the right and moves right.
             j                     The j key looks like a down arrow.
             v                     The k key looks like an up arrow.


- 'esc' -> go to normal mode
- 'normal mode' + ':q!' -> quit without saving
- 'normal mode' + ':w' -> write (save) the file, but don't exit
- 'normal mode' + ':wq' -> write (save) and quit
- 'normal mode' + 'i' -> insert before the cursor
- 'normal mode' + 'A' -> insert (append) after the end of the line
- 'normal mode' + 'x' -> delete the character under the cursor


#### Lesson 2