Vlipco's dotfiles for Mac OS X 
================

This repository is intended to cloned as `.dotfiles` if your user's home. It contains shared dotfiles and conventions to help you keep your home in order with the help of [rcm](https://github.com/thoughtbot/rcm).

Tested to work with Mavericks.

## What's included

* [Vlipco's fork of Yadr](https://github.com/Vlipco/yadr)
* A shared `.bin` [folder with utilities that the staff shares](https://github.com/Vlipco/osx-dotfiles/tree/master/bin)
* A pre-defined gitignore to allow you to use rcm with personal stuff like `.ssh` and [additional tags](https://github.com/Vlipco/osx-dotfiles/blob/master/rcrc) to those defined in `rcrc`.

## Requirements

Please make sure you have installed the following:

* Ruby & Rake.
* Homebrew.

## First steps

It is advisable to start with a home without dotfiles (move them to a temporary location) and add them back after the initial install.

To install run these from your terminal commands (uses ssh remote instead of https):

```
brew tap thoughtbot/formulae
brew install rcm
cd $HOME
git clone --recursive git@github.com:Vlipco/osx-dotfiles.git .dotfiles
rcup
cd .yadr
rake install
```

Restart your terminal to see yadr applied.

run `lsnorc` to find what dotfiles in your home aren't handled by rcm or linked elsewhere, this could be useful for you to know what other dotfiles could be useful in your .dotfiles, see usage section for examples.

By default rcm will use the tag `notrack` in all commands. That tag is use to handle dotfolders or files that you don't want to track in the repo or that don't make sense to have in the host specific dotfile (e.g. installed gems, heroku client, etc.)

## Usage

If you want to use stuff with tags differente to `notrack`, you can create `.dotfiles/extra-tags` and put there the space separated list of other tags that rcm should use by default.

You shouldn't put in notrack host specific stuff, like your `.ssh` folder. For that you can do something like `mkrc -o .ssh` that will put it in the `.dotfiles/host-[HOSTNAME]` folder (ignored by the repo for safety!). Ideally that folder would be tracked with some backup software that keep a safe and ciphrered copy elsewhere, github is not the right place for this kind of sensitive info.

To find how you could clean more your home's dotfiles (by moving folders to rcm's host rcfiles, notrack tag or your custom extra-tags) you can use `.bin/lsnorc` Here are some examples of how to track any of the listed results into rcm:

```
mkrc -o .ssh # move to host specific folder
mkrc -t notrack .rbenv # move to tag-notrack folder
```

At any given time you can `rcdn` to remove all links of anything listed in `lsrc` (handled by rcm). This will also let you see your home folder without the stuff handled by rcm in order to organize it before performing `rcup` again. If you kept a safe copy of all your dotfiles/folders prior to using this repo, this can be a great way to test how `rcup` behaves if you just copy paste the same `.dotfiles` folder to another machine aka. how you'd use a backup of your dotfiles

