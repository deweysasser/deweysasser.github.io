---
categories:
- git
title: Resetting a git-crypt system
slug: resetting git-crypt system 
created: 1589315846
toc: true  
---
# The Problem

[git-crypt](https://github.com/AGWA/git-crypt) is pretty awesome, but I've managed to do enough evil things to bork 
the decryption keys.  Here's how to fix it.

<!--break-->

# The Background

[git-crypt](https://github.com/AGWA/git-crypt) allows you to encrypt some of the files in a git repository.  It supports adding other users' GPG keys so they will be able to encrypt/decrypt the file.  It's pretty clever, and I like it.

The basic operation is that it creates a single symmetric key (which it stores in `.git/git-crypt/keys/default`), then
on request will use GPG to encrypt that key to the public key IDs you specify, and those are stored in `.git-crypt//keys/default/0`.

However, if you do sufficiently evil things in git repos, like using [git filter-repo](https://github.com/newren/git-filter-repo) (another pretty awesome tool), it's possible to drive `git crypt` into a pathological state where your keys are wrong and you can't do anything.

In order to recover from this situation, make sure you have unencrypted copies of the files around somewhere, then:

# The Fix
* create a fresh clone of your repo.  In that clone, do...
*  save the IDs of all keys

```bash
keys=$(ls .git-crypt/keys/default/0/*.gpg | xargs -n 1 -I F basename F .gpg)
```

* Remove the existing encrypted keys

```bash
git rm -r .git-crypt
rm -rf .git/git-crypt
```

* Reinitialize the encryption

`git crypt init`

* Re-add the public keys which should access the encrypted files

```bash
for k in $keys; do git crypt add-gpg user $k; done
```

* COPY in fresh, unencrypted copies of all previously encrypted files, however you do that

* (Optional) rebase so that all of this stuff occurs in a single commit

```bash
git rebase -i origin/master
```
Note that the VI magic to "fixup" all commits into the first one is `2,$ s/pick/fixup/`

