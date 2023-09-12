# SSH signing

After cloning initialize the repository:

```sh
git config gpg.format ssh
git config gpg.ssh.allowedSignersFile allowed_signers
git config user.signingKey "$(ssh-add -L | head -n 1)"
git config commit.gpgsign true
```

Adding key to the file:

```sh
ssh-add -L | sed -e "s/^/$(git config user.email) /g" >> allowed_signers
```
