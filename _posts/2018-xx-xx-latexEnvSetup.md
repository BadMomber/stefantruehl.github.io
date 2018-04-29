---
layout: post
title: LaTeX Environemnt Setup
feature-img: "assets/img/post-latexVSCode/VSCodeLatexScreenshot.png"
tags: [howto, latex]
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
If you are using Linux, it is very likely that you can install Tex Live though you standard package manager. I have checked the following distributions, and for them this seems to be true:
- Ubuntu: [link](https://packages.ubuntu.com/search?keywords=texlive)
- Fedora: [link](https://fedoraproject.org/wiki/Features/TeXLive)
    - I use it myself. Even though the link above only refers to a old version, a newer one is available in the Fedora repositories.
- Arch Linux [link](https://wiki.archlinux.org/index.php/TeX_Live)
However, according to a co-worker, some distributions ship very old versions of TeX Live. In this case it may be beneficial to install it manually. 

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
[Visual Studio Code](https://code.visualstudio.com/) is a light weight IDE developed by Microsoft that is [open source](https://github.com/Microsoft/vscode). It offers great ability to be extended with new functionality though a extension system. Still it remains easy to use and lean. 

Operating system specific installation guides can be found here: 
- [Linux](https://code.visualstudio.com/docs/setup/linux)
- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [MacOS](https://code.visualstudio.com/docs/setup/mac)

If you want to get familiar with VS Code, the following will give you an introduction on basic editing: [link](https://code.visualstudio.com/docs/editor/codebasics).



## Step 3: Install the VS Code extension: "LaTeX Workshop"
In order to be able to edit LaTeX with VS Code, you need to install an extension. The one I use and recommend is called [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop "LaTeX Workshop - Visual Studio Marketplace").

On all operating systems, it is installed by simply: 
1. launch VS Code Quick Open (ctrl/cmd + P)
2. paste the following command: "ext install James-Yu.latex-workshop"
3. hit enter
4. after the installation, it is most probably necessary to restart VS Code

At this point you are probably all set and can create LaTeX documents with your machine. However, if you want to verify that everything is set up properly, you may want to execute the following step es well. 


## Step 4: Verify everything is set up properly
In order to verify, that everything is set up properly, I recommend using the [research proposal template](https://github.com/stefantruehl/research-proposal-template) that I host on my GitHub account. 

#### Step 1: Clone the repo on to your local machine
Use the git client of your choosing to clone the repo locally.
Using the console client, the command is:
```sh
git clone git@github.com:stefantruehl/research-proposal-template.git
```
Optional: in order to be able to see later, if the pdf if properly generated, I recommend deleting the *researchproposal.pdf*-file at this point.

#### Step 2: Open the *researchproposal.tex*-file with VS Code
Follow these steps: 
1. Open VS Code
2. Open Folder ("File"->"Open Folder"), browse to the location where you cloned the repository and open the *research-proposal-template* folder. 
3. In the explorer section of VS Code's UI open the *researchproposal.tex*-file


#### Step 3: Setup necessary Workspace Build Settings for the Research Proposal
The research proposal has been set up the way that it requires [Biber](https://en.wikipedia.org/wiki/Biber_(LaTeX)) as bibliography information processing tool. Thus, it is necessary to adjust the build recipe that *LaTeX Workshop* uses to generate a pdf. 

In order to do that, follow these steps (screenshot below): 
1. Open the settings: "File"->"Preferences"->"Settings"
2. For the setting *latex-workshop.latex.recipes* add a workspace setting as listed below. 
3. For the setting *latex-workshop.latex.tools* add a workspace setting as listed below. 

The following is the full content of my workspace settings. 
````json
{
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex -> biber -> pdflatex*2",
            "tools": [
                "pdflatex",
                "biber",
                "pdflatex",
                "pdflatex"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "%DOC%"
            ]
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        },
        {
            "name": "biber",
            "command": "biber",
            "args": [
                "%DOCFILE%"
            ]
        }
    ]
}

````

![Screenshot of my Workspace settings]({{ site.baseurl }}/assets/img/post-latexVSCode/VSCodeWorkspaceConfiguration.png)

#### Step 4: Build pdf-file
Once you have added the workspace settings, return to the 

Choose the item "Build LaTeX project (Alt+Ctrl+B)" from the context menu. Now a pdf should be generated. 


#### Bonus Point: Open Preview on the Side
Personally, I use the preview on the side feature as it gives me the ability to see what to document I am editing in in (near) real-time. Screenshot below.

In order to open this, click the "Open Preview to the Side (Ctrl+K V)"-icon on the top right corner of the edit window that shows the *researchproposal.tex*-file.

![Screenshot of my Workspace settings]({{ site.baseurl }}/assets/img/post-latexVSCode/VSCodeLatexScreenshot.png)


