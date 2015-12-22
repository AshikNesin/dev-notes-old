Git is command line application

### What is a version control system? And why would I use one?


- track the history of source code

- snapshot of the code at different stages

- roll back

- create branches

- code sharing

## Install

### Configuration


1. System => 
2. Global (User) => ~/.gitconfig
3. Local => .git/config


```sh


git config --global user.name "Ashik Nesin"
git config --global user.email "mail@ashiknesin.com"


```

## Initialize


```sh
git init
```

## Basic Commands


status

### Delete Git Branch
```
git branch -d branch_name
git push origin branch_name

```

### Rollback to certain BRANCH
```
git reset --hard <commit_id>

```

### Show All Branches

```
git show-branch --all


```

### Rename a Branh

```

git branch -m <old branch name> <new branch name>

git branch -m <new name> (current)


```