# Git Commands

# Setting up SSH in the local machine and adding SSH Key Pair  in the Git Hub Account

Signup to Github Account:

When working with GitHub repository, you'll often need to Username and Password to login to GitHub.

Alternate Option is to Use SSH Key to identify yourself that doesn't require you to enter your username and password each time.

SSH protocol: you can connect and Authentiate to remote servers and services.

Below are the steps:

Step 1: Generating a new SSH key

    ssh-keygen -t ed25519 -C "your_email@example.com"

Step 2: Start the SSH Agent and Adding your SSH key to the ssh-agent (Mac)

    eval "$(ssh-agent -s)"
    ssh-add --apple-use-keychain ~/.ssh/id_ed25519

Step 3: Add SSH key to Git Hub Account

    $ pbcopy < ~/.ssh/id_ed25519.pub
    # Copies the contents of the id_ed25519.pub file to your clipboard
    # In the upper-right corner of any page on GitHub, click your profile photo, then click Settings.
    # In the "Access" section of the sidebar, click  SSH and GPG keys.
    # Click New SSH key or Add SSH key.

Step 4: Testing your SSH Connection

    ssh -T git@github.com
    # > Hi USERNAME! You've successfully authenticated, but GitHub does not
    #> provide shell access.

References: https://docs.github.com/en/authentication/connecting-to-github-with-ssh

