# SSH signing

After cloning initialize the repository:

```sh
git config gpg.format ssh
git config gpg.ssh.allowedSignersFile allowed_signers.md
git config user.signingKey "key::$(ssh-add -L | head -n 1)"
git config commit.gpgsign true
```

Adding key to the file:

```sh
ssh-add -L | sed -e "s/^/$(git config user.email) /g" >> allowed_signers
```

Other config variables you may want to enable:

```sh
# show signatures by default when doing "git log"
git config log.showSignature true

# verify signatures on "git pull"
git config merge.verifySignatures true
```
