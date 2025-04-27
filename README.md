# TENV

This script adds some functionality to the excellent [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect).

tmux-resurrect has one flaw, and that is that saving and loading of sessions is kind of annoying. You can save and load the last session relatively easily, but if say you want a custom tmux setup for each of your projects, it's a pain to setup. You have to find the directory where tmux-resurrect sessions are stored, and symlink the one you want to the 'last' symlink in the same directory.

`tenv` solves this problem.

## Installation

curl the script and put it somewhere logical like `~/.local/bin`. You may need to `chmod +x` it too.

You'll need to have TPM and [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect) installed too.

## Usage

Save the tmux session for your project using tmux-resurrect. Then go to your project root dir and run tenv. It will create a .tenv file in your project directory. Next time you want to work on your project, run tenv, then load tmux and hit <Prefix> Ctrl-r to reload the session. Probably better to not commit your .tenv file to source control unless you work alone.
