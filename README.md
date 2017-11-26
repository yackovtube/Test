# Git Workshop
Lab 5: Undoing Changes

---

## Exercises

 - Use the following command to clone a repo:
```
$ git clone https://gitlab.com/git-getstarted/lab5.git
$ cd lab5
```

 - See tracked branches
```
$ git branch
```

 - See all branches
```
$ git branch -a
```

 - Checkout hotfix branch
```
$ git checkout hotfix
```

 - See tracked branches
```
$ git branch
```

 - Move to the master branch
```
$ git checkout master
```

##### Revert

 - Inspect the repository:
```
$ git log --oneline --graph --branches --decorate
```

 - Check the file "print-lines/Program.cs" to see the mistake:
```
$ cat print-lines/Program.cs
```

 - Undo the last commit in the master branch using (don't automatically commit):
```
$ git revert HEAD -n
```

 - Check the file "print-lines/Program.cs" to see the rollback:
```
$ cat print-lines/Program.cs
```

 - Add the changes to the index area and create a commit:
```
$ git add print-lines/Program.cs
$ git commit -m "rollback mistake"
```

##### Cherry-Pick

 - Compare the master branch with the bugfix commit
```
$ git diff bugfix master
```

 - Check the file "print-lines/Program.cs" and find the bug:
```
$ cat print-lines/Program.cs
```

 - Apply the changes of the bugfix commit in the master branch:
```
$ git cherry-pick bugfix
```

 - Check the file "print-lines/Program.cs" and see the fix:
```
$ cat print-lines/Program.cs
```

##### Reset

 - Move to the poc branch
```
$ git checkout poc
```

 - Inspect the branch history:
```
$ git log --oneline --decorate
```

 - Rollback 3 commits backwards until "Add Line 2" (deleting the commits)
```
$ git reset --hard HEAD~3
```

 - Inspect the branch history:
```
$ git log --oneline --decorate
```

---

## Tips

 - Use reset carefully, this command will update the branch reference

 - The unreferenced commits will not be automatically deleted, therefore if you make a mistake you can reset the reference to the previous commit (if you know the commit SHA1)

 - You can recover the SHA1 checking the previous HEAD references using:
 ```
$ git reflog
```