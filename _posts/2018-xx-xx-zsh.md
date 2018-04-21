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

Another great example for the awesome usability is the menu Zsh will give you if tab completion is not conclusive. In this menu you will be able to select the right item using cursor keys. Illustrated by the figure above. 

#### Customizability 
Zsh offers great ability to be customized and extended. There is a wide variate of different plugins available that make tab completion even more powerful, for example by introducing completion for application parameters. Illustrated by figure above.
Another awesome ability its theming. Zsh give great opportunity to be adjusted to your personal taste. The figure above illustrates the Agnoster theme, which comes along with Oh My Zsh. 


### Install Zsh
Obviously, how to install Zsh is quite specific for you OS. During playing around with Zsh I have come across a nice [installation guide](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH) you may want to review.

If you want to make Zsh your default shell you only need to execute the following command:
> chsh -s /bin/zsh


Even though Zsh offers great extensibility and customizability, I don't want to spend the time of doing it myself, instead I use available resources that are available. 
So far I have tested two configuration framework for Zsh **Prezto** and **Oh My Zsh**. The following is a brief introduction.


## Prezto — "Instantly Awesome Zsh"
[Prezto](https://github.com/sorin-ionescu/prezto) is a nice configuration framework for Zsh. It enriches the shell with a variety of different defaults, aliases, functions, auto completion, and prompt themes.

I have used it for some time and enjoyed it. You may want to give it a shot and try it out. 


### Install Prezto

You will find a description on how to install Prezto on the project's [GitHub page](https://github.com/sorin-ionescu/prezto). I strongly suggest to stick to this how to. 

In my case it was rather simple as I had a vanilla installations of Zsh (running on my Fedora 27 installation). So I simply executed the following steps: 
  1. Launch Zsh:

     ```sh
     zsh
     ```

  2. Clone the repository:

     ```sh
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

     ```sh
     chsh -s /bin/zsh
     ```

  5. Open a new Zsh terminal window or tab.


### Uninstall Pretzo 
At some point I wanted to change to another configuration framework. Thus, I had to uninstall Pretzo. This is what I did to do so. 

  1. Remove all the related .z* files and directories in $HOME directory. Im my case these were the directories: 
  - .zprezto
  - .zcompcache

    and files: .zcompdump, .zcompdump.zwc, .zhistory, .zlogin, .zlogout, .zpreztorc, .zprofile, .zshenv, .zshrc. You might want to keep some of them, e.g. hold on to your history.

  2. Change your default shell back to Bash (adjust to your default shell)
     ```sh
     chsh -s /bin/bash 
     ```
     


## Oh My Zsh - "Your terminal never felt this good before"
[Oh My Zsh](http://ohmyz.sh/) is the configuration framework that I am currently using. According to the project's website, they offer more than 200 plugins and more than 120 themes. For more infos review the following:
- [Overview of themes](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)
- [Overview of plugins](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins-Overview)


### Install Installing Oh My Zsh 
Instructions on how to install Oh My Zsh can be found on the [GitHub page of the project](https://github.com/robbyrussell/oh-my-zsh). 
I chose the installation via curl which is a single command:
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```


### My current Configurations
The following are some configurations that I made.

#### Plugins 
Activating plugins is quite easy. You only need to edit the *.zshrc* configuration file and add the plugins' names at the right spot. 
I am still in the trying-out phase. At the moment those are the ones I am using (snipet from .zshrc): 
```sh
plugins=(
  git
  svn-fast-info
  docker
  sudo
  dnf
)
```
Well, from the names it should be obvious what the plugins are about, *git* adds awesome support for git, etc. 
However, there is one that I want to point out specifically: **sudo**. This plugin adds *sudo* in front of a console line once you hit the escape key twice. This is awesome because is significantly increases productivity. 

#### Theme
After browsing the available themes for some time I chose **agnoster** as my favorit theme. 

##### Step 1: Adjust .zshrc

Using it can simply be done by changing the chosen theme in the *.zshrc* configuration file in the following way: 
```sh
ZSH_THEME="agnoster"
```

##### Step 2: Install Powerline Fonts
The Agnoster theme relies on the [Powerline Fonts](https://github.com/powerline/fonts). They need to be installed on your system. 

In my case, using Fedora I installed in the following way: 
```sh
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

##### Step 3: Make your Terminal Emulator use a Powerline Font
After installation, you need to make your terminal emulator use a powerline font. I use [Terminator](https://launchpad.net/terminator) as terminal emulator. If you too, open the preference menu (right-click -> Preferences). Under Profiles you should find the General tab with the possibility to change the font. 

![Choose powerline font in your terminal window]({{ site.baseurl }}/assets/img/post-zsh/AgnosterTheme-ChooseFont.png)



##### Step 4: Get rid of *UserName@MachineName
At this point I still had **sruehl@stefansX1C6** in front of the command prompt. In order to get rid of it, I added the following line to the *.zshrc* configuration file:

```sh
DEFAULT_USER="$USER"
```