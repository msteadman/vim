# Vim Settings

Manage Vim settings so they can be synced between machines.

## Starting on a new system

In the home directory clone the repo as `.vim` and run `ln -s .vim/vimrc .vimrc` to set things up. Initialize the submodules by running:

```sh
git submodule init
git submodule update
```

## Package Management

Using Vim 8's native package support, and `git submodule` for syncing. References:

* [Vim: So long Pathogen, hello native package loading](https://shapeshed.com/vim-packages/)
* [Using Vim packages](https://vimhelp.org/repeat.txt.html#packages)

Adding a package:

```sh
git submodule add https://github.com/tpope/vim-fugitive.git pack/myk/start/vim-fugitive
```

Updating packages:

If you're pulling updates, run:

```sh
git submodule update --init --remote
```
Or if you're just keeping in sync after a `git pull`, run:

```sh
git submodule update --init
```

Removing a package:

```sh
git submodule deinit pack/myk/start/vim-fugitive
git rm pack/myk/start/vim-fugitive
rm -rf .git/modules/pack/myk/start/vim-fugitive
```

Remember to commit/push after any changes. Help tags for plugins aren't automatically generated, just run `:helptags ALL` to add them. For packages that don't need to be automatically loaded, put them in `pack/myk/opt` and activate them with `:packadd packagename`.

## Keeping in Sync

On other systems where you just want to keep in sync but aren't doing any package management:

```sh
git pull
git submodule update --init
```
