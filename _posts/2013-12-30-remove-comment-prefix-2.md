---
layout: post
title: "Automatic Comment Prefixing Revisisted"
---

A while back, I wrote about [removing Vim's automatic comment prefixing](http://tilvim.com/2013/05/29/comment-prefix.html). This behaviour is turned on by default, and is best shown with an example:

    # some comment {cursor here}

If I was to hit `o` or `O`, to insert on the line above/below, or be in insert mode and hit enter, Vim would automatically add the comment prefix for me, so it would look like this:

    # some comment
    # {cursor here in insert mode}

Vim has automatically added the `#` for me.

I am not a fan of this, and in my original post I advised adding this line to your vimrc to fix it:

    set formatoptions-=or

However, that stopped working for me (I'm not sure when - or if it's related to a new Vim version). Today I managed to figure out the solution. This line does the trick:

     autocmd FileType * setlocal formatoptions-=r formatoptions-=o

To be honest, I'm not sure why the original doesn't work, and if anyone does, please leave a comment, as I'd be really interested to know why. If you've had the same problem, try the new line and see if that solves it.


