# Terminal
Source: [YouTube](https://youtu.be/tw07ctwa7_8)

## Basic Navigation

### Creating & Removing Directories
- `mkdir "Path/folder_name"`: Create a directory named folder_name in the specified path.
- `rmdir "Path/folder_name"`: Remove an empty directory named folder_name in the specified path.

### Changing Directories
- `cd "Path"`: Change to the specified directory.
- `cd ..`: Go to the parent directory.
- `cd ~`: Go to the home directory of your user.
- `cd /`: Go to the root directory.
- `.`: Represents the current directory.
- `..`: Represents the parent directory.

## Listing & Clearing

### Listing Files & Directories
- `ls "Path"`: List files and directories in the specified path.
- `ls -l`: List files and directories in long format.
- `ls -lh`: List files and directories in long format with human-readable sizes.
- `ls -ltr`: List files and directories in long format, sorted by modification time (oldest first).
- `ls -ltrh`: List files and directories in long format, sorted by modification time with human-readable sizes.
- `ls -s`: List files and directories with their sizes.
- `ls -sh`: List files and directories with their sizes in human-readable format.
- `ls -a`: List all files and directories, including hidden ones.
- `ls -1`: List files and directories in a single column.


### Clearing the Terminal
- `clear`: Clear the terminal screen.

## Common Shortcuts & Commands

- `Ctrl + c`: Interrupt the currently running command.
- `Ctrl + w`: Delete the word before the cursor.
- `Ctrl + u`: Delete the whole line.
- `Ctrl + k`: Delete the line after the cursor.

- `Ctrl + r`: Search the command history.
  - `Ctrl + r`: Move to the next matching command.


## Viewing & Editing Files

### Creating & Viewing Files
- `touch "Path/file_name"`: Create a new file named file_name.
- `cat "Path/file_name"`: Display the contents of a file.
- `tac "Path/file_name"`: Display the contents of a file in reverse order.
- `less "Path/file_name"`: View the contents of a file using a pager.
- `file "Path/file_name"`: It use signatures and magic numbers to determine the file type.
- `head "Path/file_name"`: Display the first 10 lines of a file.
- `tail "Path/file_name"`: Display the last 10 lines of a file.
- `od "Path/file_name"`: Display the contents of a file in octal format. Some useful options:
  - `-c`: Display the contents of a file in ASCII format(Characters) per byte.
  - `-b`: Display the contents of a file in octal format per byte.
  - `-A`: Display offsets in different formats.
    - `-An`: Display no offsets.
    - `-Ax`: Display offsets in hexadecimal format.
    - `-Ad`: Display offsets in decimal format.
  - `-w`: Customize the output width.
    - `w4`: Display 4 byte per line.
- `wc "Path/file_name"`: Display the number of lines, words, and characters in a file.(wc stands for word count)
  - `-l`: Display the number of lines.
  - `-w`: Display the number of words.
  - `-c`: Display the number of characters.

### Searching within Files & Editing Files
- `Vim "Path/file_name"`: Open a file in Vim (text editor). To enable syntax highlighting, type "syntax on" within Vim.
- `grep word "Path/file_name"`: Search for a specific word in a file.
- `open "Path/file_name"`: Open a file in its default application.
  - `open -a "Application"`: open Application.


## Advanced Commands

### Running Commands with Root Access
- `sudo "command"`: Run a command with root access.
- `su -`: Switch to the root user.

### Accessing Manual Pages
- `man "command"`: Display the manual page for a command.

### Copying, Moving, & Removing Files & Directories
- `cp "Path/folder_name1" "Path/folder_name2"`: Copy a file or directory to a new location.
- `mv "Path/folder_name1" "Path/folder_name2"`: Move or rename a file or directory.
- `rm "Path/folder_name"`: Remove a file
- `rm -rf "Path/folder_name"`: Remove a directory and its contents.

## Miscellaneous

- `pwd`: Print the current working directory.
- `uname`: Display system information.
- `type "command"`: Show how a command will be interpreted.
- `which "command"`: Display the path of a command.
- `whereis "command"`: Display the locations of a command's binary, source, and manual page files.
- `whatis "command"`: Display a brief description of a command.

## History & Searching

- `Ctrl + r`: Search command history.
- `history`: View command history.

## Hashes

- `shasum "Path/file_name"`: Print or Check SHA Checksums
  - `-a`: Specify the algorithm.
    - `256`: SHA-256
    - `512`: SHA-512