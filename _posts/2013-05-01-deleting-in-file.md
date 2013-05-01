---
layout: post
title: Deleting Lines that don't Match a Pattern
---

Something that I found out last night at the [Vim London Meetup](http://www.meetup.com/Vim-London/) that was demonstrated by [Drew Neil](http://twitter.com/nelstrom) was the ability to delete lines in your file that don't match a particular pattern. All credit for this tip goes to Drew - I'm just typing it up on here!

Say we have a file that has lines that look a bit like this (I had to do this earlier today):

    calculate
    something_else
    calculate
    something_else
    calculate
    something_else
    calculate
    some_other_thing
    calculate
    some_more_things
    calculate
    some_other_things
    something_else
    something_else

And we want to delete all lines that don't contain `calculate`. We can do that with `:v`. Simply running:

    :v/calculate/d

Leaves me with:

    calculate
    calculate
    calculate
    calculate
    calculate
    calculate

This is part of the [:global](http://vimdoc.sourceforge.net/htmldoc/usr_10.html#10.4) command.

_Thanks again to Drew for demonstrating this! If you're London based, I highly recommend making an effort to attend the meetups. They are completely free and I never come away from one without at least one new trick or tip that improves my usage of Vim._
