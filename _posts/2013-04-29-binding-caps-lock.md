---
layout: post
title: Binding Caps-lock to Control and Escape
---

As a Vim user, the `ESC` key is an important one. To do Vim *the proper way* you're constantly switching in and out of insert mode. The escape key, however, is a fair distance from the fingertips of most typists. The caps-lock key is the polar opposite - it's rarely useful, yet in a prominent position on the keyboard.

Many developers rebind their caps-lock key to control. Control is used fairly often (particularly for those spending hours in a shell), but sometimes awkward to reach, especially on laptop keyborads.

On Mac OS X, using the aptly-named [KeyRemap4MacBook](http://pqrs.org/macosx/keyremap4macbook/), you can solve these two problems in one by binding the caps-lock key to escape if pressed alone, or to control if pressed in combination with another key.

In OS X's keyboard settings, bind caps-lock to control:

![Binding caps-lock to control](https://pbs.twimg.com/media/BItDLa2CYAAVXxZ.png:medium)

Then, in KeyRemap4MacBook's preferences, enable this setting:

![Binding control to send escape when pressed alone](https://pbs.twimg.com/media/BItC5M0CMAMEBMg.png:medium)

_This post was contributed by [@mark_js](http://twitter.com/mark_js)._
