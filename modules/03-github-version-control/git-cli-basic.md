# Git CLI Basics

Set global settings for user information

```bash
git config --global user.name "[name]"

git config --global user.email "[email address]"
```

Check status

```bash
git status
```

Clone a project and working with branches

```bash
git clone [https://repository-link]

git checkout [branch-name]
```

Creating a new branch

```bash
git checkout -b feature/[branch-name]

git checkout -b bugfix/[branch-name]

git checkout -b release/[branch-name]
```

Renaming an existing branch

```bash
git branch -m bugfix/[branch-name] feature/[branch-name] --> Long version of renaming a branch (from bugfix to feature in this example)

git branch -m {bugfix,feature}/[branch-name]--> Short version of renaming a branch (from bugfix to feature in this example)
```

Adding changes for commit

```bash
git add [file] --> This is for adding a single file, following 2 commands are adding all allowed changed files

git add -A

git add .
```

Committing and pushing

```bash
git commit -m "commit message"

git push

git push --set-upstream [remote] [branch-name]--> If the branch is newly created.
```

Changing the most recent commit message

```bash
git commit --amend -m "new commit message"
```

Pull, fetch and merge

```bash
git pull

git fetch

git merge [branch-name]
```

Reset changes

```bash
git reset [commit]

git reset --hard [last-known-good-commit]

git reset --hard HEAD~1 -->Undo the last commit, do not keep the changes.

git reset --soft HEAD~1 -->Undo the last commit, keep the changes.
```

Show all ignored files

```bash
git status --ignored
```

Check local, remote and all branches

```bash
git branch

git branch -r

git branch -a
```

Delete a local branch

```bash
git branch -d feature/branch-name

git branch -d bugfix/branch-name

git branch -d hotfix/branch-name
```

Delete a remote branch

```bash
git push origin --delete feature/branch-name
```

Tag checking and creation

```bash
git tag

git tag -a [tag-name] -m "tag description"

git push origin [tag-name]
```

Start using SSH in a repository where I am currently using HTTPS

```bash
git remote set-url origin git@ssh.dev.azure.com:v3/rest-of-your-project-ssh-url
```

Stash changes

```bash
git stash -->Save the un-committed changes in a "stash". This will remove changes from working tree.

git stash list -->List the stashes

git stash apply -->Apply stash to working tree in current branch

git stash apply stash@{0} -->Apply the stash 0 - change the number in order to apply other stashes

git stash drop stash@{0} -->Remove the stash 0 from stash list - change the number in order to apply other stashes.

git stash pop stash@{1} -->Apply the selected stash and remove it from the stash list.
```

Show all commits of the current branch as well as the parent branch and its commits

```bash
git log --first-parent
```

Exit git log history

```bash
:q -->For exit

:h -->For help
```
