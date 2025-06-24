+++
title = "Github SSH Key"
date = "2024-06-11"
description = "Setup Github SSH key"
[taxonomies]
tags = ["Key", "SSH", "Github", "Setup", "Generate"]
+++

## Generate key

Just replace your github email address in command:

```bash
ssh-keygen -t ed25519 -C "yourname@email.com"
```

It will prompt for password (as an extra layer of protection) 
you can skip by pressing [ENTER].

## Copy public key

```bash
cat ~/.ssh/id_ed25519.pub | xsel -b # copying content of public key
```
filename is ending with **.pub**, copy content of public key.


## Add to github
Github >> Profile >> Settings >> SSH and GPG Keys

[Goto this page](https://github.com/settings/keys)

Click **New SSH key**

Title: Any

Key Type: Authentication key

Key: *paste here*

Click **Add SSH key**

**DONE!**

Now try to clone your own repo with SSH..  
```bash
git clone git@github.com:YOURNAME/REPO.git
```