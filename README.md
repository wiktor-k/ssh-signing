# SSH signing

After cloning initialize the repository:

```sh
git config gpg.format ssh
git config gpg.ssh.allowedSignersFile allowed_signers
git config user.signingKey "$(ssh-add -L)"
git config commit.sign true
```

Adding key to the file (this won't work if you have multiple unlocked
keys):

```sh
echo "$(git config user.email) $(ssh-add -L)" >> allowed_signers
```
