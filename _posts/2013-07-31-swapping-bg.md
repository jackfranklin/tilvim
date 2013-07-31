---
layout: post
title: "Swapping background quickly"
---

I often like to change the background from `light` to `dark` or vice-versa depending on my environment. I use the [Solarized theme](http://ethanschoonover.com/solarized) and it comes with two lovely variants, light and dark.

I used to do this by manually entering:

    :set background=light

But why do that when it's easy to set up a mapping to toggle them automatically for you:

    map <Leader>bg :let &background = ( &background == "dark"? "light" : "dark" )<CR>

Now it's a simple case of `,bg` (I have my leader set to `,`) to toggle the background.
