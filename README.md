This is the backup of my shell configurations under `~/` on the csl-227-99 machine.

This repo is itself a folder under `~/`, with files hard-linked from actual configs under `~/`. In this way, all shell config changes will be automatically reflected in this repo, and could be conveniently committed.

To use it, either 1) clone this repo and create hard-links under `~/`, or 2) copy the config files to `~/`

## Cheatsheet
### Zsh Sourcing Existing Bash Script During Shell Initiation (Already Added)
Suppose the script to source is `~/.shell_independent_rc`. Put the following at the end of `~/.zshrc`. Notice that if there is conda operations, e.g., conda environment activation in the `~/.shell_independent_rc`, you need to wait until conda is initiated: that is why it is recommended to add the following statement to the end of `~/.zshrc`

```
[[ -e ~/.shell_independent_rc ]] && emulate sh -c 'source ~/.shell_independent_rc'
```


see https://stackoverflow.com/questions/764600/how-can-you-export-your-bashrc-to-zshrc
### Change Shell
Execute

```
chsh -s $(which zsh)
```

and log out.

see https://askubuntu.com/questions/131823/how-to-make-zsh-the-default-shell
