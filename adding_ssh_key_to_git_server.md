# Adding SSH Key to Git Server

Some repositories require SSH. It's my preferred method of authenticating as I don't need to enter in my username and password every time I `push` or `pull`. It also works when I have enabled two-factor authentication on my git accounts.

These notes are based on [Gitlabs's documentation](https://docs.gitlab.com/ee/ssh/).

You can also look at the [Bitbucket docs](https://support.atlassian.com/bitbucket-cloud/docs/set-up-an-ssh-key/), but it's not as clear, imho.

Here are the steps to set up SSH with the git server.

## How to Generate SSh Key

Check to make sure you have SSH installed with (version 6.5 or newer):

`ssh -V`

Generate a key:

`ssh-keygen -t ed25519 -C "<comment>"`

for the `<comment>`, I do an email or a computer description like "raspberry_pi". The comment labels the keys online so  you can manage them.

I use the default location and I don't use a passphrase (just leave blank and press `Enter`).

If you do use a passphrase, then you need to enter it in every time you push or pull.

## Copying the Public SSH Key

Next you need to copy the public key. This is system dependent.

MacOS:

`pbcopy < ~/.ssh/id_ed25519.pub`

Linux (`sudo apt install xclip` if you don't have the package):

`xclip -sel clip < ~/.ssh/id_ed25519.pub`

Windows:

`cat ~/.ssh/id_ed25519.pub | clip`

## Linking Key to Server

Log into your git sever account, e.g. GitHub. Go to settings and select the SSH settings. Paste the public key. To test, run the following command (assumes github, replace as necessary):

`ssh -T git@github.com`

And yes, it should be `git@` not `my_username@git`.
