# Commands to handle environment

## Environment

### List the environment variables

```bash
env
```

### Export variables in a .env file

```bash
export $(grep -v '^#' .env | xargs)
```