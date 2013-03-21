---
title: 4AM once again
published: true
---

So, I have a confession to make.

I've been using [Gossip][] as my Jabber client for a while. Which has
been working out fairly well, since the UI is nice and clean. But
there's been this slight annoyance with it - every time that I close a
chatwindow in Gossip, it forgets how big the window was. Just completely
forgets it.

This behavior finally got annoying enough that I put some gloves on, dug
down deep, closed my eyes, and [massaged some GNOME code][].

The good news is, I lived. I have survived to tell the tale.

The bad news is, it was scary. And I feel sort of dirty.

It took a few hours to work out exactly what needed to go where, but
overall it wasn't quite as terrifying as I had thought it would be. My
underscore key did get quite a workout though. And I got to determine a
few more reasons why I'm definitely glad to be a KDE developer.
(Namespaces. Classes. God, I never thought I'd be so happy to look at
classes again.)

  [Gossip]: http://www.imendio.com/projects/gossip/
  [massaged some GNOME code]: http://c133.org/tmp/gossip-chat-window-save-size.diff
