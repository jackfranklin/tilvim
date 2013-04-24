---
layout: post
title: The Command Window
---

Vim's command window is a nice way to view all commands you've previously run. I stumbled upon this today when I made a small typo in a complex search regex, and wanted to fix it. Instead of typing it all out again, or going back through the command line history by hitting `:` and then my up arrow lots, I was able to bring up the command line window, edit the command I wanted, and then hit enter to run it.

You can access the command window with `q:`. You can then navigate and edit as you would any other Vim buffer. Exit into normal mode and hit enter when you're on the line you want to run. You can then close the buffer as normal with `:q`.

Much more information is available in [this blog post](http://blog.sanctum.geek.nz/vim-command-window/) on the command window, which goes into much more detail.

