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

traveling, need to be in a clean working directory

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

## Commit

amend

```bash
# commit by changing latest commit history without creating new commit
# no edit is about the commit message
git commit --amend --no-edit
```

can also edit last commit message only

## Branching

checkout to previous commit, then create new branch from there

```bash
git checkout <commit-hash>

git switch -c <new-branch>
```

then you can merge back to the original branch

```bash
# after new commits
git checkout <original-branch>

git merge <new-branch>
```

checkout to

## What happen if

- edit staged file

editing staged file will mark both as staged and modified

- rebase fixup within same file

have potential conflict, better use it to fixup multi file edit to one commit
