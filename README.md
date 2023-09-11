# .dotfiles

## First Time Setup

```bash
mkdir $HOME/.dotfiles
git init --bare $HOME/.dotfiles
```

Add this alias to the `.bashrc` or `.zshrc`.
`alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'`

Add a remote origin and set status to not show untracked files:

```bash
dotfiles config --local status.showUntrackedFiles no
dotfiles remote add origin git@github.com:Sheeplet1/.dotfiles.git
```

## Example Usage

```bash
cd $HOME
dotfiles add .tmux.conf
dotfiles commit -m "Add .tmux.conf"
dotfiles push
```

## Setting up a new machine

```bash
git clone --bare git@github.com:Sheeplet1/.dotfiles.git $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles checkout
-- might need to remove some files here to sync
dotfiles config --local status.showUntrackedFiles no
dotfiles config --global init.defaultBranch main
```
