
:warning: _**This project has been superseded by
[pedrohdz/dotfiles-vim](https://github.com/pedrohdz/dotfiles-vim).**_ :warning:

dr-vimfiles-python
==================

## Overview 

Pedro's Node.JS vimfiles for use with homeshick.

Contains vim plugins that require Node.js to be installed.


### Requirements

  - [Homeshick][]
  - [dr-vimfiles][]
  - [npm][]
  - [Node.js][]


### Features

  - [vim-instant-markdown][] - Want to instantly preview finnicky markdown
    files, but don't want to leave your favorite editor, or have to do it in
    some crappy browser textarea? vim-instant-markdown is your friend!


## Installation

The following assumes you want to install the _node.js_ componants in
`~/.local/`, and not in `~/node_modules/`.


### Shell configuration

Create `~/.local/bin`:

  ```bash
  $ mkdir -p ~/.local/bin
  ```

Create/update `~/.npmrc` so that it contains:

  ```
  prefix = ${HOME}/.local
  ```
Append the following to `~/.profile`:

  ```bash
  # local user bin
  export USER_LOCAL="$HOME/.local"
  if [ -d "$USER_LOCAL" ]; then
      if [ -d "$USER_LOCAL/bin" ]; then
          export PATH="$USER_LOCAL/bin:$PATH"
      fi

      if [ -d "$USER_LOCAL/share/man" ]; then
          export MANPATH="$USER_LOCAL/share/man:$MANPATH"
      fi
  fi
  ```

Restart your termiminal session(s) and confirm that the path has been updated.


### MacPorts installation

Then install:

  ```bash
  $ sudo port install nodejs npm
  $ npm -g install instant-markdown-d
  $ homeshick clone git@github.com:digitalrounin/dr-vimfiles-nodejs.git
  ```

The `-g` in `npm install` installs it in `~/.local/`.


[dr-vimfiles]: https://github.com/digitalrounin/dr-vimfiles
[Node.js]: https://nodejs.org/
[npm]: https://www.npmjs.com/
[homeshick]: https://github.com/andsens/homeshick
[vim-instant-markdown]: https://github.com/suan/vim-instant-markdown
