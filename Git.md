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
