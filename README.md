# SVN

## Create a repository

```sh
    svnadmin create ${repo-name}
```

### List Repository

```sh
    svn list ${protocol}:///${path}
```

Parameters: 
  - -r <revision>

### Import project

```sh
    svn import ${path} ${url-repo}
```

### Checkout

```sh
    svn co <url> <repo-name>
    cd <repo-name> && svn info
```

Parameters: 
  - -r <revision>
  -  --set-depth

### Show changes

```sh
    svn status
    svn diff <file>?
```
Parameters: 
  - -u: Show updates in repository

```sh
    svn blame (praise, annotate, ann)
```

### Discard changes

```sh
    svn revert <file>
```

### Commit changes

```sh
    svn commit -m "message"
```

### Update working copy

```sh
    svn update
```

### svn status codes

| Code | Description                       |
| :--- | :-------------------------------- |
| M    | Modify                            |
| A    | Added                             |
| D    | Deleted                           |
| ?    | Unknown                           |
| !    | It doesn't exists in working copy |

### Add files to the working copy

```sh
    svn add <file>
```

### Delete files from the working copy

```sh
    svn del <file>
```

### Rename a file

```sh
    svn mv <file_to_rename> <new_name> 
    svn commit ...
    svn status ensalada_de_patatas.txt
```

### Show file content

```sh
    svn cat <url>
```

Parameters: 
- -r : show revision number

### Ask for difference

```sh
    svn diff -r 5:7 <url>
```

### Show deleted files in directory

```sh
    svn log <path> -v
```

### Changelist
```sh
    svn changelist <name> <list of files>
    svn update --cl <name>
```
    Support for changelist:
    - update
    -  revert 
    -  diff
    -  commit

### Remove a file from a changelist

```sh
    svn cl --remove <name of file>
```

### Preserve changelist after commmiting

By default a changelist is deleted after a commit. If you want to preserve is neccessary to add a parameter:
```sh
    svn commit -m "my commit msg" --cl <changelist> --keep-changelists
```

### Ignore
```sh
    svn propedit svn:ignore .
```

### Mark a conflict as resolved

```sh
    svn resolved <name of file resolved>
```

### Resolving tree conflicts

```sh
    svn patch <from file> <dest path>
    svn revert <from file> 
```

### Branches

```sh
    svn import . <url-repo>/trunk -m "message"
    svn co <url-repo>/trunk trunk

    svn copy -m "branch 1.0" <url-repo>/trunk <url-repo>/branches/branch_1_0 --parents

    svn co <url-repo>/branches/branch_1_0
```

### Merge

```sh
    svn merge -c <revision number> caret/branches/branch_1_0
    svn commit -m "bug fixed"
```

### Switch

```sh
    
```

### Help

```sh
    svn <subcmd>? help
```