---
layout: post
title: "Awesome JS Auto Completion"
---

One area that Vim often falls down compared to other editors is in auto completion and for a while I've been looking at ways to improve it.

Today I came across [YouCompleteMe](https://github.com/Valloric/YouCompleteMe), a code completion engine for Vim. It works best with C languages as it provides an engine to provide completition, but it is also able to hook into Vim's omnicomplete to provide completion for languages like Ruby, Python, JavaScript, and so on. As I work in Ruby & JavaScript 99% of the time, that was what interested me most.

Installing YouCompleteMe isn't the easiest - there's an extra step to take after installing it, which is done through something like Vundle or Pathogen.

I won't repeat the entire instruction guide - [it's in the README](https://github.com/Valloric/YouCompleteMe#mac-os-x-super-quick-installation), but for me it was a case of:

- Install the plugin with Pathogen
- `brew install cmake`
- `cd ~/.vim/bundle/YouCompleteMe && ./install.sh`

The README also says you should use the latest MacVim on OS X, but I use terminal Vim and didn't have any problems. YMMV.

Once you've done that you'll get autocompletion, although it won't be at all intelligent. That's where [TernJS](https://github.com/marijnh/tern_for_vim) comes in. This is a project to provide better JS support within editors - and so far there are plugins for Vim, Emacs and Sublime Text 2. When installed, it hooks into Vim's omnicomplete and updated it, and then YouCompleteMe picks it up.

Once again, there's an extra installation step here. Install the plugin as normal with Vundle/Pathongen/etc, and then you'll need to take some extra steps.

- Make sure you have Node and npm installed.
- `cd ~/.vim/bundle/tern_for_vim && npm install`

Then fire up Vim in a JS project, and start typing. Intelligent auto completion! Here, in a small JS game I've been working on, you can see it makes sensible suggestions, and tells me what type the variables it's suggested are.

![](http://cl.ly/image/0C170s2t1b21/Screen%20Shot%202013-08-21%20at%2015.03.41.png)

Hit `tab` to cycle through the suggestions, or keep typing to narrow it down. It's not perfect - both YCM and Tern are still relatively young, but they already make a powerful combo and hopefully will only improve with time.

TernJS also has other features to find the definition of things, and these are documented in the [Tern for Vim README](https://github.com/marijnh/tern_for_vim).
