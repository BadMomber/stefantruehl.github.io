---
layout: post
title: Zsh is awesome!
feature-img: "assets/img/post-zsh/OhMyZsh-AgnosterTheme.png"
tags: [how-to, Linux]
---


Many Linux distributions bring along [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) as their standard shell. Thus, I have been using it for years. 
However, a couple of months ago I was made aware of [Z shell (Zsh)](http://www.zsh.org/) and have been using ever it since on a daily basis. In this time, I have come to love it and enjoy working with it. Thus, I want to outline some of my key findings and learnings in this post.  

![Zsh with Oh my Zsh extenstion and Agnoster theme]({{ site.baseurl }}/assets/img/post-zsh/OhMyZsh-AgnosterTheme.png)

## Zsh
Compared to Bash Zsh offers a wide variate of different advantages. Those that I have learned to appreciate most are the following:

#### Ease of Use
Zsh is much more powerful than Bash when it comes to tab completion. A simple but power example is the fact that it will tab complete names (e.g. folder or file names) case insensitively. Even further, it will even tab complete, in fact tab correct typos. 

Another great example for the awesome usability is the menu Zsh will give you if tab completion is not conclusive. In this menu you will be able to select the right item using cursor keys. 

#### Customizability 
Themes and Plugins


#### Install Zsh
Obviously, how to install Zsh is quite specific for you OS. During playing around with Zsh I have come across a nice [installation guide](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH) you may want to review.

If you want to make Zsh your default shell you only need to execute the following command:
> chsh -s /bin/zsh





### Prezto — "Instantly Awesome Zsh"
https://github.com/sorin-ionescu/prezto

#### Install Prezto

You will find a description on how to install Prezto on the project's [GitHub page](https://github.com/sorin-ionescu/prezto). I strongly suggest to stick to this how to. 

In my case it was rather simple as I had a vanilla installations of Zsh (running on my Fedora 27 installation). So I simply executed the following steps: 
  1. Launch Zsh:

     ```console
     zsh
     ```

  2. Clone the repository:

     ```console
     git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
     ```

  3. Create a new Zsh configuration by copying the Zsh configuration files
     provided:

     ```sh
     setopt EXTENDED_GLOB
     for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
       ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
     done
     ```

  4. Set Zsh as your default shell:

     ```console
     chsh -s /bin/zsh
     ```

  5. Open a new Zsh terminal window or tab.


#### Uninstall Pretzo 

  1. Remove all the related .z* files and directories in $HOME directory. Im my case these were the directories: 
  - .zprezto
  - .zcompcache

    and files: .zcompdump, .zcompdump.zwc, .zhistory, .zlogin, .zlogout, .zpreztorc, .zprofile, .zshenv, .zshrc. You might want to keep some of them, e.g. hold on to your history.

  2. Change your default shell back to Bash (adjust to your default shell)
     ```console
     chsh -s /bin/bash 
     ```
     


### Oh My Zsh - "Your terminal never felt this good before"
http://ohmyz.sh/



http://vincenzo-do.ch/?p=64



https://stackoverflow.com/questions/28491458/zsh-agnoster-theme-showing-machine-name

> ZSH_THEME="agnoster"
> DEFAULT_USER="$USER"

# Which plugins would you like to load? (plugins can be found in ~/.oh-my-zsh/plugins/*)
# Custom plugins may be added to ~/.oh-my-zsh/custom/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(
  git
  svn-fast-info
  docker
  sudo
)

