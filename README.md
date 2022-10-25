# dotfiles

Dotfile syncing/backup.

Intended to be used with the following organization:

Repository tracked in $HOME/.cfg/. Worktree is simply $HOME.

Setting up these dotfiles in a new system:

```shell
echo ".cfg" >> .gitignore #cfg shouldn't track itself
git clone --bare git@github.com:danielfrees/dotfiles.git $HOME/.cfg  #--bare is fine if desired, change url if not using ssh
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'  #this will auto apply in the future once .zshrc is synced
config config --local status.showUntrackedFiles no  #DONT TRACK YOUR ENTIRE FILESYSTEM LOL
config checkout   #If you get errors, backup and delete conflicting file names as necessary until no errors
```
