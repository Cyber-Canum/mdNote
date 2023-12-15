
## Git Init

The `git init` command is utilized to initialize a new Git repository within a directory. When executed within a folder, it sets up all the necessary data structures and files, allowing Git to start tracking changes within that directory. This command creates a hidden subfolder named `.git`, which contains the versioning information and configuration files essential for Git operations within the repository.

### Syntax:
```bash
git init
```

## Git Status

The `git status` command is used to obtain information regarding the current state of the Git repository. When executed, it displays details about tracked, untracked, modified, and staged files. It provides valuable insights into which files have been altered, which are staged for commit, and which files are yet to be tracked by Git.

### Syntax:
```bash
git status
```

## Git Add

The `git add` command is employed to include changes made to files in the working directory to the staging area, preparing them for the subsequent commit. It allows users to selectively stage specific changes or entire files before committing them to the repository.

### Syntax:
```bash
git add <file_name>
``` 
```bash
add .
```
```bash
add -all
```
 
## Git Commit

The `git commit -m "<commit_message>"` command is employed to save the staged changes to the Git repository. It creates a snapshot of the changes that have been staged using `git add`, along with a descriptive commit message that outlines the modifications made.
- git config --global core.editor "code --wait"
- --amend add comment to last changes if you faggot 

### Syntax:
```bash
git commit -m "<commit_message>"
```

## Git Log --oneline

The `git log --oneline` command is utilized to display a condensed version of the commit history in a Git repository. When executed, it provides a concise listing of commits, showing abbreviated commit hashes along with the commit messages in a single line format.
- --oneline - output all logs commin in one line and it's like a history
- q is key to close loge file. I thing it uses the Vim editor

### Syntax:
```bash
git log --oneline
```

## Git Ignore

The `.gitignore` file tells Git what files or directories to ignore, ensuring they aren't tracked or committed. It helps exclude unnecessary or sensitive files like log files, compiled binaries, or user-specific settings. Simply list filenames, patterns, or directories in this file to keep your repository clean and focused on essential code and assets.
- touch .gitignore - add rules about files wich  git must ignore


## Git Branch

The `git branch` command is used in Git to manage branches within a repository. It displays, creates, deletes, renames, or lists branches in the repository. Additionally, it allows users to switch between branches or set a specific branch as the current working branch.

*Usage:*
- git branch <branch_name>: Creates a new branch with the specified name.
- git branch -d <branch_name>: Deletes the specified branch (if merged).
- git branch -m <old_branch_name> <new_branch_name>: Renames an existing branch.
- git branch -a: Lists all local and remote branches in the repository.
- git branch -r . list remote branches origin/[branch1]...origin/[branch_N]

### Syntax:
```bash
git branch <branch_name>
```
```bash
git branch -d <branch_name>
```
```bash
git branch -m <old_branch_name> <new_branch_name>
```
```bash
git branch -a
```
```bash
git branch -r
```

## Git Switch

The `git switch` command in Git is used to switch between branches or restore working tree files. Introduced in Git version 2.23, `git switch` primarily focuses on branch switching compared to the traditional `git checkout` command.

*Usage:*
- git switch <branch_name>: Moves the HEAD pointer to the specified branch.
- git switch -c <new_branch_name>: Creates a new branch from the current HEAD position and switches to it.

### Syntax:
```bash
git switch <branch_name>
```
```bash
git switch -c <new_branch_name>
```
## Git Checkout

The `git checkout` command in Git is a versatile tool used to switch branches, restore files from different commits or branches, and even create new branches. It's a powerful command that allows users to navigate through the repository's history and manage branches effectively.
*Usage:*
- git checkout <branch_name>: Moves the HEAD pointer to the specified branch, making it the active branch.
- git checkout -b <new_branch_name>: Creates a new branch from the current HEAD position and switches to it.
- git checkout <commit_hash> -- <file_name>: Restores the specified file from a specific commit, replacing the current version  in the working directory.

### Syntax:
```bash
git checkout <branch_name>
```
```bash
git checkout -b <new_branch_name>
```
```bash
git checkout <commit_hash> -- <file_name>
```
## Git Merge

