# My personal dotfiles

This is just a little collection of things I found usefull in my
daily bash work.

The .bash_profile is based on http://natelandau.com/my-mac-osx-bash_profile/
I added some more aliases and removed parts that are not usefull to me.

Addtionally I added liquidprompt as git submodule.

# Installation notes

There is no automatic installation, yet!

1. Clone the repository to your home folder
2. Do git submodule init && git submodule update
2. Create symbolic link from local .bash_profile to ~/.bash_profile
4. Create symbolic link from local .config to ~/.config

# Warning

Do not use the .bash_profile in non interactive shells and shell scripts, because it aliases
some of the default built in tools like cd.

# Additional Notes

This explanation is taken from [Stackoverflow](http://stackoverflow.com/questions/415403/whats-the-difference-between-bashrc-bash-profile-and-environment)

The main difference with shell config files is that some are only read by "login" shells (eg. when you login from another host, or login at the text console of a local unix machine). these are the ones called, say, .login or .profile or .zlogin (depending on which shell you're using).

Then you have config files that are read by "interactive" shells (as in, ones connected to a terminal (or pseudo-terminal in the case of, say, a terminal emulator running under a windowing system). these are the ones with names like .bashrc, .tcshrc, .zshrc, etc.

bash complicates this in that .bashrc is only read by a shell that's both interactive and non-login, so you'll find most people end up telling their .bash_profile to also read .bashrc with something like

[[ -r ~/.bashrc ]] && . ~/.bashrc

Other shells behave differently - eg with zsh, .zshrc is always read for an interactive shell, whether it's a login one or not.

The manual page for bash explains the circumstances under which each file is read. Yes, behaviour is generally consistent between machines.

.profile is simply the login script filename originally used by /bin/sh. bash, being generally backwards-compatible with /bin/sh, will read .profile if one exists
