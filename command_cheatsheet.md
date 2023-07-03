# Command Cheatsheet

## Aliases
```zsh
git commit -m -> gc
git add -> ga
git push -> gp
python3 -> py
```
## Other stuff for command line

Start Aggietime API: 
```zsh
docker compose -f docker-compose-devl.yml up
```
Check what is running on a port: 
* `lsof` = `ls` open files
* `-P`: tells shell not to convert port numbers to port names
    * Can instead do `-nP` if I want to see network numbers instead of network names, eg. 127.0.0.1 instead of localhost
* `-iTCP:5000`: specifies which port
* `grep`: search for a keyword
```zsh
sudo lsof -P -i :[port number]
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

### Pull In Updates to a Branch

```zsh
git remote add <name> <URL>
git fetch <name>
get checkout <branch>
```

### Undo Local Commits

```zsh
git reset HEAD~<number of commits to go back by>
```
If you just committed and want to remove the commit, but keep all your changes intact:
```zsh
git reset HEAD^
```
If you just committed and want to undo the act of committing, but go back to having all the same files staged:
```zsh
git reset --soft HEAD^
```
If you want to get rid of _all_ your most recent changes and reset all your files to a certain commit, choose one of the following:
```zsh
git reset --hard HEAD
git reset --hard HEAD^
git reset --hard HEAD~<number of commits to go back by>
```

### Undo a Commit Sent to a Remote

```bash
git reset HEAD~<number of commits to go back by>
git push -f # this should be avoided if possible
```

## VSCode Keyboard Shortcuts

* Search for a command: `Cmd + Shift + P`
* Open/close a terminal window: `Ctrl + ` `
* Search the current file: `Cmd + F`; add  `Shift` to search the current directory instead
* Preview a markdown file: `Cmd + Shift + V`
* Open/close sidebar: `Cmd + B`
* Select word: `Cmd + D` (press multiple times to also select subsequent occurrences of that word)
* Select line: `Cmd + L` (press multiple times to also select subsequent lines)
* Delete line: `Cmd + Shift + K`
* Split editor: `Cmd + [\, 2, 3, 4]` depending on how many you already have up
    * Switch between sections: `Cmd+
* Move line(s) up/down: `Opt + [↑/↓]`; add `Shift` to copy instead of moving
* Format code: `Opt + Shift + F`
* Peek definition: `Opt + F12`
* Rename a component: `F2`



## Rectangle (windows)

* Left/right/top/bottom half: `Cmd + Opt + [arrow key]`
* Top left/right: `Cmd + Ctrl + [←/→]`
* Bottom left/right: `Cmd + Ctrl + Shift + [←/→]`
* Maximize: `Cmd + Opt + F`
* Maximize height: `Ctrl + Opt + Shift + ↑` 
* Leftmost fourth (for terminal, notes): `Cmd + Ctrl + ↑`
* Second leftmost fourth (for browser?): `Cmd + Ctrl + ↓`

## Vim Commands

* Exit Vim: `:wq`
* Go to end of document: `G`

## Other helpful keyboard shortcuts

* Inspector tools: `Cmd + Opt + I`
* Go to mobile view within a Firefox window: `Cmd + Shift + M`
* Full-screen current tab (excluding VSCode): `Cmd + Shift + F`