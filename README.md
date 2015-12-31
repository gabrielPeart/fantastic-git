# git-commands
Useful git commands

Tag
--

### List all tags

```
git tag
```

### Tag a commit

```
git tag -a v1.4 -m "my version 1.4"
```

### Delete remote tags

- [How to delete a remote tag?](http://stackoverflow.com/a/5480292/1418457)

```
git push --delete origin tagname
```

```
git push origin :tagname
```

### Push tag to remote

- [Push a tag to a remote repository using Git?](http://stackoverflow.com/a/5195913/1418457)

```
git push origin tagname
```

### Rename tag

- [How do you rename a Git tag?](http://stackoverflow.com/a/5719854/1418457)

```
git tag new old
git tag -d old
git push origin :refs/tags/old
git push --tags
```

### Move tag from one commit to another commit

- [How can I move a tag on a git branch to a different commit?](http://stackoverflow.com/a/8044605/1418457)

```
git push origin :refs/tags/<tagname>
git tag -fa tagname
git push origin master --tags
```

Remote
--

### List all remote

```
git remote
```

### Rename remote

- [Renaming a remote](https://help.github.com/articles/renaming-a-remote/)

```
git remote rename old new
```

Branch
--

### List all branches

```
git branch
```

### Create a branch

- [Create a new branch with git and manage branches](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)

Create the branch on your local machine and switch in this branch

```
git checkout -b branch_name
```

### Create branch from commit

- [Branch from a previous commit using git](http://stackoverflow.com/a/2816728/1418457)

```
git branch branch_name sha1_of_commit
```

### Push the branch to remote

```
git push origin branch_name
```

### Rename local branch

- [How do you rename the local branch?](http://stackoverflow.com/a/6591218/1418457)

Rename other branch

```
git branch -m old new
```

Rename current branch

```
git branch -m new
```

### Rename remote branch

- [Rename master branch for both local and remote Git repositories](http://stackoverflow.com/a/16220970/1418457)

```
git branch -m old new                # Rename branch locally    
git push origin :old                 # Delete the old branch    
git push --set-upstream origin new   # Push the new branch, set local branch to track the new remote
```

Commit
--

### Undo last commit

- [How do you undo the last commit?](http://stackoverflow.com/a/6866485/1418457)

```
git reset --hard HEAD~1
```

### Squash last n commits into one commit

- [Squash my last X commits together using Git](http://stackoverflow.com/questions/5189560/squash-my-last-x-commits-together-using-git)

Do the squashing on a separate branch
```
git checkout -b squashed_feature
```

```
git reset --soft HEAD~3 &&
git commit
```

```
git rebase -i <after-this-commit> // commit X+1 i.e. parent of the oldest commit you want to squash.
```

### Pick

- [CHERRY-PICKING EXPLAINED](http://think-like-a-git.net/sections/rebase-from-the-ground-up/cherry-picking-explained.html)

```
git cherry-pick hash_commit_A hash_commit_B
```

### Reflog

Show reflog

```
git reflog
```

### Amend

- [Edit an incorrect commit message in Git](http://stackoverflow.com/questions/179123/edit-an-incorrect-commit-message-in-git)

```
git commit --amend
```

```
git commit --amend -m "New commit message"
```

- [Changing git commit message after push](http://stackoverflow.com/questions/8981194/changing-git-commit-message-after-push-given-that-no-one-pulled-from-remote)

```
git commit --amend -m "New commit message"
git push --force <repository> <branch>
```

Checkout
--

### Checkout a tag

```
git checkout tagname
```

```
git checkout -b newbranchname tagname
```

### Checkout a branch

```
git checkout destination_branch
```

Use -m if there is merge conflict

```
git checkout -m master // from feature branch to master
```

### Checkout a commit

```
git checkout commit_hash
```

```
git checkout -b newbranchname HEAD~4
```

```
git checkout -b newbranchname commit_hash
```

Stash
--

- [6.3 Git Tools - Stashing](https://git-scm.com/book/en/v1/Git-Tools-Stashing)

### Stash

```
git stash save "stash name"
```

```
git stash
```

### List all stashes

```
git stash list
```

### Apply a stash


```
git stash pop
```

```
git stash apply
```

```
git stash apply stash@{2}
```

Rebase
--

```
git rebase base // rebase the current branch onto base
```

Misc
--

- [How to get “their” changes in the middle of conflicting Git rebase?](http://stackoverflow.com/questions/8146289/how-to-get-their-changes-in-the-middle-of-conflicting-git-rebase)

```
git checkout --ours foo/bar.java
git add foo/bar.java
```

- [Resolve Git merge conflicts in favor of their changes during a pull](http://stackoverflow.com/questions/10697463/resolve-git-merge-conflicts-in-favor-of-their-changes-during-a-pull)
- [Is there a “theirs” version of “git merge -s ours”?](http://stackoverflow.com/questions/173919/is-there-a-theirs-version-of-git-merge-s-ours)

```
git pull -X theirs
```

```
git checkout --theirs path/to/the/conflicted_file.php
```

```
git checkout --theirs .
git add .
```

```
git checkout branchA
git merge -X theirs branchB
```
