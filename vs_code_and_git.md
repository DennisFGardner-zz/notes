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
