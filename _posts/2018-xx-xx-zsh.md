---
layout: post
title: Zsh is awesome!
feature-img: "assets/img/sample_feature_img.png"
tags: [test, sample]
---

some general introductive words

### Zsh

#### Install Zsh
Obviously, howto install Zsh is quite specific for you OS. During playing around with Zsh I have come across a nice [installation guide](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH) you may want to review.


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

    and files: .zcompdump, .zcompdump.zwc, .zhistory, .zlogin, .zlogout, .zpreztorc, .zprofile, .zshenv, .zshrc. You might want to keep some of them, e.g. got hold on to your history.

  2. Change your default shell back to Bash (adjust to your default shell)
     ```console
     chsh -s /bin/bash 
     ```
     


### Oh My Zsh - "Your terminal never felt this good before"
http://ohmyz.sh/

