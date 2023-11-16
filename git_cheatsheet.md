# Git Cheatsheet

## Set Up a New Repository

```zsh
git clone [git url for project]
```

## Managing Remote Branches

### Set Up Remotes

```zsh
git remote add upstream [git url for main project]
git remote set-url origin [git url for fork]
git fetch upstream
git branch -u upstream/master
```

### Check `origin` and `upstream` Remote URLs

```zsh
git remote -v
```

## Managing Local Branches

### Check Out a New Branch

```zsh
git checkout master
git pull
git checkout -b issue-*
git push -u origin HEAD
```

### Pull In Updates to a Branch

```zsh
git remote add <name> <URL>
git fetch <name>
get checkout <branch>
```

### Add and Pull a Branch from a Fork

```zsh
git remote add <name> <URL>
git fetch <name>
get checkout <branch>
```

### Delete a Local Branch

```zsh
git branch -d <branch>
```

## Updating Commit History

### Committing New Changes

```bash
git status
git add . # obviously only do this once the status has been reviewed
git commit -m "make this a good description; should be present tense and treated as instructions for what you did"
git push origin
```

If you're working in a collaborative project, you can then review the git pull request, make sure everything looks good, and move the task to the "Ready for Review" column of the GitHub project board.

### Undoing Local Commits

Command structure:

```zsh
git reset [optional: arguments specifying which type of reset] [commit to return to]
```

Ways to specify the commit you want to return to:

- `HEAD`: the most recent or current commit; does not include staged changes or modifications in the working directory. This is useful if you broke your program since the last commit and can't remember how to fix it.
- `HEAD^`: the commit directly before the most recent commit; you could use this if you just committed something and realized you'd made a mistake in which files you added.
- `HEAD~[n]`: the commit _n_ commits before the most recent. Use this one if you need to jump back further in your commit history.

The `reset` command without any arguments will move you back to the commit you specify, but your files in the working directory will not change. You'll see the same files locally as before, but they won't be saved as part of your branch anymore. So for example, if you just committed some files, but realized there was something you forgot to add to one of them, you might use:

```zsh
git reset HEAD^
```

Adding the argument `--soft` will move you back to a previous commit, but keep all the changes you've committed since then in the index, or "staging area" where files go when you say `git add`. Everything in your working tree will be untouched. If you just made two commits, then realized your history would make more sense if you combined the two into one commit, you might use:

```zsh
git reset --soft HEAD~2
git commit ...
```

If you want to get rid of _all_ your most recent changes and reset all your files to a certain commit, choose one of the following, you can use the argument `--hard`. Be careful with this command, because you will lose _every change you've made_ since the commit you reset to. Your working directory and your branch will both reflect the commit you specify. You might use this if you've made a lot of changes since your last commit, realized you were writing useless spaghetti code, and need to go back to where things still worked. In that situation, you might use:

```zsh
git reset --hard HEAD
```

### Undoing Only Part of a Commit

```zsh
git show [commit hash] >> changes.diff
```

Edit the `changes.diff` file that was just created and remove the parts of the commit you want to **keep**.

```zsh
git apply --reverse changes.diff
```

Everything in the `changes.diff` file will now be removed.

### Undoing a Commit Sent to a Remote

Use `git reset` as specified above, then use:

```zsh
git push -f
```

Avoid this as much as possible.
