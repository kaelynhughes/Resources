# Git Cheatsheet (Ellie's Edition)

## Starting a New Git Repository

1. Make sure you're in the right folder - if unsure you can run `pwd` to see the whole path of folders that leads to the current one. If you're not in the folder you want on the outside, use `cd [folder name]` to move to the right one.
2. Tell the folder it needs to be a Git repository:
```
git init
```
3. Create a repository in GitHub, then click the green Code button and copy the link. We've been using the one under HTTPS.
4. Tell the folder where to send the files you push:
```
git remote add origin [link you just copied]
```
5. Add all the files you want to upload to the staging area. You can use `.` instead of a filename to add everything in the current folder.
```
git add [filename]
```
6. Set a save point to send to GitHub:
```
git commit -m "[message]"
```
7. Send all the commits on your computer to GitHub:
```
git push -u origin HEAD
```

## Pushing to a repository you've pushed to before

1. Add and commit like normal:
```
git add [filename or .]
git commit -m "[message]"
```
2. Push to GitHub:
```
git push
```

## Other

Check to see which files are in the staging area, which have new changes, etc.: 
```
git status
```

Move from the current folder to its parent folder:
```
cd ..
```

Check to make sure your folder is set to send to the right place:
```
git remote -v
```

