# This contains my dotfiles consistent across machines
* Typically your dotfiles like .zprofile and .vimrc are in your home directory
  but I moved them to this directory instead.
* You could initialize a git repo in your home directory and then push just the
  files you want but that seems dangerous to privacy. Beyond that I'm trying to
make my life easy, not spend my time managing a .gitignore for my home
directory. ;)
* The solution is to put those files here and then create a symlink (shortcut)
  from my home directory to the file in this directory.

# Example using a .vimrc file
1. Go to your home directory and create a directory called dotfiles.
  `mkdir dotfiles`

2. Check to see if you have a `.vimrc` file in your home directory, if
  so make a quick backup for safetey.  
  `cd ~/`  
  `ls -la`  
  `cp .vimrc .vimrc_backup`  

2. (P2). If you did not have a `.vimrc` that's fine. It's just
  a configuration file for vim so you can make it. If you want you can pull
mine.  
  `cd dotfiles`
  `git clone https://github.com/tschnide/dotfiles.git`  

3. Move your `.vimrc` file from your home directory to the dotfile
  directory. This step is only relevent if you already had one.  
  `mv .vimrc dotfile`  

4. Now create a symlink from your home directory to the dot file.  
  `ln -s dotfile/.vimrc .vimrc`  

5. Check.  
  `cd ~/`  
You should now see a symlink like this: 
  `vimrc -> dotfiles/.vimrc` 
Open it and  you should see the same contents as the file
in the dotfile.  
  `vim .vimrc`  
  
6. Push to the repo you made by following the steps provided by GitHub.  

Ok. You're done. To link up another computer just create a dotfile as you did for the first computer, initialize a git repo and clone your dotfile repository. Don't forget to symlink it, and remove the backup that you made.


I tried to make this easy enough that anyone could follow along. When I first
gained an interest in computers there were cool things that I wanted to do but they were written to
an audience that had more experience. Sometimes this was the case even for something as
conceptually simple as this. That said. I just wrote all of this ENTIRELY from memory
and I'm tired of working on it right now so it may not be perfect. If someone
stumbles on this, be sure to check commands etc. Please request a pull if you see improvements that can be made. 

# Sources
* The article I just shamelessly plagiarized: https://shinglyu.github.io/productivity/2016/03/12/dotfiles.html
* More info on symlinks: https://www.nixtutor.com/freebsd/understanding-symbolic-links/
