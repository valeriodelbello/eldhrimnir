+++
title = "Git Personal Setup"
date = 2023-12-31
+++

Covers creating SSH and GPG keys, and creating a minimal Git configuration for personal use.
<!-- more -->


&nbsp;


Create SSH key:

```bash
ssh-keygen -t ed25519 -C ${EMAIL} -f ${HOME}/.ssh/git
```

When prompted, insert the passphrase.


&nbsp;


Add the private key to the agent to avoid continuously typing the passphrase:

```bash
eval "$(ssh-agent -s)"
ssh-add ${HOME}/.ssh/git-scm
```

When prompted, insert the passphrase.


&nbsp;


Create GPG key:

```bash
gpg --full-generate-key
```

Select the default kind (`RSA and RSA`), length (`3072`), and expiration (`0`).  
Insert comment `Git SCM`.  
Follow the prompts.  


&nbsp;


Get the GPG key ID:

```bash
gpg --list-secret-keys --keyid-format=long
```


&nbsp;


Configure Git:

```bash
git config --global user.name "Valerio Del Bello"
git config --global user.email "git@valeriodelbello.net"
git config --global user.signingkey 19BBC53ACDC0DC9
git config --global commit.gpgsign true
```


&nbsp;


Extract GPG keys for backup:

```bash
gpg --output git.public.pgp --armor --export git@valeriodelbello.net
gpg --output git.private.pgp --armor --export-secret-key git@valeriodelbello.net
```


&nbsp;


If on `git commit` you get

```text
error: gpg failed to sign the data
fatal: failed to write commit object
```

then set

```bash
export GPG_TTY=$(tty)
```