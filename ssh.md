# SSH

## Configure

[Initial configuration](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

If you have more than one user configured, the `ssh-agent` will always try to use the key that was added with `ssh-add`.

To avoid this, add to the second config file:

```text
Host gitserv
    Hostname remote.server.com
    IdentityFile ~/.ssh/id_rsa.github
    IdentitiesOnly yes  # Add this
```

[Source](https://stackoverflow.com/questions/4565700/how-to-specify-the-private-ssh-key-to-use-when-executing-shell-command-on-git)