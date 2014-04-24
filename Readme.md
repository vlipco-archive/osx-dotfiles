Vlipco's dotfiles for Mac OS X 
================

This repository is intended to cloned as `.dotfiles` if your user's home. It contains shared dotfiles and conventions to help you keep your home in order with the help of [rcm](https://github.com/thoughtbot/rcm)

## What's included

* [Vlipco's fork of Yadr](https://github.com/Vlipco/yadr)
* A shared `.bin` [folder with utilities that the staff shares]()

## Requirements

Please make sure you have installed the following:

* Ruby & Rake.
* Homebrew.

Thoughtbot's rcm is of course required, you can install it with `brew tap thoughtbot/formulae && brew install rcm`

## Install


rcup -d Dotfiles rcrc
find . -maxdepth 1 -name ".*"
ls -dAl .*

WORKS:

SYMLINK_DIRS="*:*" rcup test

ls -dAl .* ; ls -Al .test/