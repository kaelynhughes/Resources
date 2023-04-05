# Command Line Cheatsheet

## Aliases
```zsh
git commit -m -> gc
python3 -> py
```

## Git

### Check `origin` and `upstream` Remote URLs

```zsh
git remote -v
```

### Set Up Remotes

```zsh
git remote add upstream [git url for main project]
git remote set-url origin [git url for fork]
git fetch upstream
git branch -u upstream/master
```

### Check Out a New Branch

```zsh
git checkout master
git pull
git checkout -b issue-*
git push -u origin HEAD
```

### Commit Changes

```zsh
git status
git add . # obviously only do this once the status has been review
git commit -m "make this a good description; should be present tense and treated as instructions for what you did"
git push origin
```
...then review the git pull request, make sure everything looks good, and move the task to the "Ready for Review" column of the GitHub project board
