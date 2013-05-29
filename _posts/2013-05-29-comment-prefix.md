---
layout: post
title: Automatic Comment Prefixing
---

For a long time, I hated the fact that if I had something like this in Vim:

    // foo{C}

Where `{C}` is the cursor, and hit `o` onto the next line, Vim would insert the comment bit for me:

    // foo
    // {C}

More often than not, I didn't actually want that. Thankfully, as with a lot of my Vim problems, the [dotfiles](https://github.com/r00k/dotfiles/) of [Ben Orenstein](http://twitter.com/r00k) came to my rescue with [this line](https://github.com/r00k/dotfiles/blob/master/vimrc#L295):

    set formatoptions-=or

This stops Vim continuing the comment automatically.

As an aside, it seems like a good time to mention that [my dotfiles are on Github also](https://github.com/jackfranklin/dotfiles) if you, like me, like trawling through other's dotfiles for gems.

