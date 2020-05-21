# VIM Settings

Manage VIM settings in a useful, shareable way, using git submodules to take advantage of VIM 8's built-in package handling.

## Starting on a new system

In the home directory clone the repo as `.vim` and run `ln -s .vim/vimrc .vimrc` to set things up. Initialize the submodules by running:

```sh
git submodule init
git submodule update --remote --merge
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

Remember to commit/push after any changes. Help tags for plugins aren't automatically generated, just run `:helptags ALL` in VIM to add them. For packages that don't need to be automatically loaded, put them in `pack/myk/opt` and activate them in VIM with `:packadd packagename`.

## Keeping in Sync

On other systems where you just want to keep in sync but aren't doing any package management:

```sh
git pull
git submodule update --merge
```
