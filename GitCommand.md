
# git init
    create instance

# git status
    # output the status of repository

# git add
   ```
    # add files
    ! add . - add all files in current dir
    ! add -all add all files
   ```
 
# `git comit -m`
    # attached comment to files

# git comit
    # attached comment to all files with long comit
    !! git config --global core.editor "code --wait"
    ! --amend add comment to last changes if you faggot 

# git log
    # output the comment history
    !! q is key to close loge file. I thing it uses the Vim editor
    ! --oneline - output all logs commin in one line and it's like a history

# git ignore
    !! touch .gitignore - add rules about files wich  git must ignore

# git branch
    #show all branch in repo
    - git branch [name] add branch in git project
    !! branch -d [name]; branch -D [name]; deleted branch
    - git branch -r
    # list remote branches origin/[branch1]...origin/[branch_N]

# git switch 
    #switch branch like timelaps or time point 
    - git switch -c [name branch]; -c add new branch and switch
    
# git checkout
    - git checkout [name] 
    - git checkout origin/[branchName]
    # switch to remote origin/[branchName]

# git merge
    - merge two branch, but be careful with HEAD

# git diff
    #see difference only not add in repo!
    # @@ -1,4         +1,5 @@ 1; 
    #                  | |
    #   Line number  <=| |=>  How many  
    - git diff HEAD [filename]
    # list ALL (staged & unstaged) changes in the working tree since your last commit 
    - git diff --staged [filename]
    # list staged and curent changes in the working tree
    - git diff branch1..branch2
    # list difference between two branchs
    - git diff commit1..commit2
    # git diff 4e5g6t..3h5k3h0k. list difference between two add comit in repo 
    - git diff branch1..branch2 [filename]
    # list difference file between two branchs
    ! git diff HEAD HEAD~1 - list difference between last comment

# git stash
    # save changes befor switch in other branch
    - git stash pop
    # return save changes
    - git stash apply
    # apply stashed changes to multiply branches (very useful)
    ! git stash has been LIFO principle
    - git stash list [stash@{N}]
    # list of LIFO stashed changes
    - git stash drop [stash@{N}]
    # deleted stash 

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