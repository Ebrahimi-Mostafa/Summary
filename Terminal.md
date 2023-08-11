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

### Searching within Files & Editing Files
- `Vim "Path/file_name"`: Open a file in Vim (text editor). To enable syntax highlighting, type "syntax on" within Vim.
- `grep word "Path/file_name"`: Search for a specific word in a file.

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
