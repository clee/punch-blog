---
title: subversion migration
published: true
---

One of the things I keep thinking about with KDE's much-vaunted
CVS-\>SVN migration is... why don't we just leave the CVS server up as
it is, and screw the whole "import the entire history of our repository
into SVN" idea?

Think about it.

The cvs2svn script is good. Don't get me wrong - it's pretty impressive.
But we've done some evil to our CVS repository - manually moved files,
etc, and cvs2svn is not perfect; why don't we just leave the CVS server
up and running read-only and import a snapshot (say, 3.4) into SVN
without trying to drag all of the history along?

People who want to pull absolutely 100% accurate checkouts of a given
revision can do it with the old tools and we can evaluate subversion
without having to deal with any possible issues brought up by weirdness
caused by cvs2svn.

I personally think this may be the smartest way to move forward, but I'm
sure that others have differing opinions. Care to [share them with
me][]?

  [share them with me]: mailto:clee@kde.org
