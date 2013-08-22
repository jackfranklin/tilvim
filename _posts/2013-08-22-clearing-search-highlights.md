---
layout: post
title: Clearing the Search Highlight
---

I think it's the biggest annoyance of any Vim-er. Highlighting something when I search for it is great, but a quick way to get rid of that highlight would be even better. I think today I finally found the perfect way to do it. This is one I picked up from [Katrina Owen's vimrc](https://github.com/kytrinyx/dotfiles/blob/master/.vim/vimrc).

    :nnoremap <CR> :nohlsearch<cr>
    " clear the search buffer when hitting return

Now once I've searched, the highlight is gone the next time I hit enter, which is brilliant.
