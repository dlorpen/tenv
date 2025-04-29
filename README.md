# TENV

This script adds some functionality to the excellent [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect).

tmux-resurrect has one flaw, and that is that saving and loading of sessions is kind of annoying. You can save and load the last session relatively easily, but if say you want a custom tmux setup for each of your projects, it's a pain to setup. You have to find the directory where tmux-resurrect sessions are stored, and symlink the one you want to the 'last' symlink in the same directory.

`tenv` solves this problem.

## Installation

curl the script and put it somewhere logical like `~/.local/bin`. You may need to `chmod +x` it too.

```bash
	curl 'https://raw.githubusercontent.com/dlorpen/tenv/refs/heads/main/tenv' -o tenv
	chmod +x tenv
	mv tenv ~/.local/bin/
```

You'll need to have [TPM](https://github.com/tmux-plugins/tpm) and [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect) installed too.

## Usage

Run `tmux`
Set up the session as you want it and hit `prefix Ctrl s` to save it
Run `tenv` in your project root directory to copy the latest setup into a `.tenv` file.

Next time you want to load the same configuration, run `tmux` and run `tenv` in your project root dir.
Then hit `prefix Ctrl r` to reload the tmux config using tmux-resurrect.

I suspect you don't wanna commit the .tenv file - my guess is that it's specific to you so if you commit it then everyone gets your tenv setup which sounds... suboptimal.

If you ever want to change the saved config, delete the .tenv file from your project root, save the config again with tmux-resurrect, and run tenv again to copy the new config in.
