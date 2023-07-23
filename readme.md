# Git Bash

**Step One**

-   get gitbash: download from [here](https://git-scm.com/downloads) install and open it
-   name: `git config --global user.name "Biswajit Biswas"`
-   email: `git config --global user.email "jfbiswajit@gmail.com"`
-   go to root directory: `cd ~`
-   create .ssh directory: `mkdir .ssh`
-   generate SSH Key: `ssh-keygen -t rsa -C "jfbiswajit@gmail.com"`
-   copy the SSH key from: `id_rsa.pub`

**Step Two**

-   go to your github account settings and click SSH and GPC keys
-   click `new SSH key` button
-   give it a title
-   paste the key that you copied from `id_rsa.pub` into the key input field.

**Testing**

-   connection: `ssh -T git@github.com` it will show your github user name (jfbiswajit)
-   config details: `git config --global --list` it will show you your all git config details

**SSH settings (Optinal)**

```
  Host github.com
  User jfbiswajit@gmail.com
  HostName ssh.github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_rsa
  Port 443
```

**Create Alias (.gitconfig)**

```bash
[user]
  name = Biswajit Biswas
  email = jfbiswajit@gmail.com

[alias]
  al = !git config --get-regexp ^alias\\. | sed -e s/^alias\\.// -e s/\\ /\\ =\\ /
  st = status
  rs = !git reset --hard && git clean -fd
  cm = !git add . && git commit -m
  gtc = reset --merge
  sw = switch
  lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
  pp = !git pull origin $(git branch --show-current) && git push origin $(git branch --show-current)
  br = branch
	amd = !git add . && git commit --amend --no-edit
  dep = !git add . && git commit -m "\"DEP: Deploy to the server\"" && git push origin HEAD

[core]
  editor = nano
[init]
  defaultBranch = master
```
