# GitHub

### New Repository Setup

Create a new repository on the command line  
```
echo "# dash" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/mufasa159/dash.git
git push -u origin main
```

Push an existing repository from the command line
```
git remote add origin https://github.com/mufasa159/dash.git
git branch -M main
git push -u origin main
```

### Other

Remove files that was mistakenly added but not yet committed
```
git restore --staged <filename>
```

Undo last git commit
```
git reset --soft HEAD~1
```

Delete a branch
```
git branch -d <branch-name>
```

Rename a branch
```
git branch -M <branch-name>
```

### Signing Commits

```
ssh-keygen -t ed25519 -C "<email-address-connected-to-github>"
```
```
eval "$(ssh-agent -s)"
```
Check if file exists:
```
open ~/.ssh/config
```
If not,
```
touch ~/.ssh/config
```
Open the file
```
nano ~/.ssh/config
```
Then paste the following
```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```
Type `ctrl` + `o` to save. `ctrl` + `x` to exit nano.  

Add key to keychain on macos
```
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```
Copy SSH key to clipboard
```
pbcopy < ~/.ssh/id_ed25519.pub
```
Create a new SSH key in GitHub and paste it there.

Back to terminal and run
```
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
```
To sign all commits by default, run
```
git config --global commit.gpgsign true
```
Or, specify in each commit like following
```
git commit -S -m"your-commit-message"
```

### Troubleshooting

When running this:
```bash
git log --show-signature
```
Do you see this?
```bash
error: gpg.ssh.allowedSignersFile needs to be configured and exist for ssh signature verification
...
No signature
```
If so, do this:
```bash
touch ~/.ssh/allowed_signers
echo "$(git config --get user.email) namespaces=\"git\" $(cat ~/.ssh/id_ed25519.pub)" >> ~/.ssh/allowed_signers
git config --global gpg.ssh.allowedSignersFile ~/.ssh/allowed_signers
```


More details:  
[Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)  
[Telling Git about your signing key](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)  
[Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)  
