# git

## git init

### Usage

```zsh
git init
```

## git remote

### Usage

```zsh
git remote add [ name ] [ remote_repository_path ]
git remote rename [ remote_repository_path ] [ new_name ]
git remote show [ remote_repository_path or repository_name ]
```

* ``git remote add``: Connect remote repository with local repository by the name.
* ``git remote rename``: Rename remote repository name.
* ``git remote show``: Show information of remote repository.

### Example

```zsh
git remote add origin https://github.com/lands-takahiro/lands-takahiro
git remote show origin
```

## git clone

### Usage

```zsh
git clone [ repository_path ] [ new_repository_path ]
```

### Example

```zsh
git clone https://github.com/lands-takahiro/lands-takahiro
```

## git rm

### Usage

```zsh
git rm [ --cached ] ${file}
```

* ``${file}``: Remove file from work tree and index.
* ``--cached``: Remove file of index only.

### Example

```zsh
git rm a.txt
git rm --cached a.txt
```

## git mv

### Usage

```zsh
git mv ${filename1} ${filename2}
```

### Example

```zsh
git mv a.txt b.txt
```

## git add

### Usage

```zsh
git add ${modified_files}
```

### Reset git add

* First git add

```zsh
# All files reset
git rm --cached .
# Specific file
git rm --cached ${file}
```

* Second and more git add

```zsh
# All files reset
git reset HEAD
# Specific file
git reset HEAD ${file}
```

## git commit

### Usage

```zsh
git commit -m "${commit_message}"
```

### Reset git commit

* Usage

```zsh
git reset [ --hard or --soft ] HEAD[^,~,~{n}]
```

* ``--hard``: Reset commit and modified files.
* ``--soft``: Reset commit only.
* ``HEAD^``: Just before commit.
* ``HEAD~``: 1 before commit.(=``HEAD^``)
* ``HEAD~~``: 2 before commit.
* ``HEAD~{n}``: n before commit.

* Example

```zsh
git reset --soft HEAD~~
```

```zsh
git reset --hard HEAD^
```

### Revert git commit

```zsh
git revert ${commit_id}
```

### Overwrite git commit

```zsh
git commit --amend
```

## git push

### Usage

```zsh
git push [ -set-upstream,-u ] [remote_repository] [branch]
```

### Example

```zsh
git push origin master
```

## git pull

pull = fetch + merge
### Usage

```zsh
git pull [ --set-upstream,-u ] [remote_repository] [branch]
```

### Example

```zsh
git pull origin master
```

## git fetch

### Usage

```zsh
git fetch [ remote_repository ] [ --prune ]
```

* ``remote_repository``: Update information of remote repository to local repository.(Update to ``origin/master`` branch not ``master``)
* ``--prune``: Update information of delete to local.


### Example

```zsh
git fetch
git fetch origin master
git fetch --prune
```

## git merge

### Usage

```zsh
git merge [ branch ]
```

### Example

```zsh
git merge origin/master
```

## git branch

### Usage

```zsh
git branch [ --remotes,-r ] [ --all,-a ] [ --verbose,-v,-vv ] [ --delete,-d branch ] [ --set-upstream-to=upstream ] branch
```

* ``no options``: Show local branches.
* ``--remotes,-r``: Show remote branches.
* ``--all,-a``: Show remote and local branches.
* ``--verbose,-v``: Show branches in details.
* ``-vv``: Show tracked remote branches.
* ``--delete,-d branch``: Delete local branch which is merged. Delete remote branch by adding ``-r``.
* ``--set-upstream-to=upstream``: Local checkout branch tracks the remote branch(=upstream).
* ``branch``: Make new branch.

### Example

```zsh
git branch
# * master
git branch -r
#  origin/master
git branch -a
# * master
#   remotes/origin/master
git branch -v
# * master 34b6470 initial commit
git branch -vv
# * master 34b6470 [origin/master] initial commit
```

## git checkout

### Usage

```zsh
git checkout [ branch ] [ commit_id filename ]
```

* ``branch``: Change branch.
* ``commit_id filename``: Restore file of the commit id.

### Example

```zsh
git checkout master
```


