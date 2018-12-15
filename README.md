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

# Example using a .vimrc file
1. Create a git repo called dotfiles.  
  https://github.com/new

2. Go to your home directory and create a directory called dotfiles.
  `mkdir dotfiles`

3. Check to see if you have a `.vimrc` file in your home directory, if
  so make a quick backup for safetey.  
  `cd ~/`  
  `ls -la`  
  `cp .vimrc .vimrc_backup`  

3. (P2). If you did not have a `.vimrc` that's fine. It's just
  a configuration file for vim so you can make it. If you want you can pull
mine.  
  `cd dotfiles`  
  `git pull https://github.com/tschnide/dotfiles.git`  

4. Move your `.vimrc` file from your home directory to the dotfile
  directory. This step is only relevent if you already had one.  
  `mv .vimrc dotfile`  

5. Now create a symlink from your home directory to the dot file.  
  `ln -s dotfile/.vimrc .vimrc`  

6. Check.  
`cd ~/`  
You should now see a symlink like this `vimrc -> dotfiles/.vimrc` 
Open it and  you should see the same contents as the file
in the dotfile.  
  `vim .vimrc`  

* Now repeat the process beginning with step two for each computer that you
  want to configure.

* I tried to make this easy enough that anyone could follow along. When I first
  started there were cool things that I wanted to do but they were written to
an audience that had more experience. This was the case even for somthing as
conceptually simple as this. That said. I just wrote all of this ENTIRELY from memory
and I'm tired of working on it right now so it may not be perfect. If someone
stumbles on this, be sure to check commands etc.

# Sources
* The article I just shamelessly plagiarized: https://shinglyu.github.io/productivity/2016/03/12/dotfiles.html
* More info on symlinks: https://www.nixtutor.com/freebsd/understanding-symbolic-links/
