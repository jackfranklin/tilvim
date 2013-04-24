---
layout: post
title: Easier Reindenting
---

With a visual selection you can use `<` to indent left by 1 tab (or spaces, depending on your settings) and `>` to indent right by 1 tab. And of course we can prepend these with a motion to indent more than one tab at a time, such as `3>`.

But what if you're not sure how many you want to indent by? You can guess a number and then alter it after that, but that's not efficient. You can use `gv` to select the previous visual selection, so what I tend to do is make a selection, and use `<` or `>`. If I need to indent again, I can do `gv>` to indent the same selection 1 more to the right.

From this, I decided to map `<` and `>` to do this for me automatically:

    " reselect visual block after indent/outdent
    vnoremap < <gv
    vnoremap > >gv

This means that when I run `>`, the selection I indented is selected for me again, so I can then keep hitting `>` however many times I need to get the code indented just right. This is one of my favourite snippets in my [.vimrc](https://github.com/jackfranklin/dotfiles/blob/master/.vimrc#L87).
