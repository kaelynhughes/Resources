# Command Cheatsheet

## Aliases
```zsh
git commit -m -> gc
git add -> ga
git push -> gp
python3 -> py
```

docker compose -f docker-compose-devl.yml up

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

### Pull In Updates to a Branch

```zsh
git remote add <name> <URL>
git fetch <name>
get checkout <branch>
```

### Undo a Commit

```zsh
git reset HEAD~<number of commits to go back by>
```

### Undo a Commit Sent to a Remote

```bash
git reset HEAD~<number of commits to go back by>
git push -f # this should be avoided if possible
```

### VSCode Keyboard Shortcuts

* Search for a command: `Cmd + Shift + P`
* Open/close a terminal window: `Ctrl + ` `
* Search all files in the current directory: `Cmd + Shift + F`
* Preview a markdown file: `Cmd + Shift + V`

### Other helpful keyboard shortcuts

* Inspector tools: `Cmd + Opt + I`
* Go to mobile view within a Firefox window: `Cmd + Shift + M`
* Full-screen current tab (excluding VSCode): `Cmd + Shift + F`

### Vim Commands

* Exit Vim: `:wq`
* Go to end of document: `G`