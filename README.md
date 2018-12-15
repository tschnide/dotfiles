# This contains my dotfiles so I can keep them consistent across all of the
computers that I insist on using.
* Typically your dotfiles like .zprofile and .vimrc are in your home directory
  but I moved them to this directory instead.
* You could initialize a git repo in your home directory and then push just the
  files you want but that seems dangerous to privacy. Beyond that I'm trying to
make my life easy, not spend my time managing a .gitignore for my home
directory. ;)
* The solution is to put those files here and then create a symlink (shortcut)
  from my home directory to the file in this directory.

# Example
* The article I just shamelessly plagiarized: https://shinglyu.github.io/productivity/2016/03/12/dotfiles.html
