---
layout: post
title: Aliasing g
---

This isn't so much of a Vim tip (sorry), but a terminal tip that has made a lot of difference to my workflow recently, so much so that I've bent the rules slightly and posted it today.

This one is courtesy of [Ben Orenstein's dotfiles](https://github.com/r00k/dotfiles), from which I have picked up a lot of good things, including this shell function:

    function g {
       if [[ $# > 0 ]]; then
         git $@
       else
         git status
       fi
    }

This does a really simple thing, and remaps `g` on your command line. If you call `g` on its own, you'll call `git status`,  but if you pass it an argument, it will pass that through to git.

For example:

    g => git status
    g diff => git diff
    g commit => git commit

Of course, you should also set up [some aliases for common commands](https://github.com/jackfranklin/dotfiles/blob/master/zsh/aliases) to save yourself more typing.

