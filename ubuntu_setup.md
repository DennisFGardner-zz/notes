# Ubuntu Setup

## oh my zsh

I like to use [oh my zsh](https://github.com/ohmyzsh/ohmyzsh/tree/48a3c2f32d1a4643db367eed4d6c53768c3847b1) as my shell. If zsh is not installed (you can check with `zsh --version`) then install zsh with:

`sudo apt install zsh`

Install oh my zsh with:

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

I add the following to `~/.zshrc`:

```text
# I like the output to remain in the terminal
unset LESS;
```

To make zsh the default shell:

`chsh -s $(which zsh)`

Then log out and log back in.

## Command Line Utilities

- `sudo apt install xclip`
- `sudo apt install tree`
