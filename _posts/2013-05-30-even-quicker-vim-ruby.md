---
layout: post
title: vim-ruby
---

Last week I published [a post on making Vim quicker with rbenv / RVM](http://tilvim.com/2013/05/20/vim-and-rbenv.html) and it gained quite a few comments. It did help out but it was also pointed out that it was not a good way of doing things.

I was then told that the problem had been fixed in [vim-ruby](https://github.com/vim-ruby/vim-ruby), but the version of vim-ruby that contained the fix was not the one bundled with the latest Vim. This will be fixed in Vim 7.4 which is not a million miles away, but if you want to get it now, you can simply bundle vim-ruby as a plugin, using the latest from Github.

Then you can safely delete this line from your config:

    let g:ruby_path = system('echo $HOME/.rbenv/shims')

I have found that this change has sped up Vim hugely, even more then the previous solution, and now have one less complete hack in my `.vimrc`.

Hope this helps!
