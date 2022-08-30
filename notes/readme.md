# Notes about education

## Linux

<details><summary>Notes</summary>

#### Command List for Linux


Windows `cmd` or PowerShell doesn't support Linux commands but we can use CLI when Git is installed. 
Just RC mouse and in explorer and choose `Git Bash here`.

|Command		|Description |
|:----------|:-----------|
|`cat`		|concatenate (combine) two or more files
|`cd`		|change to another directory
|`chmod` 	|change mode (security permissions) of file or directory
|`ugo+-rwx`	|user (owner), group, other (world), add, remove, read, write, execute
|`cp`		|copy file
|`cp -r`	|copy directory tree
|`df`		|show disk free information
|`find`		|find files in a directory tree
|`finger`	|display user information
|`grep`		|list text lines containing particular characters
|`groups`	|show your security group memberships
|`kill`		|kill process
|`kill -9`	|kill process immediately
|`lpr`		|send to printer
|`lpr -P`	|send to another printer
|`lpq`		|show status of print queue
|`lpq -P`	|show print jobs in a different print queue
|`lprm`		|remove print job from printer
|`lprm -P`	|remove from a different print queue
|`ls`		|list contents of current directory
|`ls -l`	|long (detailed) listing
|`man`		|display portion of online Unix manual
|`man -k`	|display command descriptions relating to subject keyword
|`mkdir`	|make new directory
|`more`		|display contents of file
|`mv`		|move or rename file or directory
|`ps aux`	|list status of all processes (running programs)
|`pwd`		|print working (current) directory
|`rm`		|remove file
|`rm -r`	|remove directory tree
|`rmdir`	|remove an empty directory
|`..`		|parent directory
|`.`		|current directory
|`*`		|wildcard representing any combination of characters
|`?`		|wildcard representing exactly one character
|`~`		|your home directory
|`~userid`	|userid's home directory
|`>` 		|send output to file
|`>>`		|append (add) output to file
|`\|`		|pipe output from one command as input to another

</details>

## Git and GitHub

<details><summary>Notes</summary>


Before git there were commands in Linux to use for updating the code.
`diff` and `diff -u` to make file with changes between files
`patch` to grab changes in diff file to adjusted one.
Example:
```
diff -u file1.py file2.py > file.diff

patch file1.py < file.diff
```

Actual website of [**Git**](git-scm.com)

How to set e-mail address - [**Setting your email in Git**](https://help.github.com/articles/setting-your-email-in-git/)

_.gitignore_ file is used to exlude certain types of files we don't want to commit<br>
Example of added types in _.gitignore_:
```
*.com
*.class
*.dll
*._*
*.zip
```

*HEAD* represent the current checked-out snapshot of the commit.<br>
Can be imaged as a bookmark or a pointer to certain commit.

`git log -p` represents the same as `diff -u`

`git log -2` represpent last 2 commits, can be any number

`git show [id]` show log info for a certain commit

`git checkout [filename]` reverts file not staged yet to the latest commit

`git reset HEAD [file]` remove files from staged area

`git commit --ammend` changing previous commit. ***Use only for local commits***.

`git revert HEAD` adds a new commit which rollsback the previous one

`git revert [hash]` adds a new commit which rollsback the commit wih ID stated

_*Branch*_ - a pointer to a particular commit. Rather can be thougt as a separate place to do the work.

`git branch` shows list of branches

`git branch [name]` creates a new branch

`git checkout [branch]` switch to different branch

`git checkout -b [branch name]` create new branch and switch there immediately

`git branch -d [name]` delete branch

`git branch -D [name] delete branch even if it has uncommited changes

`git merge [name]` adds changes from branch into currently checked out.

`git log --graph --oneline` visual way of presenting the merging history

`git merge --abort` If there are merge conflicts (meaning files are incompatible), --abort can be used to abort the merge action.

`git rebase [target branch]` copy and moves to another branch not merging, leaving previous branch as is

`git checkout HEAD^` checkout to commit 1 step above HEAD (^2 - 2 steps)

`git branch -f [name] [hash]` move branch to certain commit

`git clone [url]`copy repo to local from gitHub

`git push` upload repo to remote

`git pull`download from remote

`git remote` list of remote repos

`git remote -v`

`git remote show [name]`describes remote repo

`git remote update`fetches latest updates

`git fetch` download specific objects

`git branch -r` lists remote branches

`git rebase [name]` puts a branch on top of other branch

`git rebase -i [pointer]` lets choose which commit and in which to rebase (unlike cherry-pick gives a list of hashes)

`git cherry-pick [pointer]` choose and rebase commits by hashes




#### Git Commands

|Git command				|Description|
|:--------------------------|:--------------------------|
|`git init`					|Initialize a local Git repository|
|`git clone repo_url`		|Clone public repository|
|`git clone ssh://git@github.com/[username]/[repository-name].git`|	Clone private repository|
|`git status`				|Check status|
|`git add [file-name]`		|Add a file to the staging area|
|`git add -a`				|Add to staging area but *only tracked* files. New files should be used added with `git add`
|`git add -p`				|Allows a user to interactively review patches to add to the current commit
|`git commit`				|Commit changes (will asked to enter message)
|`git commit -m "[message]"`|Commit changes - adding message inline
|`git commit -a`			|Stages files automatically
|`git commit --amend`		|Is used to make changes to commits after-the-fact
|`git log`					|View changes
|`git log --summary`		|View changes (detailed)
|`git log --oneline`		|View changes (briefly)
|`git log -p`				|Produces patch text
|`git show`					|Shows various objects
|`git diff`					|Preview changes before merging in different commits
|`git diff --staged`		|An alias to --cached, this will show all staged files compared to the named commit
|`git rm`					|Remove a file (or folder)
|`git mv`					|Similar to the Linux `mv` command, this moves a file
|`git checkout [name]`		|Switch to a branch
|`git checkout -`			|Switch to the branch last checked out
|`git reset`				|Basically resets the repo, throwing away some changes.
|`git revert`				|Makes a new commit which effectively rolls back a previous commit. It’s a bit like an undo command.
|`git branch`				|List of branches (the asterisk denotes the current branch)
|`git branch -a`			|List all branches (local and remote)
|`git branch [name]`		|Create a new branch
|`git branch -d [name]`		|Delete a branch
|`git branch -D [name]`		|Delete a branch forcefully
|`git push origin --delete [name]` |Delete a remote branch
|`git checkout -b [name]`|Create a new branch and switch to it
|`git checkout -b [name] origin/[name]`|	Clone a remote branch and switch to it
|`git branch -m [old name] [new name]`|	Rename a local branch
|`git merge [branch name]`	|Merge a branch into the active branch
|`git merge [source branch] [target branch]`|Merge a branch into a target branch
|`git stash`				|Stash changes in a dirty working directory
|`git stash clear`			|Remove all stashed entries
|`git push origin [branch name]`|Push a branch to your remote repository
|`git push -u origin [branch name]`|	Push changes to remote repository (and remember the branch)
|`git push`					|Push changes to remote repository (remembered branch)
|`git push origin --delete [branch name]`|	Delete a remote branch
|`git pull`					|Update local repository to the newest commit
|`git pull origin [branch name]`|	Pull changes from remote repository
|`git config --global user.name "your_username"`|	Set globally Username
|`git config --global user.email "your_email_address@example.com"`|	Set globally Email id
|`git config --global --list`	|Get global config


</details>