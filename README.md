# Dotfiles
These are some config I use. I like to use the default configs most of the time so there is not a lot.

## Initial setup
```bash
# Save these lines wherever you save your aliases
alias dotgit='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
complete -F _complete_alias dotgit # Make bash-complete still work
```


## Creating a new dotfile repo
```bash
git init --bare $HOME/.dotfiles
dotgit config status.showUntrackedFiles no
# now you can add dotfiles, see examples
```

## Migrate to a new system
```bash
git clone --bare https://github.com/lhiguer1/dotfiles.git $HOME/.dotfiles/
dotgit config status.showUntrackedFiles no
dotgit checkout
```

## Examples
```bash
dotgit status
dotgit add .vimrc
dotgit commit -m "Add vimrc"
dotgit add .bashrc
dotgit commit -m "Add bashrc"
dotgit push
```

### Helpful links
[Archlinux wiki](https://wiki.archlinux.org/index.php/Dotfiles)  
[The best way to store your dotfiles: A bare Git repository](https://www.atlassian.com/git/tutorials/dotfiles)  
[complete-alias](https://github.com/cykerway/complete-alias)
