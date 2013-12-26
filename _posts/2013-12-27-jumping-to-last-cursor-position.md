---
layout: post
title: Jumping to last cursor position
---

When I open a file, I like the cursor to jump to the position it was in last
time I had the file open. This can be achieved by adding the following snippet
to your .vimrc:

    augroup vimrcEx
      autocmd!
      autocmd BufReadPost *
        \ if line("'\"") > 0 && line("'\"") <= line("$") |
        \   exe "normal g`\"" |
        \ endif
    augroup END

You can collapse that `autocmd` statement onto a single line, removing the `\`s
if you like, but I think it's more readable this way.

The various conditions in the if statment ensure that the line position is still
valid, in case the file has been changed by some other means since it was last
open (think version control!). Credit goes to [Gary Bernhardt](http://twitter.com/garybernhardt) for this.

I've had this in my .vimrc for a while, and it's been working great, but there's
one thing about it that has been winding me up about it: whenever I write or
edit a git commit message, I don't want this behaviour. The problem arises from
the fact that all git commit messages are in the same "file" as far as vim is
concerned. Today I finally snapped, and added the following snippet to handle
this:

    augroup gitCommitEditMsg
      autocmd!
      autocmd BufReadPost *
        \ if @% == '.git/COMMIT_EDITMSG' |
        \   exe "normal gg" |
        \ endif
    augroup END

You could probably roll both of the above snippets into one if you're that way
inclined, but I'm happy keeping them separate. It makes it easier to see what's
going on, and it'll be easier to change if I ever want to modify the behaviour
in the future.

Now when I write or edit a commit message, the cursor is always on the first
line, which is pretty much always going to be where I want it. Sweet!

_This guest post hastily cobbled together by [Will Pragnell](http://twitter.com/willpragnell)._

