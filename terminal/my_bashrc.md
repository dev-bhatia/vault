```bash
# Stop default zsh message - OS Catalina
export BASH_SILENCE_DEPRECATION_WARNING=1

# Terminal Colors
export PS1="[ \[$(tput sgr0)\]\[\033[38;5;11m\]\w\[$(tput sgr0)\] ] \[$(tput sgr0)\]\[\033[38;5;10m\]>\[$(tput sgr0)\] \[$(tput sgr0)\]"

# don't put duplicate line in history. See bash(1) for more options
# ... or force ignoredups and ignorespace
export HISTCONTROL=ignoredups:ignorespace

# append to the history file, and don't overwrite it
shopt -s histappend

# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)
export HISTSIZE=50000
export HISTFILESIZE=50000

# Git completion with tab button
# See - https://github.com/bobthecow/git-flow-completion/wiki/Install-Bash-git-completion
[ -f /usr/local/etc/bash_completion ] && . /usr/local/etc/bash_completion || {
    # if not found in /usr/local/etc, try the brew --prefix location
    [ -f "$(brew --prefix)/etc/bash_completion.d/git-completion.bash" ] && \
        . $(brew --prefix)/etc/bash_completion.d/git-completion.bash
}

# Unzip TGZ files
alias tgz='tar -xvzf'

# Open files in Xcode
alias xcode='open -a /Applications/Xcode.app'

# Color for less command
export LESS='-R'
export LESSOPEN='|~/.lessfilter %s'

# Python
alias python="python3"
```