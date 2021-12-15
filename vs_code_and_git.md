# VS Code and Git

I use [Yury Zhauniarovich's blog](https://zhauniarovich.com/post/2020/2020-03-using-vscode-as-git-editor/) as reference. I modify his commands and remove the `--new-window` flag.

Set VS code as default editor:

`git config --global core.editor "code --wait"`

Check to make sure it's set and to add more settings:

`git config --global -e`

Where you can enter the settings below:

```text
[core]
    editor = code --wait
[merge]
    tool = vscode
[mergetool "vscode"]
    cmd = code --wait $MERGED
[diff]
    tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
```

## A Prettier Log

I like the pretty git log alias from [Coderwall](https://coderwall.com/p/euwpig/a-better-git-log)

`git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"`

## Other Aliases

`git config --global alias.stat "status -s"`

`git config --global alias.co "checkout"`
