# pyenv

I prefer using pyenv to manage multiple python installations. I good resource on pyenv is [Real Python](https://realpython.com/intro-to-pyenv/).

Integration with MacOS and Linux systems is supported by pyenv. To integrate with windows, which I have done, use [pyenv-win](https://github.com/pyenv-win/pyenv-win). When I used pyenv-win, I installed by following the Github readme. I installed pyenv-win from a cloned pyenv-win repo.

## pyenv install on Ubuntu

The versions of python are built from source. To build python, the following dependencies are recommended on [pyenv's website](https://github.com/pyenv/pyenv/wiki#suggested-build-environment):

`sudo apt update`

`sudo apt install --no-install-recommends make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev`

To install pyenv, I use [pyenv-installer](https://github.com/pyenv/pyenv-installer). The following dependencies are needed to install pyenv, there is a lot, with almost total overlap with the python build dependencies:

`sudo apt install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl git`

After dependency installation, install pyenv with:

`curl https://pyenv.run | bash`

After installation, the following needs to be added to `~/.bashrc`:

```text
# Load pyenv automatically
export PATH="/home/dennis/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

The shell needs to be restarted for path changes to take effect:

`exec $SHELL`

## Install python versions with pyenv

To see a list of local python versions (* indicates active version):

`pyenv versions`

The system version is the python version that was installed by the OS.

There are a lot of python versions available. You can use grep to trim down the list, for example:

`pyenv install --list | grep " 3\.[5]"`

To install a python version (replace version as desired):

`pyenv install 3.5.10`

## Activating python versions

You can set the global version with this command:

`pyenv global 3.9.4`

The global version is overridden by the local version (useful to run this command in the directory of the application):

`pyenv local 3.8.9`

And finally, you can override the local version in a shell with:

`pyenv shell 3.8-dev`

## pyenv and virtual environments

The installer I used to install pyenv also installs pyenv-virtualenv. However, I don't use virtualenv and instead use `venv`.
