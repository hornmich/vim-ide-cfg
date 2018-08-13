# vim-ide-cfg
My configuration of VIM editor to act like IDE

This is my personal VIM editor configuration that I currently use for my
development.

# Features

* Vundle for easy plugin management
* YouCompleteMe for fast code completition
* YouCOmpleteMe for real time syntax errors highlighting
* Vim-buftabline for easy buffers management 

![features preview](https://github.com/hornmich/vim-ide-cfg/blob/master/doc/vim_preview.apng "Preview of the features.")

# Installation

## Prerequisites

In order to use this configuration, the following prerequisites must be fulfilled:

* VIM version: 7.4.1578 with Python 2 or 3 support (dictated by [YCM plugin](https://valloric.github.io/YouCompleteMe/)
* [Vundle plugin](https://github.com/VundleVim/Vundle.vim)
* Have a directory tree at your home like the following (this is obvious if you follow the Vundle installation guide, but I mention it for clarity of next steps):
     .vim/
    | bundle/
    | | Vundle.vim/
    | | | .git/
    | | | autoload/
    | | | doc/
    | | | ftplugin/
    | | | syntax/
    | | | test/
    | | | .gitignore
    | | | CONTRIBUTING.md
    | | | LICENSE-MIT.txt
    | | | README.md
    | | | README_KR.md
    | | | README_ZH_CN.md
    | | | README_ZH_TW.md
    | | | changelog.md

## Installation

Download the .vimrc file from this repository and put it in your home directory.

Start your Vim editor and use Vundle to install the plugins:

    :PluginInstall

The following plugins should be installed automatically:
* Plugin 'VundleVim/Vundle.vim'
* Plugin 'Valloric/YouCompleteMe'
* Plugin 'ap/vim-buftabline'

Download the .ycm_extra_conf.py file from the repository and put it into ~/.vim directory.

Create local .ycm_extra_conf.py file using the one located in ~/.vim directory as a template and customized for your C/C++ project.

To fill the paths to header files I am using the following command and put the output to the find .ycm_extra_conf.py file.

find $(pwd) -type f -printf "\t'-I', '%p',\n" | grep -P ".*\.h((pp)|(h))?',$"

And thats it.
