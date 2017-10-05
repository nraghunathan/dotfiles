dotfiles-template
=================

Use this repository as a template for your own personal "dotfiles" repository, if you don't already have one.  If you do, you can reference the files and file structure to make your existing dotfiles repository work with the Daptiv Strap scripts.

# Instructions
* Clone this repository in order to get a copy of it locally.
* If you don't have a dotfiles repository already, then:
*  Create repository in your github account named `dotfiles`, but don't clone it.
*  Now, run these commands:

```bash
git clone https://github.com/daptiv/dotfiles-template.git ~/src/dotfiles
cd ~/src/dotfiles
git remote remove origin
git remote add origin git@github.com:{your-github-username}/dotfiles.git
git add -f *
git commit -a -m "Initial commit"
git push -u origin HEAD
```

Note: When you are done strapping your Mac, you will have your personal dotfiles repository cloned twice to your mac.  Once in `~/src/dotfiles` and once in `~/.dotfiles`.  To avoid this situation, either remove the `~/src/dotfiles` folder, or symlink it to the root folder (`ln -s $HOME/src/dotfiles $HOME/.dotfiles`).  You can always edit and push updates from either folder.  The choice is yours.

## Important Files
`.Brewfile`

Strap will look for a `.Brewfile` in the root of your dotfiles repository (`~/.dotfiles/.Brewfile`).  If it finds it, it will symlink it to your personal root folder, and then install all Brew packages and casks referenced in it.

`script/setup`

Strap will call this script, if it exists, to perform personalized setup steps.  You can use it configure the projects and virtual machines installed on your Mac, call out from here to other scripts, other repos, etc.

`script/postbrew`

Strap will look for this file in `script/postbrew`, and it will run it as the very last step of the Strap process.

`.bash_profile`

This is your personal bash profile.  The daptiv `.bash_profile` file will source your personal `.bash_profile` file, if it exists in `~/.dotfiles/.bash_profile`

`.gitconfig`

This is your personal .gitconfig file.  Strap will symlink this to your home folder.
