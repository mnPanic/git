Multiple users with SSH
=======================

In order to configure authentication of multiple users with SSH,
follow these steps:

1. [Generate the keys and add them to your account](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
2. Configure the ssh key with the user
    [Source](https://medium.freecodecamp.org/manage-multiple-github-accounts-the-ssh-way-2dadc30ccaca)

    ```sh
    ~/.ssh/config>

    # Personal account, - the default config
    Host github.com
        IdentityFile ~/.ssh/id_rsa
        IdentitiesOnly yes
        HostName github.com
        User git

    # Work account
    Host work.github.com
        IdentityFile ~/.ssh/id_rsa_work_user1
        IdentitiesOnly yes
        HostName github.com
        User git
    ```

    The `IdentitiesOnly` is used so that the correct ssh key is used, and the
    other one isn't tried.
    [Source](https://stackoverflow.com/questions/4565700/how-to-specify-the-private-ssh-key-to-use-when-executing-shell-command-on-git)

    After this, to clone:

    ```sh
    # Personal account
    git clone git@github.com:repo.git

    # Work account
    git clone git@work.github.com:repo.git
    ```

3. Configure authors

    This can either be done

    * Manually

        ```sh
        # For a single repository, overriding global configuration
        git config user.name "username"
        git config user.email "username@gmail.com"

        # Global config, stored at ~/.gitconfig
        git config --global user.name "username"
        git config user.email "username@gmail.com"
        ```

    * Automatically

        [Conditional includes](https://git-scm.com/docs/git-config#_conditional_includes)
        are used.

        > Example: for all repositories inside ~/somedir to have a specific username

        ```sh
        ~/.gitconfig

        [user]
            name = John Doe
            email = john@doe.tld

        [includeIf "gitdir:~/somedir/"]
            path = ~/somedir/.gitconfig
        ```

        ```sh
        ~/somedir/.gitconfig

        [user]
            name = John Doe Company
            email = john.doe@company.tld
        ```
