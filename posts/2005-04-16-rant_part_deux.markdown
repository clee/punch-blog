---
title: rant part deux
published: true
---

<p>
Several people were kind enough to point out that this code:  

    for i in xrange(foo):    print i

  
actually wouldn't work. Thanks, I'm an idiot. I should have had:  

    for i in xrange(len(foo)):    print i

</p>
<p>
Next, yet another method of reversing/iterating backwards over a list
has been suggested in multiple places, one which I didn't know about.  

    foo = ['one', 'two', 'three']bar = foo[::-1]

</p>
The only thing I can possibly say to that is... but the ternary operator
is too obscure? C'mon, give me a break. This provides the ability to
have tons of random line noise and make your code just as unreadable.

And, [Seth][]: Since I couldn't catch you on IRC earlier, I'll just
reply here.

Multiple issues to respond to, so let me break it down.

1.  You seem to be confused as to what I was complaining about with
    `list.reverse()`. It's not that I want a copy of the list, exactly,
    but I want the return value of `list.reverse()` to be sane, which in
    my exceedingly humble opinion, it is nowhere near.
2.  I'm not upset, mind you, just mildly annoyed, by the
    iteritems()/enumerate()/xrange() issue. And the reason that it's
    annoying to me is because it's inconsistent. Some of the iterator
    methods are global and some of them are not. Inconsistency is lame.
    End of topic.
3.  Ternary operators seem to be quite the polarizing issue so I'll just
    leave my stance exactly where it is. I think they're useful, and I'd
    like to have them, but obviously I can work around the language not
    having them...
4.  Especially since Python doesn't have sane scoping, either; the
    method-local and class-local scoping rules provide the opportunity
    for **way** too many obscure and annoying bugs. I note that you
    didn't respond to my issue with scoping at all.

</p>
Oh, also, a friend of mine has offered to send you a copy of the
Smalltalk book, where he says that they solved the problem of doing
lambdas and maps efficiently.

I'll kindly ignore your not-so-subtle digs at my programming ability (or
perceived lack thereof) and refuse to insult you for liking Python. Mind
you, I still think it's a useful language, but I'm just annoyed at the
inconsistencies and some pet features (like ternary operators, or sane
scoping) that I wish it had.

  [Seth]: http://blog.sethdot.org/index.cgi/223