The `git merge` command in Git is utilized to combine changes from one branch into another. It integrates the changes introduced in a specified branch into the current branch, thereby incorporating the commits from the source branch.
- merge two branch, but be careful with HEAD
### Syntax:
```bash
git merge <branch_name>
```
## Git Diff

The `git diff` command in Git is used to display the differences or changes between various states of a Git repository. It shows the variations between commits, the working directory, and the staging area, allowing users to inspect modifications made to files.
*Usage:*
- git diff: Shows changes between the working directory and the staging area.
- git diff <commit_A> <commit_B>: Displays differences between two commits.
- git diff <file_name>: Reveals changes made to a specific file.
- git diff HEAD [filename] list ALL (staged & unstaged) changes in the working tree since your last commit 
- git diff --staged [filename] list staged and curent changes in the working tree
  
### Syntax:
```bash
git diff
```
```bash
git diff <commit_A> <commit_B>
```
```bash
git diff <file_name>
```
```bash
git diff HEAD [filename] 
```
```bash
git diff --staged 
```
```bash
git diff HEAD HEAD~1
```

    #see difference only not add in repo!
    # @@ -1,4         +1,5 @@ 1; 
    #                  | |
    #   Line number  <=| |=>  How many  


## Git Stash

The `git stash` command in Git allows users to temporarily store changes in a 'stash,' enabling them to switch branches or perform other operations without committing the changes.
Usage:
- git stash: Stores the modifications in a stash, reverting the working directory to the last commit state.
- git stash apply: Applies the most recent stash to the working directory without removing it from the stash list.
- git stash list: Lists all stashes, displaying their IDs and descriptions.
- git stash drop: Removes the most recent stash from the stash list.

### Syntax:
```bash
git stash
```
```bash
git stash apply
```
```bash
git stash list
```
```bash
git stash drop
```

# git checkout [ID-commit]
    # HEAD points at that commit, not branch pointer
    ! git checkout HEAD~[N]
    # HEAD points at commits 1,2...N before
    - git checkout HEAD [filename]
    # Restore [filename] in HEAD 
    - git checkout -- [filename]
    # Restore --[filename]

# git restore --source HEAD~[N] [filename] 
    # restore the contents = git checkout HEAD [filename] or git checkout -- [filename]

# git reset [commit-hash]
    # deleted commit in repo, but not changed files
    - git reset --hard [comit-hash]
    # deleted commit in repo with files
    
# git revert [comit-hash]
    - deleted [comit-hash] changes, but left the comment

# git remote
    - git remote -v
    # list with information where was clone the repo

# git remote add [name] [url]
    # connect your repo with GitHub

# git push oringin [branch-HUB]:[branch-Git]
    # push [branch-HUB]<-[branch-Git]
    - git push -u
    # connect two branches in one link
    !! git pull --rebase origin master (error: failed to push some refs to )

# git fetch [remote] (origin) [branche] (main)
    # download changes from a remote repository   
    !! BUT did't integrated into our working files 

# git pull [remonte] [branch] = git fetch + git merge
    ! impotant WHERE we run this command 

# git rebase [branch]
    It same thing like merge, but without the extra comments 
    - git switch [branch]
    - git rebase master
    *!! never rebase in MASTER/Main branch*

# git rebase -i [Head ~4] 
    - interactive mode, which allows us to edit commits
  
# git tag [name_tag] [commit_HASH]
    - tag is link to comment
    - -l "*pattern*" - filter
    -  -a special annoteted tag
    -  -f force tag
    -  -d deleted tag   
  
# git show [tag]
# git push [tag]
    - push tag in remote server
    - --tags - push all tags
  
# git config --local 

# echo "Hello World" | git hash-object --stdin -w
    - return hash ssh1
    - parametr -w is write to folder .git\objects\ce
# git cat-file -p [hash]
    - revers method for echo "Hello World" | git hash-object --stdin -w

# git reflog show
    - show track, history og log
    - use in combo command got checkout HEAD~2 or [hash-commit]

# usefull commande with time point
    - git diff HEAD HEAD@{yesterday}
    - git diff master master@{yesterday}
    - git reflog show HEAD@{2.days.ago}
    - git reflog show HEAD@{one.minute.ago}
    - git checkout master@{1.week.ago}
  
  # git rebase -i HEAD~4
  
  # cat ~/.gitconfig ---- code ~/.gitconfig

