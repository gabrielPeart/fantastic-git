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
