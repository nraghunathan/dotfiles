dotfiles-template
=================

Use this repository as a template for your own personal "dotfiles" repository, if you don't already have one.  If you do, you can reference the files and file structure to make your existing dotfiles repository work with the Daptiv Strap scripts.

# Instructions
* Clone this repository in order to get a copy of it locally.
* If you don't have a dotfiles repository already, run this:
    
```bash
git clone https://github.com/daptiv/dotfiles-template.git ~/src/dotfiles
cd ~/src/dotfiles
git remote remove origin
git remote add origin git@github.com:{your-github-username}/dotfiles.git
git add -f *
git commit -a -m "Initial commit"
git push -u origin HEAD
```


## Important Files
`Brewfile`

Strap will look for a Brewfile in the root of your dotfiles repository.  If it finds it, it will symlink it to your personal root folder, and then install all Brew packages and casks referenced in it.

`script/postbrew`

Strap will look for this file in `script/postbrew`, and it will run it as the very last step of the Strap process.

`.bash_profile`

This is your personal bash profile.  Strap will symlink this to your home folder.

`.gitconfig`

This is your personal .gitconfig file.  Strap will symlink this to your home folder.
