# Common Git Commands
Git tracks the changes on the files in every commit not copy the entire project for every commit, it only stores the changes that happened during each commit, we can see the changes that were made in any commit using: .
```sh
git show <commit_id> 
```
- <Commit\_id>: Can be `full id` Or `first 7 digits`.
-- full id: 18497d7...061f459
-- first 7 digits: 18497d7

## Symbols
| Symbol | Meaning |
| ------ | ------- |
| Asterisk (\*)  | All files that have the **current** directory in their path |
| Dot (.) | All files that have the **current** directory in their path |
| Double dots (. .) | All files that have the **parent** directory in their path |

## Commands

| Command | Option | Argument | Description |
| ------- | ------ | -------- | ----------- |
| git config user. name | --global | github_username | ----------- |
| git config user\.email | --global | github_email | ----------- |
| git init | ------ | -------- | ----------- |
| git status | ------ | -------- | ----------- |
| git add | ------ | < file\_name > Or < file\_name`1` file_name`2` ... > Or < * > Or < . > Or < . . >| from the working directory to the staging area. |
| git restore | ------ | < file\_name > Or < file\_name`1` file_name`2` ... > Or < * > Or < . > Or < . . > | if the file was in the staging area and we modified it again and want to discard the new changes, we can restore it from the same file in the staging area, it will only discard the new changes and the file will not be unstaged from the staging area. |
| git restore | -staged | < file\_name > Or < file\_name`1` file_name`2` ... > Or < * > Or < . > Or < . . > | undo [git add], remove any file we specify from the staging area without any modification to the working directory. |
| git commit | -m | < message > | from staging area to the local repo |
| git revert | ------ | < commit_id >  | reverse the effect of some earlier commits (often only a faulty one) as a new commit, like undo. |
| git reset | --soft |  < commit_id > | uncommit changes, changes are left staged (index). |
| git reset | --mixed |  < commit_id > | (default): uncommit + unstage changes, changes are left in working tree. |
| git reset | --hard |  < commit_id > | (DANGEROUS): uncommit + unstage + delete changes, nothing left. |
| git reflog | ------ | -------- | used to find and restore the orphaned commits (the commits we don't see after reset) if it was reset no more than 30 days ago. |
| git log | ------ | -------- | display all commit history |
| git log | --oneline | -------- | display all commit history with a short format |
| git log | --state | -------- | more data about ["the files that were modified in each commit", "the number of lines added or removed", ...] |
| git show | ------ | < commit\_id > | display the changed data in that commit, the default commit_id is where the head pointed |
| git diff | ------ | < first\_commit\_id second\_commit_id > | ----------- |
| git checkout | ------ | < commit\_id > Or < branch_name > | switch branch, or go to a specific commit, change the head pointer to go wherever we want on the project's [branches and commits] |
| git remote | ------ | -------- | display all created variables that store repo_links. |
| git remote | -v | -------- | display all created variables with stored repo_links |
| git remote add origin | ------ | < repo\_link > | set the variable [origin = repo\_link] to < push, pull, ...> without writing the full [repo_link] every time. |
| git remote rm origin | ------ | -------- | remove the variable [origin] that carries the repo_link |
| git push | ------ | [< repo\_link > Or < variable\_pointed\_to\_repo > ] < branch\_name > |  push the local\_repo into the global_repo, example: git push origin master |
| git pull | ------ | [< repo\_link > Or < variable\_pointed\_to\_repo > ] < branch\_name > |  pull the latest global\_repo update into the local_repo to continue development from the last update(commit) if you want the last update, example: git pull origin master |
| git branch | ------ | -------- | display all existing branches |
| git branch | < branch_name > | -------- | create a new branch starting from the commit that the head pointed on |
| git merge  | ------ | < brance_name > | merge the specified branch with the currently used branch |
| ------- | ------ | -------- | ----------- |

