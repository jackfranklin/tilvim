---
layout: post
title: Better Pasting from the Clipboard
---

Something I find myself doing fairly regularly is copying something from outside of Vim into Vim. Usually this is something like a chunk of code from a Stack Overflow post, or a new reference to add to my Bibtex file (I'm in the middle of my University dissertation...). The problem with pasting some code in is, as you've probably seen, that Vim tries to indent the code as you paste it. If the code already has indents (which usually it does) this is a bit of a nightmare, as you end up with incorrect indenting and have to perfom `==` on a number of lines to correct it.

There is a better way. We can run `:set paste`, which tells Vim to be in _paste_ mode. In this mode, when you're in insert mode and paste in, Vim will not perform any indenting itself, and let what you're pasting in dictate it. You can then run `:set nopaste` to turn off paste mode.

This is good, but it's still too many steps for me:

1. Exit insert mode.
2. Run `:set paste`
3. Go into insert mode.
4. Hit `Cmd+V` to paste in.
5. Exit insert mode.
6. Run `:set nopaste`.

That's far too much work, and far too many keystrokes. Thankfully, we can turn this into a handy mapping. I should add that credit for this mapping goes to [Ben Orenstein](https://github.com/r00k/dotfiles/blob/master/vimrc), as it was taken directly from his `.vimrc` file, all I've done is write it up as I thought it warranted it. Here's the mapping:

    map <Leader>p :set paste<CR>o<esc>"*]p:set nopaste<cr>

Let's step through that:

1. `:set paste<CR>` turns on paste mode
2. `o<esc>` inserts a new line below and goes back into normal mode
3. `"*]p` gets the content from the system clipboard, and pastes it in.
4. `:set nopaste<cr>` turns paste mode off.

The one oddity there is the use of `]p` instead of `p` to paste in. Vim's help can solve that one, `:h ]p`:

    Like "p", but adjust the indent to the current line.

Effectively it applies the indent within the pasted content from the indent level that you're at when you invoke the pasting.

This is a great example in my opinion of the power of Vim and its mappings - this mapping in particular is one I use multiple times a day and really does save me time and keystrokes.

