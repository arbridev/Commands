# Commands for Git

## Author

### List the current author properties

```bash
git config --list
```

## Contributors

### List project contributors

```bash
git shortlog -e -s -n
git shortlog -s -n --all --no-merges
```

## Tags

### List tags with date

```bash
git log --tags --simplify-by-decoration --pretty="format:%ci %d"
```

Example output:

```bash
2020-02-14 18:25:32 -0500  (tag: 5.0.0)
```

## Commits

### List the files included a the commit

```bash
git diff-tree --no-commit-id --name-only -r bd61ad98
```

Reference: https://stackoverflow.com/questions/424071/how-to-list-all-the-files-in-a-commit


## Branches

### List remote branches

```bash
git branch -r
```

### List branches that contains another

```bash
git branch --contains other-branch
```

To show the commits in oldbranch but not in newbranch:

```bash
git log newbranch..oldbranch
```

To show the diff by these commits (note there are three dots):

```bash
git diff newbranch...oldbranch
```

Reference: https://stackoverflow.com/questions/1710894/using-git-show-all-commits-that-are-in-one-branch-but-not-the-others

### Rename

```bash
git branch -m newname
```

or, if you're on another branch:

```bash
git branch -m currentname newname
```

### List last commit by branch

List remote Git branches and the last commit date for each branch. Sort by most recent commit date. 

```bash
for branch in `git branch -r | grep -v HEAD`;do echo -e `git show --format="%ci %cr" $branch | head -n 1` \\t$branch; done | sort -r
```

Reference: https://gist.github.com/jasonrudolph/1810768

## Remotes

### Update local list of branches

```bash
git remote update origin --prune
```

### Rename

```bash
git remote rename fromname toname
```

## Repair

### Returns the head to an indexed reference commit

In the example is 1 commit back on head

```bash
git reset --soft HEAD~1
```

### Clean the remaining files after a hard reset

```bash
git clean -f -d
```