# Git

## Source:
- [Faradars](https://faradars.org/fvgit9609)
- [YouTube](https://youtu.be/TEx_mRpIDkA)

### Initialization and Basic Commands:
- `git init`: Initialize a new Git repository
- `git add filename`: Stage changes in filename
- `git add -a` (or `git add --all`): Stage all changes
- `git commit -m 'message'`: Commit staged changes with a message
- `git status`: Show the working tree status
- `git log`: Show commit history
- `git diff`: Show changes between the working tree and the index
- `git diff HEAD`: Show changes between the working tree and the latest commit
- `git diff --staged`: Show changes between the index and the latest commit
- `git diff filename`: Show changes in filename
- `git restore --staged filename` (or `git reset filename`): Unstage changes in filename
- `git restore filename` (or `git checkout -- filename`): Discard changes in filename

### Branches and Merging:
- `git branch`: List branches
- `git branch nameOfNewBranch`: Create a new branch
- `git checkout branchname`: Switch to a branch
- `git checkout "title_tag"`: Switch to a commit (using its title tag)
- `git merge branchname`: Merge branchname into the current branch
- `git branch -d branchname`: Delete a branch
- `git show "id_commit"`: Show information about a commit (using its ID)
- `git show "title_tag"`: Show information about a commit (using its title tag)

### Cloning, Remote, and Push/Pull:
- `git clone "address"`: Clone a repository from an address
- `git remote`: List remote repositories
- `git remote add "name_remote" "address_remote"`: Add a remote repository with a name
- `git push "name_remote" "name_branch"`: Push changes to a remote branch
- `git push origin master`: Push changes to the origin master branch
- `git pull origin master`: Pull changes from the origin master branch
- `git push`: Push changes to the default remote branch (usually origin)
- `git pull`: Pull changes from the default remote branch (usually origin)

### Tags and Fetch:
- `git tag`: List tags
- `git tag -a "title_tag" -m "message"`: Create an annotated tag with a message
- `git tag -a "title_tag" "id_commit" -m "message"`: Create an annotated tag with a message and associated commit
- `git tag -l "expression(title_tag)"`: List tags with matching expressions
- `git push origin --tags`: Push all tags to the origin repository
- `git push origin "title_tag"`: Push a specific tag to the origin repository
- `git fetch --all --tags`: Fetch all tags from all remotes

### Git Log Visualization:
- `git log --oneline --graph`: Show commit history in a one-line format with a graph
- `git log --graph`: Show commit history with a graph

### Git Help and Blame:
- `git help "commands"`: Get help for specific Git commands
- `git blame "name_file"`: Show who changed which lines in a file
- `git blame "name_file" -L"number_line"`: Show blame for specific lines in a file
- `git blame "name_file" -L"number_line","number_line"`: Show blame for a range of lines in a file

### Git Bisect:
- `git bisect start`: Start a bisection process to find a faulty commit
- `git bisect bad`: Mark the current commit as bad
- `git bisect good "id_commit"`: Mark a specific commit as good in the bisection process
- `git bisect good`: Mark the current commit as good in the bisection process