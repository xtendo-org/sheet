## TL;DR

- Use pyenv.
- Use pyenv.
- Use pyenv.

## FAQ

- Q. Multiple versions of Python blah blah blah...
    - A. Use pyenv.
- Q. Shell and virtualenv blah blah blah...
    - A. Use pyenv.
- Q. virtualenv...
    - A. Use pyenv.
- Q. But...
    - A. Use pyenv.

Seriously, do me a favor and _use pyenv_.

- Q. I'm on Windows.
    - A. [Follow this instruction](https://wiki.archlinux.org/index.php/Installation_guide) and use pyenv.

## Install

```sh
git clone --depth=1 https://github.com/yyuu/pyenv.git ~/.pyenv
git clone --depth=1 https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
```

Configure your shell:

```bash
# bash
cat >> ~/.bash_profile <<END
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
END
exec bash
```

```fish
# fish
echo 'set -x PATH $HOME"/.pyenv/bin" $PATH' >> ~/.config/fish/config.fish
echo '. (pyenv init -|psub)' >> ~/.config/fish/config.fish
echo '. (pyenv virtualenv-init -|psub)' >> ~/.config/fish/config.fish
exec fish
```

## Usage

Install different versions of Python, safely, without interfering each other:

```sh
pyenv install 3.5.1
pyenv install 2.7.11
```

Create a virtualenv that uses the specified version of Python:

```sh
pyenv virutalenv 3.5.1 myproject
```

Activate virtualenv:

```sh
pyenv activate myproject
```

Deactivate:

```sh
pyenv deactivate
```

Delete virtualenv:

```sh
pyenv virtualenv-delete myproject
```
