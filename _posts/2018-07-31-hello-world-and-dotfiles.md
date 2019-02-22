---
layout: post
title:  "Hello World! And dotfiles"
description: The first blog post, dotfiles and configurations
date:   2018-07-31 20:45:00 -0800
categories: jekyll update
---
Hello World! 

Welcome to my first and long overdue blog post. I've recently been dabbling in making my
terminal more aesthetic, which led me down a rabbithole of making everything else look just as nice too.
Here, I'll write a quick guide on how my current setup looks, in case anyone finds it useful, or if I
need to refer to it in the future (P.S. there's a super cool [bot][dotfiles-bot] which automates a ton
of this if you're setting up a new macOS machine).

## Customizing the terminal

![iTerm2]({{site.baseurl}}/assets/img/2018-07-31-hello-world-and-dotfiles/iterm2.png)
*The finished product*

First things first, install the terminal emulator [iTerm2][iTerm2-link] with the [solarized][solarized-link] theme. I haven't fully explored all the features of iTerm2 yet, but the fact that I can use `CMD + [0-9]` to cycle between tabs is already a huge upgrade.  

Next, add some colors to the command line for more visual cues between the different components. There are 
[tons][tons] [of][of] [guides][guides] [out][out] there on how to get nice colors, but I'll keep it quick and simple. Furthermore, many of the guides out there use themes for zsh, but I haven't found a compelling enough reason to switch shells besides the nice themes (...yet). Briefly, I use bash, and so all my changes will live in `.bash_profile`. You could also add these changes to `.bashrc`, which won't make much of a difference on macOS machines. The difference between the two is that the former is loaded for a login shell (default in macOS), whereas the latter is for non-login shells. See [here][shell-se] for more info.

Here's what my `.bash_profile` looks like:

{% highlight bash %}
###########################
# ENVIRONMENTAL VARIABLES #
###########################

# python 2.7
export PATH="/opt/local/Library/Frameworks/Python.framework/Versions/2.7/bin:${PATH}"

# postgreSQL
export PATH="/Library/PostgreSQL/10/bin/psql:$PATH"

# added by Anaconda2 5.2.0 installer
export PATH="/anaconda2/bin:$PATH"

# git autocomplete
test -f ~/.git-completion.bash && . $_

###################
# TERMINAL COLORS #
###################

# file/directory listing colors
export CLICOLOR=1

# Git branch in prompt.
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

# PS1 color
function prompt {
  local BLACK="\[\033[0;30m\]"
  local BLACKBOLD="\[\033[1;30m\]"
  local RED="\[\033[0;31m\]"
  local REDBOLD="\[\033[1;31m\]"
  local GREEN="\[\033[0;32m\]"
  local GREENBOLD="\[\033[1;32m\]"
  local YELLOW="\[\033[0;33m\]"
  local YELLOWBOLD="\[\033[1;33m\]"
  local BLUE="\[\033[0;34m\]"
  local BLUEBOLD="\[\033[1;34m\]"
  local PURPLE="\[\033[0;35m\]"
  local PURPLEBOLD="\[\033[10;95m\]"
  local MAGENTA="\[\033[1;35m\]"
  local CYAN="\[\033[0;36m\]"
  local CYANBOLD="\[\033[1;36m\]"
  local WHITE="\[\033[0;37m\]"
  local WHITEBOLD="\[\033[1;37m\]"
  local RESETCOLOR="\[\e[00m\]"

  export PS1="$PURPLEBOLD\h:\W \u$CYAN\$(parse_git_branch) $MAGENTA$ $GREEN"
}

prompt
{% endhighlight %}

It's heavily inspired by [this][dobson-dev-link] post. What I particularly like about this is the reusable local variables, in case I want to change my current color scheme. This can be done by changing the `PS1` variable, which is used to display information about the user, host, etc. and can be rewritten to include all or none of those. In my case, it corresponds to this line:

![ps1-custom]({{site.baseurl}}/assets/img/2018-07-31-hello-world-and-dotfiles/ps1-custom.png) 

## Customizing vim

I don't use vim too too much, but I often find it useful for editing files quickly, or if I need to edit a file in ssh, so I decided to add a theme for more visual cues. I won't go into details, since the process is already covered [here][set-up-vim-solarized-link], but briefly, you should install:

1. [Pathogen][pathogen-github] (a runtimepath manager for vim)
2. The [solarized][solarized-vim] theme for vim (obviously)

Both links above will guide you through the process of creating and editing your `.vimrc` and `~/.vim/bundle`. To get line numbers in vim, you just need to append `:set number` to your `.vimrc`. Here's what my `.vimrc` looks like:

{% highlight vim %}
" setup
execute pathogen#infect()
syntax on
filetype plugin indent on

" solarized
let g:solarized_termcolors=1
syntax enable
set background=dark
colorscheme solarized

" line numbers
:set number
{% endhighlight %}

And finally, the finished product in action:

![vim-shell-in-action]({{site.baseurl}}/assets/img/2018-07-31-hello-world-and-dotfiles/vim-shell-in-action.png)
*Side note: this simple script finds all the k-mers of length 9 in a file containing a single DNA string. Cool stuff.*

## Goodbye World

And we're finished! You can find all of my dotfiles on my [github][github]. I'll try to keep this updated with new features I find useful.

[github]: https://github.com/kevinxchan/dotfiles
[pathogen-github]: https://github.com/tpope/vim-pathogen
[solarized-vim]: https://github.com/altercation/vim-colors-solarized
[set-up-vim-solarized-link]: http://blog.likewise.org/2012/04/how-to-set-up-solarized-color-scheme/
[dobson-dev-link]: https://dobsondev.com/2014/02/21/customizing-your-terminal/
[shell-se]: https://apple.stackexchange.com/questions/51036/what-is-the-difference-between-bash-profile-and-bashrc
[out]: https://www.howtogeek.com/307701/how-to-customize-and-colorize-your-bash-prompt/
[guides]: http://tldp.org/HOWTO/Bash-Prompt-HOWTO/x329.html
[of]: https://misc.flogisoft.com/bash/tip_colors_and_formatting
[tons]: https://www.cyberciti.biz/faq/bash-shell-change-the-color-of-my-shell-prompt-under-linux-or-unix/
[solarized-link]: https://github.com/altercation/solarized/tree/master/iterm2-colors-solarized
[iTerm2-link]: https://www.iterm2.com/downloads.html
[dotfiles-bot]: https://github.com/atomantic/dotfiles
