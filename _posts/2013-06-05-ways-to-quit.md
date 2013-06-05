---
layout: post
title: "Ways to quit"
---

In Vim you are more than likely to want to close a file at some point after opening it.

If you open a file, have a skim through and want to close it again, you can do so with the `:quit` command. This can be shortened to `:q`.

If you make some rubbish changes and want to quit and discard them, force quit with `:q!`.

If you make some useful changes you can write them with `:w` but if you want to write and quit, combine the two with `:wq`. If the file doesn't currently have a filename, you can specify one with `:wq {file}`. If the file is read only, you can force it to save with `:wq!` - this should work as long as the file has a name.

For a short and sweet alternative, you can write changes (only if any exist) and quit using the `:xit` command or `:x` for short.

If you prefer to avoid ex commands, you can also use `ZZ` instead which is perhaps the fastest yet as it's just a double tap of the same key.

See `:help :q` for more details.

<hr>

Lovingly typed (in Vim) by [Guy Routledge](http://www.guyroutledge.co.uk)
