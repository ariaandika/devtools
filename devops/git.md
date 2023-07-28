# Git

git is a version control

## cheatsheet

starting

```bash
git init
git clone <repo_url>
```

end of the day

```bash
git add .
git commit -m "initial commit"
git push
```

check

```bash
git status
git log
```

remote

```bash
git remote add origin https://github.com/ariaandika/logistic.git

git pull
git fetch
```

traveling

need to be in a clean working directory

```bash
# goto previous commit
git checkout <commit_id>

# goto other branch
git checkout feature
```

branching

```bash
# list branch
git branch

# new branch
git branch feature

# merge
git merge feature
```

stash

```bash
git stash

git stash pop
```

squash

```bash
git merge feature --squash
```
