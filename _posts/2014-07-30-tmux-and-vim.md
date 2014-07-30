---
layout: post
title: "Tmux and Vim: the perfect combination"
---

Last night at [Vim London](http://www.meetup.com/Vim-London/) I spoke about some of my favourite plugins and settings for Tmux and Vim that allow me to work with them as I do. It's very rare these days that I won't be editing code from Vim, within a Tmux session, but out of the box the immediate advantages of this pairing are not always obvious. It takes some time to get things working.

The talk was recorded and I will update the post with it once it's public, but for now I just wanted to link to some of the plugins and settings I mentioned in the talk that I use in [my dotfiles](https://github.com/jackfranklin/dotfiles).

#### `tnew` alias

I create all my tmux sessions through an alias I have which I've called `tnew`, which simply calls a function called `new-tmux-from-dir-name` (this is taken from the [thoughbot dotfiles](https://github.com/thoughtbot/dotfiles). The function looks like so:

```sh
function new-tmux-from-dir-name {
  tmux new-session -As `basename $PWD`
}
```

This does two things:
- when you create a new session, it names it based on the directory name
- if you are in a directory that already has a tmux session associated, `tnew` will attach you back into the already existing session


#### Tmux + OS X, `pbcopy`

By default tmux on OS X breaks the `pbcopy` command. I'm not going to go into details, but thankfully [Chris Johnsen's fix](https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard) has detailed instructions on how to get that functionality back, and it's not too tricky either.

#### Renumber windows

Out of the box, if you have 3 tmux windows numbered 0, 1, 2 and then you delete the one numbered '1', you're left with two windows: 0, and 2. This is rather odd when you navigate between them. However, you can tell tmux to renumber existing windows automatically with this line in your tmux config:

```
set-option -g renumber-windows on
```

#### vim-tmux-navigator

Without a doubt, this is the one thing that makes working with Vim and Tmux so much better, Chris Toomey's [vim-tmux-navigator plugin](https://github.com/christoomey/vim-tmux-navigator). By installing this and adding a few lines to your tmux config (instructions are in the README), this lets you seamlessly jump between Vim and tmux panes (or splits, as Vim calls them) with the same keystrokes. This means if you have a Vim split next to a tmux pane, you can hop between them even though one of them is Vim, and the other is tmux. It's fantastic, and really ups the intergration of these two tools by another level.

#### Vimux

Although there are many choices, I personally have taken to using [Vimux](https://github.com/benmills/vimux), a plugin which lets you send any command to a tmux pane (which it will create if it doesn't already exist). This means I can set up mappings for running specific commands, such as for testing:

```viml
map <leader>nt :call VimuxRunCommand("clear; npm test")<CR>
```

It also has a function which you can run that will prompt you for a command, which I have mapped to `<leader>x`:

```viml
map <leader>x :VimuxPromptCommand<CR>
```

#### tmux-complete

[This plugin](https://github.com/wellle/tmux-complete.vim) adds any word visible in a tmux pane to a completion function that you can trigger with `<C-X><C-U>`. It's rare that I want to type something in Vim that I can see in a tmux pane, but when I do this plugin is always useful and saves coming out of Vim to grab some text.

So that's just some of the plugins I use daily when working with tmux and Vim. If you have any to recommend, please do leave a comment!
