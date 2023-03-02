# Common Git Commands
Git tracks the changes on the files in every commit not copy the entire project for every commit, it only stores the changes that happened during each commit, we can see the changes that were made in any commit using: .
```sh
git show <commit_id> 
```
- <Commit\_id>: Can be `full id` Or `first 7 digits`.
  - full id: 18497d7...061f459
  - first 7 digits: 18497d7

![git stages with reset](https://www.howtogeek.com/wp-content/uploads/csit/2021/07/f5026f58.png?trim=1,1&bg-color=000&pad=1,1)

## Generate public/private ssh keys
```
ssh-keygen -t rsa -b 4096 - C 'github_email'
```

## Commit Messages
For good commit messages, you must make them suitable for completing this sentence:
```
If applied, this commit will ...
```
Make it composed of an informative header with no more than 50 characters and detailed dotted messages for the body.
`e.g`

![ good commit message ](https://github.com/[Mahmoud821]/[Git-Commands]/blob/[master]/images/good-commit-message.png?raw=true)


## Symbols
| Symbol | Meaning |
| ------ | ------- |
| Asterisk (\*)  | All files that have the **current** directory in their path |
| Dot (.) | All files that have the **current** directory in their path |
| Double dots (..) | All files that have the **parent** directory in their path |

## Commands

| Command | Option | Argument | Description |
| ------- | ------ | -------- | ----------- |
| git config user\.name | --global | github_username | ----------- |
| git config user\.email | --global | github_email | ----------- |
| git init | ------ | -------- | Initialize the local git repository |
| git status | ------ | -------- | ----------- |
| git add | ------ | < file\_name > Or < file\_name`1` file_name`2` ... > Or < * > Or < . > Or < . . >| from the working directory to the staging area. |
| git restore | ------ | < file\_name > Or < file\_name`1` file_name`2` ... > Or < * > Or < . > Or < . . > | if the file was in the staging area and we modified it again and want to discard the new changes, we can restore it from the same file in the staging area, it will only discard the new changes and the file will not be unstaged from the staging area. |
| git restore | -staged | < file\_name > Or < file\_name`1` file_name`2` ... > Or < * > Or < . > Or < . . > | undo [git add], remove any file we specify from the staging area without any modification to the working directory. |
| git commit | ------ | -------- | will open the vim text editor for multiline messages in the [git commit]. |
| git commit | -m | < message > | from staging area to the local repo, one line message |
| git commit | --amend -m | < message > | if you want to rewrite a new message for the last commit or want to add another file modification with the last commit, you can add that file to the staging area and then commit it using that command to add that file modification to the last commit. |
| git revert | ------ | < commit_id >  | reverse the effect of some earlier commits (often only a faulty one) as a new commit, like undo. |
| git reset | --soft |  < commit_id > | uncommit changes, changes are left staged (index). |
| git reset | --mixed |  < commit_id > | (default): uncommit + unstage changes, changes are left in working tree. |
| git reset | --hard |  < commit_id > | (DANGEROUS): uncommit + unstage + delete changes, nothing left. |
| git reflog | ------ | -------- | used to find and restore the orphaned commits (the commits we don't see after reset) if it was reset no more than 30 days ago. |
| git log | ------ | -------- | display all commit history |
| git log | --oneline | -------- | display all commit history with a short format |
| git log | --state | -------- | more data about ["the files that were modified in each commit", "the number of lines added or removed", ...] |
| git show | ------ | < commit\_id > | display the changed data in that commit, `default` commit_id is where the head pointed |
| git diff | --staged | -------- | View the difference between the [last commit] in the branch and the [staging area] |
| git diff | ------ | head | View the difference between the [last commit] in the branch and the tracked files in the [Working Directory] no matter whether staged or not |
| git diff | ------ | < first\_commit\_id > < second\_commit_id > | display the changes that happened to the first_commit to be like the second_commit, the order is matter |
| git checkout | ------ | < commit\_id > Or < branch_name > | switch branch, or go to a specific commit, change the head pointer to go wherever we want on the project's [branches and commits] |
| git checkout | -b  | < new_branch_name > | create a new branch and let the head point to it, shortcut for [git branch new_branch_name;  git checkout new_branch_name]. |
| git remote | ------ | -------- | display all created variables that store repo_links. |
| git remote | -v | -------- | display all created variables with stored repo_links |
| git remote add origin | ------ | < repo\_link > | set the variable [origin = repo\_link] to < push, pull, ...> without writing the full [repo_link] every time. |
| git remote rename  | ------ | < current_name > < new_name > | to rename a remote repository variable |
| git remote rm origin | ------ | -------- | remove the variable [origin] that carries the repo_link |
| git push | ------ | [< repo\_link > Or < variable\_pointed\_to\_repo > ] < branch\_name > |  push the local\_repo into the global_repo, `example`: git push origin master |
| git pull | ------ | [< repo\_link > Or < variable\_pointed\_to\_repo > ] < branch\_name > |  pull the latest global\_repo update into the local_repo to continue development from the last update(commit) if you want the last update, `example`: git pull origin master |
| git branch | ------ | -------- | display all existing branches |
| git branch | ------ | < branch_name > | create a new branch starting from the commit that the head pointed on |
| git branch | ------ | -------- | Git will not let you delete the branch you are currently on so you must make sure to checkout a branch that you are NOT deleting. |
| git branch | -d | < local_branch_name > | (locally) will delete the branch only if it has already been pushed and merged with the remote branch. |
| git branch | -D | < local_branch_name > | (locally) force the branch to be deleted, even if it hasn't been pushed or merged yet. |
| git push origin | --delete | < remote_branch_name > | delete branch remotely |
| git branch | -m | < new_name > | to rename the current branch name |
| git merge  | ------ | < brance_name > | merge the specified branch with the currently used branch |
| git clone | ------ | < repo_link > | clone a repo and create a new variable [origin = cloned_repo_link]. |
| git tag | ------ | -------- | display all created tags. |
| git tag | ------ |  < tag_name Or version_number_as_tag_name > < commit_id > | (lightweight) create a tag, used for versioning (e.g v1.0.1). |
| git tag | -a -m | < tag_name > < commit_id > 'message_about_the_tag' | (annotated) create a tag, used for versioning (e.g v1.0.1), and add more data about the tag when using [git show tag_name]. [e.g] `git tag -a v1.0.0 9319028 -m 'Hello world again'` |
| git tag | -d | < tag_name >  | Delete a local Git tag |
| git push origin | --delete |  < tag_name > | Delete a remote Git tag |
| git push origin | ------ | < tag_name > | push a Git tag to the remote repository.  |
| ------- | ------ | -------- | ----------- |

