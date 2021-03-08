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

### Print the files included in the commit

```bash
git diff-tree --no-commit-id --name-only -r bd61ad98
```

Reference: https://stackoverflow.com/questions/424071/how-to-list-all-the-files-in-a-commit


## Branches

### List remote branches

```bash
git branch -r
```

## Repair

### Returns the head to an indexed reference commit

In the example is 1 commit back on head

```bash
git reset --soft HEAD~1
```