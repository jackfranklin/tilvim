---
layout: post
title: "The CamelCase Motion Plugin"
---

I, as I expect a lot of you do, work in some languages that use `camelCaseForNaming` (JavaScript), and others that prefer `the_snake_case_way_of_things` (Ruby). I don't really have a preference to which one I use, but sometimes I get frustrated by Vim's `w` command (and the corresponding `b` command), and how it doesn't treat underscores or an upper-case letter in a long variable name as a new word.

For example, if I have the following, with my cursor on the starting 's':

    someLongMethodCall();

What I want is for `w` to take me to the capital `L`, then to the capital `M`, then the `C`, and so on. Similarly with this code:

    some_long_method_call

I'd like to be able to jump between the underscores.

I've never been able to find a way to do this until now. The solution is the brilliant [CamelCase Motion](https://github.com/vim-scripts/camelcasemotion) plugin. This provides commands for jumping intelligently, as I described above, and works with both CamelCase and snake_case.

What I've done is simply map `w`, `b` and `e` to the CamelCase versions:

    map <silent> w <Plug>CamelCaseMotion_w
    map <silent> b <Plug>CamelCaseMotion_b
    map <silent> e <Plug>CamelCaseMotion_e
    sunmap w
    sunmap b
    sunmap e

Thank you to Reddit user "nandryshak" for mentioning this in [a r/vim thread](http://www.reddit.com/r/vim/comments/1tbzw2/on_moving_through_and_editing_snake_case_text/).

`w`, `b` and `e` will now work mostly as before, except when it detects camel casing or snake case, at which point it will act accordingly. Perfect!



