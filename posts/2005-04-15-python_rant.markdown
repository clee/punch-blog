---
title: python rant
published: true
---

(This is a pretty geeky entry, so if you're not a geek, consider
yourself warned.)  
I have a lot of little tiny annoyances with python, since I've been
using it for a while now to hack on some stuff. Here's a collection of
the ones that are floating on top of my brain.

#### ::sniff::

  
I miss my ternary operator.

</p>
In C, and C++, and Perl, and Ruby, and PHP, and pretty much any language
that I've ever written in (hell, I think even JavaScript supports this,
though I could be wrong about that one since I haven't written any
JavaScript code in years), you can use a very terse syntax for
`if (foo) { return bar; } else { return baz; }` using what is referred
to as the ternary operator.

<p>
The shortened syntax is more like:  

    (foo ? bar : baz)

</p>
Yeah, it's kinda weird. And yeah, if you don't understand it, it's not
very intuitive. However, it makes for much shorter and clearer code (to
those who grok ternary operators). Python doesn't support this. At all.
There was a proposal to include it and it got smacked down, so that they
could include such other genius ideas as `reversed()` instead. Speaking
of which...

#### backwards

  
Reversing an array is done like:  

    foo = ['one', 'two', 'three']foo.reverse()

  
This does not return a reversed copy of the array, but it does reverse
the array in-place and return 'None' which is quite confusing.
Especially if you're used to sensible languages which return a reversed
copy. So this code doesn't work.  

    foo = ['one', 'two', 'three']for i in foo.reverse(): # bzzzt, reverse() returns 'None'   print i

  
You **can** iterate through an array with the `reversed()` keyword,
like:  

    for i in reversed(foo):  print i

  
**However**, this is a python-2.4-specific feature, so it's useless if
you care about older python releases. Also, it doesn't create a reversed
array, just hands you a pointer to a reversed list iterator. So you
can't do:

</p>
<p>
    foo = ['one', 'two', 'three']bar = reversed(foo)print bar[0] # 'three'? how about a TypeError!

</p>
Because `bar` is actually not a list, or array, or what-have-you, but
it's a listreverseiterator object. Whatever the hell that's supposed to
mean. What it translates into is basically "Surprise! We hate you."

<p>
So, you have to do:  

    foo = ['one', 'two', 'three']foo.reverse()for i in foo:   print i

  
Which, granted, ok, isn't the end of the world, but it's pretty ugly and
it doesn't work at **all** the way I had expected it to, which to me is
the sign of a language that sucks.

</p>
<p>
For reference, the following code in ruby does work exactly how I
expected it to. And because ruby and python share a decent amount of
syntactical sugar, I keep on getting annoyed when things that I expect
to be working in python simply aren't.  

    foo = ['a', 'b', 'c']p foo.reverse() # prints out "['c', 'b', 'a']"foo.reverse().each { |i|   print i}

  
Ruby's list iterators are weird, sure. But actually, that's a good way
to bring up my next complaint.

</p>

#### iterators in general

  
Why the hell do you have multiple types of list iterator methods in
python? I shouldn't have to remember a different type of iterator method
for every different type of container, nor should I have to remember
whether it's a global iterator method or a per-container one. That's
just annoying, and pointless.

</p>
<p>
So, you have `foo = ['a', 'b', 'c']`, right.  
Now, to recap, you can traverse the list backwards (in 2.4, anyway)
with:  

    for i in reversed(foo):  print i

</p>
<p>
You can get the indexes of the members of the list with:  

    for i in xrange(foo):  print i # Prints out the index of each member

</p>
<p>
You can also do:  

    for i, n in enumerate(foo): print i, n # Prints the index and the member

  
Although I have no idea why you'd want to. (You can always just do
xrange(foo) and then 'foo[i]' since they give you the same thing. But
ternary operators would be too confusing.)

</p>
<p>
But, if you have a dict instead of a list, all of a sudden...  

    foo = { 'a':1, 'b':2, 'c':3 }for i, n in foo.iteritems():    print i, n

</p>
Using `enumerate()` gives you the index of the 'a', 'b', and 'c' keys.
Also, note that `enumerate()` is a global, like `reversed()`, but
`iteritems()` is a member of the dict class type. This is the kind of
inconsistency in a language that kills me.

#### white space

  
Surprisingly, I don't mind the whitespace thing. It just doesn't bother
me that much. (Ok, so that's not really a complaint. Still, enough other
people complain that I figured it was worth noting that it just doesn't
irk me.)

</p>

#### scoping

  
Scoping is **weird** in python. Let me explain.  
In regular languages, a variable declared inside of a block of code only
lives until the end of that block; this is the 'scope' of the variable.
So if you have:  

    if (condition) {    string foo = "hahahaha";}print (foo); /* Error! 'foo' didn't make it past that last '}' */

  
(Yeah, that's not a real language, though I suppose it could be valid C
or C++ or something. I don't care, it's just there to illustrate a
point.)

</p>
But in python, guess what?

<p>
    if condition:   foo = "hahahaha"print foo # This actually *works* - wtf?

</p>
There are other issues that annoy me, but these are just the ones on top
of my head. I'll write another rant if this one pisses off enough python
devs.
