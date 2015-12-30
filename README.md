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
