dotfiles-template
=================

Use this repository as a template for your own personal "dotfiles" repository, if you don't already have one.  If you do, you can reference the files and file structure to make your existing dotfiles repository work with the Daptiv Strap scripts.

## Important Files
*Brewfile*
Strap will look for a Brewfile in the root of your dotfiles repository.  If it finds it, it will symlink it to your personal root folder, and then install all Brew packages and casks referenced in it.

*script/postbrew*
Strap will look for this file in `script/postbrew`, and it will run it as the very last step of the Strap process.


