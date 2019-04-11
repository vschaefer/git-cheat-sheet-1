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

## Disaster Recovery

In case of deleted commits use `git reflog` and `git cherry-pick` to recover those commits:

```
$ git cherry-pick LOST_COMMIT_SHA1
```

**Note** Will be cleaned up once `git gc` ran.

## Getting information out of history

Use `git log --oneline --graph` to get condensed log view.

Use `git blame` to see **last** change for each line.

Use `git show COMMIT_SHA1` to get detailed information about commit (including diff).

Use `git log -S` to search in contents of commits.

## Branches

Branches are essential for any git workflow. To create a new branch run

```
$ git checkout -b BRANCH_NAME

$ git branch BRANCH_NAME
$ git checkout BRANCH_NAME
```

To list all your branches you can run (the active branch will be marked with a `*`)

```
$ git branch
```

Possible worklfow options:

1. Add commits as usual in your branch. When ready `git rebase --interactive master` to cleanup your commits
1. To merge branch back into `master` use `git merge --ff BRANCH_NAME` (`--ff` means fast-forward / rebase) 
1. You can even squash the branch `git merge --squash`
1. Use `git reset --soft` if you accidently added commits to `master`
1. Make sure to merge/rebase `master` **before** merging your branch into `master`


