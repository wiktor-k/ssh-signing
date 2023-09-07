# SSH signing

```sh
git config gpg.format ssh
git config gpg.ssh.allowedSignersFile allowed_signers
git config user.signingKey "$(ssh-add -L)"
git config commit.sign true
```
