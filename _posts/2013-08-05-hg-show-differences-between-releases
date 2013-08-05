--- 
layout: post 
title: Showing Differences in HG Between Releases
tags: hg,reference
--- 
Keeping track of changesets in Mercurial is often done by the use of
tags. For example, tagging a release with a pattern like, r_4.20
helps us know that a particular changeset was considered the 4.20
release. 

To build further on this, it's nice to see what has changed between two
different releases. Say perhaps there was a bug introduced between the
4.18 and 4.20 release and we want to quickly look at all differences
between these two versions. We could run the following:

  hg diff -r r_4.18:r_4.20

This also works if you have a your favorite [graphical diff tool
setup](/araxis-merge-hg-settings).

There seems to be an [entire language](http://www.selenic.com/mercurial/hg.1.html#revsets) 
around specifying revision sets in Mercurial and is worth further 
exploring when wanting to do more sophisticated queries. This one serves
it up just right when wanting to see what changed between two different 
releases. 
