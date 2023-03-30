## README please!
*This is a cheatsheet I've made to learn and remember git commands*
- git init: initialize the git repository on the specified archive
- git config --local help.autocorrect 1: authorize git to correct commands when it's misswrited
- git config --local user.name "username": define collaborator username
- git config --local user.email "useremail": define collaborator useremail
- git config --local core.editor "editor": define the default editor to the files of the project
- git config --local alias.aliasname gitcommand: create an alias for a git command
- git status: see the status of the project and its files
- git add *filename or param*: stage the files (its possible to add a specific filename or add all by using the param: *.* or *--all* or *-A*)
- git commit -m "message": creates a local snapshot of the staged files
- git commit -am "message": stage and creates a snapshot, if you already made the first commit of the file
- git remote add origin *LinkToRemoteRepository*: link the local repository to the remote one
- git push -u origin main: in the very first push, is necessary to track the repository principal branch
- git push origin *branchname*: pushes the commits to remote repository