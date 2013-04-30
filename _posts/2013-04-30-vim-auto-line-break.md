--- 
layout: post 
title: Auto Line Breaking in Vim
tags: vim,reference
--- 
Almost a year ago I switched my blog engine over to
[Jekyll](https://github.com/mojombo/jekyll). Since then, all of my posts
have been written in my favorite editor, [Vim](http://www.vim.org).
One of the handy settings that I've ended up using quite a bit of while
using the editor to write paragraphs instead of code is 
[`textwidth`](http://vimdoc.sourceforge.net/htmldoc/options.html#'textwidth').

Description:  

> 'textwidth' 'tw' number (default 0)  
>	Maximum width of text that is being inserted.  A longer line will be
>	broken after white space to get this width.  A zero value disables
>	this.  'textwidth' is set to 0 when the 'paste' option is set.  When
>	'textwidth' is zero, 'wrapmargin' may be used.  See also
>	'formatoptions' and |ins-textwidth|.
>	When 'formatexpr' is set it will be used to break the line.
>	NOTE: This option is set to 0 when 'compatible' is set.

This is super handy when you want your line to automatically wrap to the
next after a certain number of characters are written. In my case, I
like setting it to 72, which wraps to the next line once I go over 72
characters. 

	:set tw=72

This operates on the current buffer and all *new* typing wraps at 72
characters.  

But what about modifying existing content? Say for instance I need to
edit a paragraph that is already written? The `textwidth` setting does
not always work here and a
[format - `gq`](http://vimdoc.sourceforge.net/htmldoc/change.html#gq) command
must be executed.

When wanting to perform this on the existing paragraph I normally just
go into visual mode and select the paragraph and issue the format.

So to select the current paragraph and reformat: `vap` followed by `gq`

While a great editor, Vim needs a bit of tweaking to work in *word
processor* mode. These settings and commands help it feel a bit more
natural to write more like humans would.
