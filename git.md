# Git

## Git and VS Code

I like to use VS code as the editor for git. See notes [vs_code_and_git.md](./vs_code_and_git.md).

## Pretty Log

I like use a pretty formatted version of git log from [coderwall](https://coderwall.com/p/euwpig/a-better-git-log). The following command defines the alias `lg` for the pretty log:

`git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%ar) %C(bold blue)<%an>%Creset' --abbrev-commit"`

For example, if you want to see the lines that changed in the last commit:

`git lg -p -1`

## Git Ignore

A good resource for .gitignore content is github. For example, here are links to .gitignore content:

- [python](https://raw.githubusercontent.com/github/gitignore/master/Python.gitignore)
- [vscode](https://raw.githubusercontent.com/github/gitignore/master/Global/VisualStudioCode.gitignore)
- [macOS](https://raw.githubusercontent.com/github/gitignore/master/Global/macOS.gitignore)
- [windows](https://raw.githubusercontent.com/github/gitignore/master/Global/Windows.gitignore)
- [matlab](https://raw.githubusercontent.com/github/gitignore/master/Global/MATLAB.gitignore)
- [linux](https://raw.githubusercontent.com/github/gitignore/master/Global/Linux.gitignore)
- [C](https://raw.githubusercontent.com/github/gitignore/master/C.gitignore)
- [C++](https://raw.githubusercontent.com/github/gitignore/master/C%2B%2B.gitignore)

## View Git Configuration

Local overrides global (user) which overrides system.

`git config --system --list`

`git config --global --list`

`git config --local --list`

This command shows the inherited values from system, global and local:

`git config -l` or `git config --list`

This command displays the location of the configuration file for each configuration:

`git config --list --show-origin`

## Submodules

Get the submodule content when cloning a repo:

`git clone --recurse-submodules`

## Some Interesting Commands

Add all the files in the directory recursively:

`git add <directory>`

Condensed version of status. The left column is staged and the right column is unstaged. `M` is modified. `A` is new file added. `?` is untracked.

`git status --short` or `git status -s`
