

rcup -d Dotfiles rcrc
find . -maxdepth 1 -name ".*"
ls -dAl .*

WORKS:

SYMLINK_DIRS="*:*" rcup test

ls -dAl .* ; ls -Al .test/