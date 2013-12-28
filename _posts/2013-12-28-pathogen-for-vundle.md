---
layout: post
title: "Swapping Pathogen for Vundle"
---

I've been a big fan of Tim Pope's [pathogen](https://github.com/tpope/vim-pathogen) for managing my Vim plugins. I wrote a small Ruby script to manage the process of cloning from GitHub, and everything was fine.

However, recently, a lot of people have been talking about [Vundle](https://github.com/gmarik/vundle). Vundle takes the process of cloning repositories and manages it all for you, so there's a lot less work for you to do manually.

The process of setting up Vundle is very straight forward. Firstly, clone Vundle:

    git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle

Now it's just a case of editing your vimrc. Vundle requires you to add a few lines to your vimrc file. Make sure these lines are at the very top:

    set nocompatible
    filetype off
    set rtp+=~/.vim/bundle/vundle/
    call vundle#rc()

Vundle requires `filetype` to be off initially, but once you're finished adding Bundles, you can set it to be on again. Next, load in some bundles. Note that you have to load in the `vundle` repo first:

    Bundle 'gmarik/vundle'
    Bundle 'tpope/vim-endwise'
    Bundle 'tpope/vim-git'
    Bundle 'tpope/vim-surround'
    ...and so on...

Vundle will look on GitHub by default for those URLs, but you can also pass it a direct Git URL or even a local Git path.

After all your `Bundle` calls, you are free to add whatever you like to your vimrc, including setting `filetype` back to on:

    filetype on

Now, you can install your plugins by running `:BundleInstall` within Vim (you'll need to restart Vim or source your vimrc once more before). In the future, if you want to update your plugins, you can run `:BundleInstall!` to update. If you remove a plugin from your vimrc, you can run `:BundleClean` to remove the old plugin.

For me, the main advantage of Vundle is less overhead on my part. I've been able to delete my Ruby script for managing my Vim plugins, and the [relevant commit in my dotfiles](https://github.com/jackfranklin/dotfiles/commit/62861ec9e0c6b811b783298ea1ffa994401686e0) shows just how much I was able to delete. Keeping the configuration within the `vimrc` and just using Vundle's functions to pull everything together makes a lot of sense.

    





