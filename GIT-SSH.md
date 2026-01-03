## Get SSH setup (one way)
```
cd ~/.ssh
ssh-keygen -t ed25519 -C "user@email.com"

# copy id_ed25519.pub to github

# add this to your .bashrc
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# restart or rerun bashrc and enter your passphrase once
. ~/.bashrc
```

https://share.google/aimode/Xzfos62fpl14y5K0w

## Setup git
```
git config --global user.name username
git config --global user.email user@email.com

# passphrase for key will be asked once after agent
```

## Get repo setup
```
# New repo and name it express-ts for example
git clone git@github.com:sonjz/express-ts
```