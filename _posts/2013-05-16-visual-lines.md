---
layout: post
title: "Making `j` and `k` work on visual lines"
---

_Sorry for the hiatus - conferences have kept me busy. Posts will return to mostly daily rate from now on._

Four of the most important lines in my [vimrc](https://github.com/jackfranklin/dotfiles/blob/master/.vimrc) file are:

    nnoremap k gk
    nnoremap j gj
    nnoremap gk k
    nnoremap gj j

You see by default, `k` and `j` go up and down _physical lines_, not visual lines. What this means is that if you've one line but it wraps and spans more than one on your screen, `j` or `k` will jump up or down to the next physical line, and skip the wrapped lines of the current line you're on. This is a bit confusing, so hopefully this helps:

    1 this is the first line
    2 this is the second line but imagine
    3 it has been wrapped {C}around because
    4 you're on a really small screen
    5 and it wont fit on one line

If you imagine your cursor is where the `{C}` is and you press `k`, you wont end up on line 2 as you might expect, but on line 1, because `k` has gone to the next physical line, which is line 1. It doesn't respect line wraps. However, `gk` does respect line wraps, so if you're on line 3 and hit `gk`, you will end up on line 2. Personally I prefer this behaviour, so these four mappings swap `k` to work like `gk` and `gk` to work like the default `k` behaviour, and then obviously the same for `j`.

    nnoremap k gk
    nnoremap j gj
    nnoremap gk k
    nnoremap gj j

Thanks to [Yubin Kim](http://yubinkim.com/?p=6) for his collection of Vim tips, which is where I stole that mapping from.
