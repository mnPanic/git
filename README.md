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

## Commit

### Change of authors

#### Single commit

```bash
git commit --amend --author="Author Name <email@address.com>"
```

#### [Multiple commits at once](https://help.github.com/en/articles/changing-author-info)