#Using Git well to make your repos maintainable

- Perform work in a feature branch. Name branches using snake_case (ex. new_feature)
```
git checkout master
git pull origin master
git checkout -b new_branch
```

- Rebase frequently to incorporate upstream changes. But take care to use rebase when there are more than one member team using the same branch.
```
git fetch
git rebase master
```

- Avoid including files in source control that are specific to your development machine or process.
```
# =(
git add .

# =)
git add -i
```

- Write your commit message with the name of your branch as the prefix between brackets.
```
git commit -m "[branch_name] My commit message"
```

- Write your commit message in the imperative: "Fix bug" and not "Fixed bug" or "Fixes bug".Capitalized, short (50 chars or less) summary

- Use a pull request for code reviews.(https://help.github.com/articles/using-pull-requests/)

- Anything in the master branch is deployable. Mind the gap ;)

- Delete local and remote feature branches after merging.
```
git branch --delete <branch-name>
git push origin --delete <branch-name>
```

####Sources:
- http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
- https://github.com/thoughtbot/guides/tree/master/protocol/git