# git

Cosas afines a Git

## Config

### [SSH](ssh.md)

### [Multiple users](multiple_users.md)

### Set `vim` as core editor

`git config --global core.editor /usr/bin/vim`

Or, more generally:

`git config --global core.editor $(which vim)`

## Bash

### [Bash completion](https://github.com/bobthecow/git-flow-completion/wiki/Install-Bash-git-completion)

## Log

### A Dog

```bash
git log --all --decorate --oneline --graph
```

> "**A Dog**" = git log --**a**ll --**d**ecorate --**o**neline --**g**raph

[Reference](https://stackoverflow.com/questions/1057564/pretty-git-branch-graphs)

### Search code

```bash
# Search for occurrences of 'string' in code
git log -Sstring
```

### Search commits

```bash
# Search for occurrences of 'string' in commits
git log --grep string
git log --author="mnPanic"
git log --since="1 week ago"
```

### View changes

```bash
# Patch (diff)
git log -p
```

## Stash

```bash
# Include untracked changes
git stash --include-untracked
git stash -u

# Diff between local and last stash
git stash show

# Apply the last stash
git stash apply
# Drop the last stash
git stash drop
# Apply and drop the last stash
git stash pop
# Pop a specific stash
git stash pop stash@{1}

# List stash
git stash list
```

## Add

### Add empty directories

Add `.keep` files in every empty directory you want to add.

[Source](https://stackoverflow.com/questions/115983/how-can-i-add-an-empty-directory-to-a-git-repository)

## Add only parts of a file

Use `git add -p` to add the _hunks_ of the file interactively.

- `s` to split the hunks even more.
- `e` to edit the hunks manually.

## Commit

### Auto fixup / squash

[Reference](https://thoughtbot.com/blog/autosquashing-git-commits)

### Change of authors

#### Single commit

```bash
git commit --amend --author="Author Name <email@address.com>"
```

#### [Multiple commits at once](https://help.github.com/en/articles/changing-author-info)

## Rebase

### Change branch base

```bash
git rebase --onto newBase oldBase feature/branch
```

[Reference](https://stackoverflow.com/questions/10853935/change-branch-base)
