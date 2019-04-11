# Git Cheat Sheet

First `init` a new repository to work with:

```
$ git init REPO_NAME
$ cd REPO_NAME 
```

**Note** Directories are not tracked, just add a `.keep` file

To ignore files add them to `.gitignore`:

```
log/*.log
```

To add just parts to the index we can use `git add -p` (`-p` as in "patch").
