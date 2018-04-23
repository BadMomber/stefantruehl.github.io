---
layout: post
title: LaTeX Environemnt Setup
feature-img: "assets/img/sample_feature_img.png"
tags: [howto]
---



Very frequently, I am in contact with students that want to use LaTex for the creation of there academic papers or (bachelor or master) theses and struggle with the setup of a working LaTeX environment. Thus, I want to use this article to give an introduction to the LaTeX environment that I use personally. This article covers the setup of the following tool chain:
- **TeX Live** ([link](https://www.tug.org/texlive/ )) - very popular LaTeX distribution that brings along a huge number of LaTeX
- **Visual Studio Code** (aka VS Code - [link](https://code.visualstudio.com/)) - rather lightweight but very powerful IDE that brings great extendability for a vast variate of different languages. 
- **LaTex Workshop** ([link](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)) - extension for Visual Studio Code that aims to provide all-in-one features and utilities for LaTeX typesetting (list of features can be found [here](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop))

Please understand, if you have a running environment that makes sense to you - stick with it! It is by no means necessary to use the one poposed here, if you should be in one of my classes. Further, there are probably better environments out there. 

However, I personally find this setup highly usable and efficient. This is due to the points that:
1. it is available for all major operating systems
2. it is light weight
3. easy to use
4. it is fully open source
5. works for me...

If you want to give it a shoot, here is how to set it up:


## Step 1: Install TeX Live
The [project's website](https://www.tug.org/texlive/ "TeX Live Website") describes [TeX Live](https://en.wikipedia.org/wiki/TeX_Live "Wikipedia on TeX Live") as: "an easy way to get up and running with the TeX document production system. It provides a comprehensive TeX system with binaries for most flavors of Unix, including GNU/Linux, and also Windows. It includes all the major TeX-related programs, macro packages, and fonts that are free software, including support for many languages around the world."

It is available for all major operating systems. You will find how tos for installing it on your machine on the [project's website](https://www.tug.org/texlive/ "TeX Live Website").

Here is an overview of links to install tutorials per operating system:

#### Linux Setup
If you are using Linux, it is very likely that you can install Tex Live though you standard package manager. I have checked the following distirbutions, and for them this seems to be true:
- Ubuntu: [link](https://packages.ubuntu.com/search?keywords=texlive)
- Fedora: [link](https://fedoraproject.org/wiki/Features/TeXLive)
    - I use it myself. Even though the link above only refers to a old version, a newer one is available in the Fedora repositories.
- Arch Linux [link](https://wiki.archlinux.org/index.php/TeX_Live)

If Tex Live should not be available for your distribution, please review the following two links:
1. [download links](http://tug.org/texlive/acquire.html)
2. [installation guide](https://www.tug.org/texlive/quickinstall.html)


#### Windows Setup
If you are using Windows, you can simple install Tex Live by following the instructions given [here](https://www.tug.org/texlive/windows.html). The installation is really simple. It basically consists fo starting an installer and following though the installation. During the installation the installer will download all available packages and set them up on the system. 
I tested it out of curiosity and it worked perfectly on my Microsoft Windows 10 virtual machine. 


#### MacOS Setup
If you are running on MacOS it is recommended to use the [MacTex](https://www.tug.org/mactex/) redistribution of Tex Live as it includes Mac-specific utilities and front-ends. It is also pre-configured to work out-of-the-box with macOS as it provides sensible defaults for configuration options that, in TeX Live, are left up to the user to allow for its cross-platform compatibility [[wikipedia](https://en.wikipedia.org/wiki/MacTeX)].

An installation manual can be found: [here](http://www.tug.org/mactex/mactex-download.html). It seems to be very straight forward. 

(Please understand, I have never used MacOS and don't have/don't want access to a machine running it. Thus, I have not tested it :D)


#### Different Versions? Go Full! 

Depending on your operating system, TeX Live may be available in different versions, each bringing a different set of packages. I would recommend to go for a full installation, as this will prevent any trouble with missing packages later. 
As an example, for Fedora 27, the full installation package is called *texlive-scheme-full* and is available for installation from the standard repositories by using *dnf*. For Ubuntu the package's name seems to be *texlive-full* according to [this](https://packages.ubuntu.com/search?keywords=texlive). For Windows the installer will ask for the kind of installation it is supposed to do. 


## Step 2: Install Visual Studio Code


[Visual Studio Code](https://code.visualstudio.com/) is a light weight code IDE developed by Microsoft that is [open source](https://github.com/Microsoft/vscode) 

[Visual Studio Code](https://en.wikipedia.org/wiki/Visual_Studio_Code "Wikipedia on VSCode")

Installation guilds can be founs here: 
- [Linux](https://code.visualstudio.com/docs/setup/linux)
- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [MacOS](https://code.visualstudio.com/docs/setup/mac)





## Step 3: Install the VS Code extension "LaTeX Workshop"




## Step 4: Setup Tool Chain
3. Install the VS Code Extension called [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop "LaTeX Workshop - Visual Studio Marketplace")



Make sure you have a LaTeX distribution installed 
Install Visual Studio Code on your System https://code.visualstudio.com/

## Final Step: Basic Usage and make sure it works
