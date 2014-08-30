--- 
layout: post 
title: Araxis Merge HG Settings
tags: hg,mercurial,merge
--- 
As with any technology tool switch, there is a period of time where I
slowly transition my other tools/processes to work with the newcomer. 
Since switching over to mercurial (hg), I needed to find a way to 
infuse my existing graphical diff tool, [Araxis Merge](http://www.araxis.com/merge/) 
into the mix. 

Ultimately, here is the pertinent information I have in my 
mercural.ini (or .hgrc on Mac) file:


    [extensions]
    hgext.extdiff=

    [ui]  
    merge = araxis  

    [extdiff]  
    cmd.arxdiff=C:\Program Files\Araxis\Araxis Merge\ConsoleCompare.exe  
    opts.arxdiff=/2 /wait


This allows me use the Araxis Merge tool from both Tortoise Workbench 
and from the command line. 

To diff files in my working directory, I can now run:

    hg arxdiff

To invoke the three-way merge to be invoked, I simply run the standard:

    hg merge

I have different settings for Araxis when I use git, but that's 
another post. :)

Having a good diff/merge tool is well worth the investment as it saves 
time and headaches. Araxis has been my choice for over a decade now and
it continues to prove itself as irreplaceable.
