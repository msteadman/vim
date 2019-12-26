# VIM Settings

Manage VIM settings in a useful, shareable way, using git submodules to take advantage of VIM 8's built-in package handling.

## Starting on a new system

```sh
git clone https://github.com/myk/vim.git .vim
ln -s .vim/vimrc .vimrc
```

## Packages

Adding a package:

```sh
git submodule add https://github.com/tpope/vim-fugitive.git pack/myk/start/vim-fugitive
```

Updating packages:

```sh
git submodule update --remote --merge
```

Removing a package:

```sh
git submodule deinit pack/myk/start/vim-fugitive
git rm pack/myk/start/vim-fugitive
rm -rf .git/modules/pack/myk/start/vim-fugitive
```

Remember to commit/push after any changes. Help tags for plugins aren't automatically generated, just run `:helptags ALL` in VIM to add them.
