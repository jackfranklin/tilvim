---
layout: post
title: "Ruby text objects"
---

Yesterday I discovered a text object within Vim that I'd not realised existed, which served as a perfect tip post up onto this blog (and to try and get back to doing it more regularly!).

Any seasoned Ruby + Vim user has probably got Drew Neil's [textobj-rubyblock](https://github.com/nelstrom/vim-textobj-rubyblock) plugin installed, which adds the text objects `ar` and `ir` to select around and inside a ruby block.

However, what I didn't know about was the text object `im`, which is provided by vim-ruby (which comes with Vim by default), to select the contents within the current Ruby method, and its sibling `am`, to select around the method. Hat tip to [@tomstuart](http://twitter.com/tomstuart) for that one:

<blockquote class="twitter-tweet" lang="en-gb"><p>It took me a few minutes to work out how to select the body of a Ruby method in Vim, but I was happy when the answer turned out to be “vim”.</p>&mdash; Tom Stuart (@tomstuart) <a href="https://twitter.com/tomstuart/statuses/489776294075592704">July 17, 2014</a></blockquote>

Drew Neil ([@nelstrom)](http://twitter.com/nelstrom)) then followed up explaining that it was recently added to vim-ruby:

<blockquote class="twitter-tweet" lang="en-gb"><p><a href="https://twitter.com/telemachus">@telemachus</a> it’s a text object defined in the vim-ruby plugin: <a href="https://t.co/YZSmUPWr0P">https://t.co/YZSmUPWr0P</a>&#10;Should be available out the box in recent Vim builds.</p>&mdash; Drew Neil (@nelstrom) <a href="https://twitter.com/nelstrom/statuses/489802266170630144">July 17, 2014</a></blockquote>

If you're running a recent version of Vim you should have this functionality, but if you're not, you can always install the latest version of vim-ruby as a plugin through Vundle / Pathogen. The best solution though if possible is to simply upgrade your Vim.

Whilst reading to produce this blog post I also discovered the objects `iM` and `aM`, which select in and around the current Ruby class, too. All of these are going to be really useful in my day to day development.

