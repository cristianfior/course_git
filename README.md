## README please!
- git init: initialize the git repository on the specified archive
---
- git clone *LinkToRemoteRepositorySSH*: creates a clone of an existing repository
---
- git config --local help.autocorrect 1: authorize git to correct commands when it's misswrited
---
- git config --local user.name "username": define collaborator username
- git config --local user.email "useremail": define collaborator useremail
- git config --local core.editor "editor": define the default editor to the files of the project
---
- git config --local alias.aliasname gitcommand: create an alias for a git command
---
- git config --add --local core.sshCommand 'ssh -i path_to_ssh_key': define the path to the ssh-key
- sudo chmod 600 path_to_ssh_key: give rights to the key
- eval "$(ssh-agent -s)": initialize the ssh-agent
- ssh-add path_to_ssh_key: add the key to the agent, so its possible to use it with git and github
---
- git status: see the status of the project and its files
---
- git clean: removes all unstaged files
---
- git add *param*: stage the files.

| PARAMS        | DESCRIPTION                   |
| ------------- | ----------------------------- |
| filename      | stage only the specified file |
|., --all, -A   | stage all modified files      |
---
- git mv *path/oldfilename* *path/newfilename*: renames a file
---
- git mv *oldpath/filename* *newpath/filename*: moves a file to another folder
---
- git rm *filename*: remove a file from the project
---
- git checkout *filename*: reset a modified file if not staged
---
- git reset HEAD *filename*: unstage a file
---
- git commit -m "message" *param*: creates a local snapshot of the staged files.

| PARAMS                            | DESCRIPTION                                       |
| ----------------------------------| ------------------------------------------------- |
| --author="username <'useremail'>" | set collaborator username and email of the commit |
| - Closes #issuenumber             | closes automatically the specified issue          |
---
- git commit -am "message" *param*: stage and creates a snapshot, if you already made the first commit of the file.

| PARAMS                            | DESCRIPTION                                       |
| ----------------------------------| ------------------------------------------------- |
| --author="username <'useremail'>" | set collaborator username and email of the commit |
| - Closes #issuenumber             | closes automatically the specified issue          |
---
- git commit --amend: edit the last commit message before the push
---
- git remote add origin *LinkToRemoteRepository*: link the local repository to the remote one
---
- git remote -v: return what is the remote repository name and link
---
- git remote rm origin: removes the remote repository from local
---
- git push -u origin main: in the very first push, is necessary to track to where changes goes and from where it comes
---
- git push origin *branchname*: pushes the commits to remote repository
---
- git pull: pull changes from the remote repository
---
- git fetch -a: pull existing branches in remote repository
---
- git diff *param*: show differences between HEAD and the current branch before the commit.

| PARAMS                 | DESCRIPTION                                                |
| ---------------------- | ---------------------------------------------------------- |
| --name-only            | return only the name of the modified files                 |
| branchname             | show difference between HEAD and the specified branch      |
| HEAD:filename filename | show the diffs between files in remote repo and local repo |
| filename1 filename2    | show the diffs between the files                           |
---
- git log *param*:question:: see a timeline of the commits.

| PARAMS                   | DESCRIPTION                                           |
| ------------------------ | ----------------------------------------------------- |
| --decorate               | give back info about the commits                      |
| --author="name"          | filter the log by author                              |
| --oneline                | show only a part of commit hash and its name          |
| --all                    | show the log including all existing branches          |
| --graph                  | show a graph with a tree of merges and rebases        |
| --pretty=oneline         | show the complete commit hash and its name            |
| --since='month day year' | return commits after the date, excluding the set day  |
| --until='month day year' | return commits before the date, excluding the set day |
---
- git shortlog *param*:question:: a simplified log that return the authors, its commits quantity and names.

| PARAMS        | DESCRIPTION                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| -sn           | simplify even more and return only the commits quantity and author username |
---
- git show *param*:question:: show the diffs of the last commit. **Params**: *branch-hash*,  | *tag-version*, 

| PARAMS        | DESCRIPTION               |
| ------------- | ------------------------- |
| branch-hash   | returns diffs of a branch |
| tag-version   | returns diffs of a tag    |
---
- git reflog: map all commands and changes did in the repository
---
- git reset *param* *commithash*: reset the branch to a specific commit.

| PARAMS         | DESCRIPTION                                                  |
| -------------- | ------------------------------------------------------------ |
| --soft         | undo the commit leaving the changes staged                   |
| --mixed        | undo the commit and the staging leaving the changes modified |
| --hard         | undo all changes                                             |
---
- git revert *commit-hash*: reverts the commit you appointed to git.
---
- git *branch*: list all existing local branches
---
- git *branch* *param*:question: *branchname*: creates a new branch.

