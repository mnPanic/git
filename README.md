# git
Cosas afines a Git

## Config

### [SSH](ssh.md)

### [Multiple users](multiple_users.md)

## Bash

### [Bash completion](https://github.com/bobthecow/git-flow-completion/wiki/Install-Bash-git-completion)

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