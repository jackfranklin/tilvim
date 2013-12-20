---
layout: post
title: Live in-place Ruby execution
---

Today I was able to get Vim to execute Ruby files without ever having to leave Vim, and putting the results of execution in place next to the code that was executed. [Here's a quick demo on Youtube](http://www.youtube.com/embed/wigJLGmEKC4).

There's three parts to this:

1. The [rcodetools gem](http://rubygems.org/gems/rcodetools), which includes the CLI tool `xmpfilter`, which does the work.
2. The [xmpfilter vim plugin](https://github.com/t9md/vim-ruby-xmpfilter) which hooks up Vim to xmpfilter.
3. The relevant [mappings in your vimrc](https://github.com/jackfranklin/dotfiles/blob/master/vim/.vimrc#L260) to get it all working.

Installing the gem is simple:

    gem install rcodetools

You then need to install the [xmpfilter vim plugin](https://github.com/t9md/vim-ruby-xmpfilter). I recommend going down the Pathogen route for installing plugins, but do it whichever way you prefer.

There's two parts to marking a line for execution. The first is to comment it with the `# =>` syntax, which is what xmpfilter looks for. The second is then a command to run xmpfilter over the current file.

Here are the mappings I've gone for:

    nmap <buffer> <F4> <Plug>(xmpfilter-run)
    xmap <buffer> <F4> <Plug>(xmpfilter-run)
    imap <buffer> <F4> <Plug>(xmpfilter-run)
    nmap <buffer> <F3> <Plug>(xmpfilter-mark)
    xmap <buffer> <F3> <Plug>(xmpfilter-mark)
    imap <buffer> <F3> <Plug>(xmpfilter-mark)

Now I can hit F3 to mark a line to execute and then F4 to execute it.

__Note__: if you use rbenv to manage your Ruby versions like I do, you'll need [Tim Pope's rbenv.vim plugin](https://github.com/tpope/vim-rbenv) which tells Vim where your Ruby is located. Without this plugin I couldn't get xmpfilter to work, presumably due to not being able to locate the rbenv installed version of Ruby. Adding that plugin did the trick.
