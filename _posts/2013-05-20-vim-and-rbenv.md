---
layout: post
title: Stop Vim being slow when using rbenv
---

A lot of people, like me, use [rbenv](https://github.com/sstephenson/rbenv) to manage Ruby versions on their machine. When I first set it up, I would see a large lag when opening a Ruby file in Vim. After a bit of Googling, I stumbled upon [a solution](http://stackoverflow.com/questions/9341768/vim-response-quite-slow).

Putting this into my `.vimrc` sped things up quite a bit:

    let g:ruby_path = system('echo $HOME/.rbenv/shims')

If you've been struggling with Ruby slowness and are using rbenv, give that a go. If you use RVM, there's a similar fix:

    let g:ruby_path = system('rvm current')

