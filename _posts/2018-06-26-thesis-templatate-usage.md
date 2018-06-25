---
layout: post
title: Thesis Template in Visual Studio Code
feature-img: "assets/img/post-thesis-template-VSCode/ThesisTeplate-VSCode.png"
tags: [how-to, latex]
---

At our [CS department](https://www.fbi.h-da.de/fbi.html) at [University of Applied Sciences Darmstadt](https://h-da.de/) we recommend a specific LaTeX template to your students, for the creation of Bachelor's and Master's theses. This template can be found [here](https://github.com/mbredel/thesis-template).

In this article I want do describe how to work with the thesis template in the Latex environnement that I proposed in my previous [article](https://stefantruehl.github.io/2018/04/30/latexEnvSetup.html).


## Introduction 
In a previous post I have described how to setup a LaTeX environment based on the following tool stack: 
- **TeX Live** ([link](https://www.tug.org/texlive/ ) - version installed on my machine: TeX Live 2016) - very popular LaTeX distribution that brings along a huge number of packages.
- **Visual Studio Code** (aka VS Code - [link](https://code.visualstudio.com/) - version installed on my machine: 1.22.2) - rather lightweight but very powerful IDE that brings great extendability for a vast variate of different languages. 
- **LaTeX Workshop** ([link](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) - version installed on my machine: 5.3.1) - extension for Visual Studio Code that aims to provide all-in-one features and utilities for LaTeX typesetting (list of features can be found [here](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)).

For reasons why I consider this stack to be very useful and a description on how to set it up, please refer to the [article](https://stefantruehl.github.io/2018/04/30/latexEnvSetup.html). 
For the remainder of this article, I assume you have a working setup of the tool chain, according to the [article](https://stefantruehl.github.io/2018/04/30/latexEnvSetup.html).


## Step 1: Clone Thesis Template
Use the git client of your choosing to clone the repository locally.
Using the console client, the command is:
```sh
git clone git@github.com:mbredel/thesis-template.git
```
## Step 2: Configure VS Code
The thesis-template repository brings along a make file for pdf generation. Although I managed to run it from VS Code, I did not get SyncTex to work properly. 

When viewing a tex-file and the pdf-file side-by-side in VS Code, SyncTex allows you to jump to a specific place in the pdf by clicking in the tex file (and the other way around). This is a very handy feature, especially when dealing with long documents (such as a thesis). For further information on this, please review the [Visual Studio Code LaTeX Workshop Extension documentation](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop).

Due to these limitations, I recommend the standard LaTeX Workshop Extension's way of generating a document instead of the make file. In order to do that, first open VS Code and change the workspace configuration to the following. This is done the same way as I already described in my previous article. Thus, no further explanation should be necessary.
````json
{
    "latex-workshop.latex.recipes": [
        
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
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
Once you have added the workspace settings, return to the editing view of the *thesis.tex*-file.
Choose the item "Build LaTeX project (Alt+Ctrl+B)" from the context menu. Now a pdf should be generated properly without errors. 

This is the way I recommend to create the pdf during thesis writing. Once your are done and want to create the final version that you hand in and print, I strongly encourage you to use the make file with the publish parameter, as it will embed all fonts.
```sh
make publish 
```

## Step 3: Develop your Thesis in your own Remote Repository (optional but strongly recommended)
I strongly encourage you to develop your thesis in your own Git repository. Besides having a backup, this also gives you the possibility revert any changes you may accidentally have made in the middle of the night and regret in the morning ;-). 

In order to get your own remote Git repository you can choose between a lot of options. The most obvious one are [GitHub}(https://github.com/) (please keep in mind this ist most likely public) or [GitLab](https://about.gitlab.com/). However, if you are a student of the [University of Applied Sciences Darmstadt](https://h-da.de/) you can also choose our own GitLab server [code.fbi.h-da.de](https://code.fbi.h-da.de/).

In any case, once you have your own remote Git repository you can push the thesis-template repository that you cloned in step 1 to your own repository by executing the following steps. 
```sh
cd existing_repo_where_you_cloned_the_thesis_template_repo
git remote rename origin old-origin
git remote add origin <address of your own repository>
git push -u origin --all
git push -u origin --tags
```



