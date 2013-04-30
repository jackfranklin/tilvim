---
layout: post
title: Vim Scratch Plugin
---

The [Vim Scratch plugin](https://github.com/duff/vim-scratch) is a handy plugin that allows you to open "Scratch buffers". These are buffers that Vim wont ask you to save, it's just a temporary buffer that you can create and will be discarded when you quit Vim.

Once installed, you can open a scratch buffer with `:Scratch`. If you close the buffer and then run `:Scratch` again, the contents are remembered, but the contents will be lost when you close Vim.

I've been using this lots for taking quick notes when working on something, or to note something I need to revisit.
