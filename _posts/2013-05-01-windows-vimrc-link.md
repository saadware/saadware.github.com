--- 
layout: post 
title: Linking the vimrc file in Windows
tags: vim,reference
--- 
Using Vim on multiple machines and platforms is necessary when you have
a geek crush on your editor like I do. Being able to have your settings
and plugins follow you around on these various machines is invaluable.  

For me, I keep all my vimfiles stored in a [GitHub
repo](https://github.com/saadware/vimfiles). That in combination with
using [pathogen](https://github.com/tpope/vim-pathogen) as my plugin
manager enables a ubiquitous experience regardless of the machine and
platform I'm on. 

For Windows the _vimrc file is stored in the user's home directory.
(i.e. `c:\users\scott\_vimrc`).  Naturally, I want to use my vimrc file
that is stored in my vimfiles repo (i.e. `c:\users\scott\vimfiles\vimrc`).
For modern Windows installations, creating a symbolic or hard link is
trivial using the
[mklink](http://en.wikipedia.org/wiki/NTFS_symbolic_link#Syntax)
command. Yet, it's something I always have to lookup in terms of syntax.

So for reference sakes, here we go:

To create a symbolic/hard link so that my _vimrc file points to
the vimfiles/vimrc file I do the following:

`cd c:\users\scott`  
`mklink /h _vimrc c:\users\scott\vimfiles\vimrc`

And there we have it. A joyous harmony where my vimrc file always points
to the trusthworthy one I store in git. 

Tootles.