| PARAMS        | DESCRIPTION        |
| ------------- | ------------------ |
| -d            | deletes the branch |
---
- git checkout *param*:question: branchname: change between branches.

| PARAMS        | DESCRIPTION                                        |
| ------------- | -------------------------------------------------- |
| -b            | creates and checkout automatically to a new branch |
| -             | switches back to the previous branch               |
---
- git branch --set-upstream-to=origin/main branch: set the branch to pull the changes from main
---
- git push origin *:branchname* : will delete the branch on remote repository
---
- git merge *branchname*: the current branch will inherit all features from the branch passed in the command
---
- git rebase *currentbranch* *targetbranch* -i: the current branch will inherit all features from the target branch
---
- git cherry-pick *commit-hash*: pull the changes of a commit to the current branch without needing merge or rebase
---
- git stash *param*:question:: save and hide the features uncommited of a branch.

| PARAMS              | DESCRIPTION                                                             |
| ------------------- | ----------------------------------------------------------------------- |
| list                | return a list with all existing stashes                                 |
| save "stashname"    | creates a named stash                                                   |
| apply stash@{index} | apply the features saved before in the current branch                   |
| apply stashname     | apply the features saved before in the current branch                   |
| clear               | deletes all stashes                                                     |
| drop stash@{index}  | deletes a stash by index                                                |
| drop stashname      | deletes a stash by name                                                 |
| pop                 | removes the first stash in the list and applys in the current branch    |
| branch branchname   | creates a new branch and applys the features of first stash in the list |
| show -p stashid     | show the features of the stash before applying                          |

---
- git tag *param*:question:: returns a list of all existing tags.

| PARAMS        | DESCRIPTION         |
| ------------- | ------------------- |
| -d tagversion | deletes a local tag |
---
- git show *tagversion*: returns all commits and features of the specified tag
---
- git tag -a *version* -m "message": create a tag from the current state of the local repository
---
- git checkout *tagversion*: change between tags
---
- git push origin *param*: push changes to remote repository

| PARAMS        | DESCRIPTION                                               |
| ------------- | --------------------------------------------------------- |
| branchname    | push changes to the specified branch on remote repository |
| tagname       | push the specified tag to remote repository               |
| --tags        | push all tags to remote repository                        |
---
- git push origin *:tagversion* : will delete the tag in the remote repository
---
- git submodule: return existing submodules. A submodule is a way to bring other projects inside yours
---
- git submodule add *LinkToRemoteRepositorySSH* *submodulename*: add submodule to local repository
---
- git push --recurse-submodules=on-demand: push changes to the submodule remote repository
---
- git gc: garbage collector, cleans useless files to be more performatic
---
- git fsck: file system check, check the integrity of the files and if there are corrupted files
---
- git archive *branch* --format=zip --output=zipname.zip: create a compressed archive of a specific branch
---
- git bisect *param*: the debugger of git.

| PARAMS           | DESCRIPTION                                          |
| ---------------- | ---------------------------------------------------- |
| start            | starts the debugger                                  |
| bad commit-hash  | set when the bug was realized                        |
| good commit-hash | set when the bug wasn't occurring                    |
| bad              | tells to git that the bug was ocurring at that point |
| good             | tells to git that the bug is fixed                   |
---
> the symbol of ":question:" means that the param is not mandatory.

> Please check the courses below
>> - [Rodrigo Branas - Git](https://www.youtube.com/watch?v=C18qzn7j4SM&list=PLQCmSnNFVYnRdgxOC_ufH58NxlmM6VYd1)
>> - [Willian Justen - Git e Github para Iniciantes](https://www.youtube.com/watch?v=IBClN6VpJDw&list=PLlAbYrWSYTiPA2iEiQ2PF_A9j__C4hi0A)
>> - [Willian Justen - Git e Github na Vida Real](https://www.youtube.com/watch?v=_Why5uCCrXc&list=PLlAbYrWSYTiNqugqFFWWsgONJsmc3eMpg)
>> - [Matheus Battisti - Git e GitHub do básico ao avançado (c/ gist e GitHub Pages)](https://www.udemy.com/course/git-e-github-do-basico-ao-avancado-c-gist-e-github-pages/)
>> - [Git e GitHub: repositório, commit e versões](https://cursos.alura.com.br/course/git-github-repositorio-commit-versoes)
>> - [Git e Github: controle e compartilhe seu código](https://cursos.alura.com.br/course/git-github-controle-de-versao?preRequirementFrom=git-github-branching-conflitos-pull-requests)
>> - [Git e Github: estratégias de ramificação, Conflitos e Pull Requests](https://cursos.alura.com.br/course/git-github-branching-conflitos-pull-requests)

**That's all folks!**