```
git init --bare $HOME/.dotfiles
alias dot='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dot config status.showUntrackedFiles no
```
https://news.ycombinator.com/item?id=11070797

For posterity, note that this will fail if your home directory isn't empty. To get around that, clone the repo's working directory into a temporary directory first and then delete that directory,
```
git clone --separate-git-dir=$HOME/.dotfiles /path/to/repo $HOME/dotfiles-tmp
cp ~/dotfiles-tmp/.gitmodules ~  # If you use Git submodules
rm -r ~/dotfiles-tmp/
```

https://developer.atlassian.com/blog/2016/02/best-way-to-store-dotfiles-git-bare-repo/
