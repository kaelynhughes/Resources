---
alias: Common Git Commands for Integrations Projects
tags: work/integrations, git, cli
---
# Common Git Commands for Integrations Projects

## Checking `origin` and `upstream` Remote URLs

```bash
git remote -v
```

## Setting Up Remotes

```bash
git remote add upstream [git url for main project]
git remote set-url origin [git url for fork]
git fetch upstream
git branch -u upstream/master
```

## Checking Out a New Branch

```bash
git checkout master
git pull
git checkout -b issue-*
git push -u origin HEAD
```

## Committing Changes

```bash
git status
git add . # obviously only do this once the status has been review
git commit -m "make this a good description; should be present tense and treated as instructions for what you did"
git push origin
```

After pushed to origin, go review the git pull request, to make sure everything is in order. Once that's done, move it to the "Ready for Review" column in the GitHub project board.

## Pulling in Updates to a Branch

```bash
git rebase master --autostash
```

## Adding and Pulling a Branch from a Fork

```bash
git remote add <name> <URL>
git fetch <name>
get checkout <branch>
```

## Undoing a Commit

```bash
git reset HEAD~<number of commits to go back by>
```

### Undoing a Commit Sent to a Remote

```bash
git reset HEAD~<number of commits to go back by>
git push -f # this should be avoided if possible
```
