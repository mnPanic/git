# git
Cosas afines a Git

## Config

### [SSH](ssh.md)

### [Multiple users](multiple_users.md)

## Bash

### [Bash completion](https://github.com/bobthecow/git-flow-completion/wiki/Install-Bash-git-completion)

## Log

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

### Change of authors

#### Single commit

```bash
git commit --amend --author="Author Name <email@address.com>"
```

#### [Multiple commits at once](https://help.github.com/en/articles/changing-author-info)