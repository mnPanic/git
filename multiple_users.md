# Multiple users

## SSH Authentication

[Source](https://medium.freecodecamp.org/manage-multiple-github-accounts-the-ssh-way-2dadc30ccaca)

```txt
~/.ssh/config

# Personal account, - the default config
Host github.com
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa

# Work account
Host work.github.com
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa_work_user1
```

### Cloning

```bash
# Personal account
git clone git@github.com:repo.git

# Work account
git clone git@work.github.com:repo.git

```
## Change authors

### Manually

```bash
# For a single repository, overriding global configuration
git config user.name "username"
git config user.email "username@gmail.com"

# Global config, stored at ~/.gitconfig
git config --global user.name "username"
git config user.email "username@gmail.com"
```

### Automatically

In order to change authors for all repositories of a directory, [**conditional includes**](https://git-scm.com/docs/git-config#_conditional_includes) are used.

> Example: for all repositories inside ~/somedir to have a specific username

```txt
~/.gitconfig

[user]
    name = John Doe
    email = john@doe.tld

[includeIf "gitdir:~/somedir/"]
    path = ~/somedir/.gitconfig
```

```txt
~/somedir/.gitconfig

[user]
    name = John Doe Company
    email = john.doe@company.tld
```
