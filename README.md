This is the backup of my shell configurations under `~/` on the csl-227-99 machine.

This repo is itself a folder under `~/`, with files hard-linked from actual configs under `~/`. In this way, all shell config changes will be automatically reflected in this repo, and could be conveniently committed.

To use it, either 1) clone this repo and create hard-links under `~/`, or 2) copy the config files to `~/`

## Cheatsheet
### Install Oh My Zsh and Setup Auto-Suggestions, Syntax Highlighting and Theme
To install Oh My Zsh, execute the following

```
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

For further configurations of Oh My Zsh, please

see https://itsfoss.com/zsh-ubuntu/#1-install-oh-my-zsh-on-ubuntu

### Zsh Sourcing Existing Bash Script During Shell Initiation (Already Added)
Suppose the script to source is `~/.shell_independent_rc`. Put the following at the end of `~/.zshrc`. Notice that if there is conda operations, e.g., conda environment activation in the `~/.shell_independent_rc`, you need to wait until conda is initiated: that is why it is recommended to add the following statement to the end of `~/.zshrc`

```
[[ -e ~/.shell_independent_rc ]] && emulate sh -c 'source ~/.shell_independent_rc'
```

### FISH Sourcing Existing Bash Script During Shell Initiation
"One hacky way to use your existing configuration while trying to transition to a new shell like fish is simply to end your ~/.bashrc with fish"

See https://stackoverflow.com/questions/70783183/can-fish-zsh-and-bash-import-the-same-configuration-file

see https://stackoverflow.com/questions/764600/how-can-you-export-your-bashrc-to-zshrc
### Change Shell
Execute

```
chsh -s $(which zsh)
```

and log out.

see https://askubuntu.com/questions/131823/how-to-make-zsh-the-default-shell
