---
title: yet another python rant
published: true
---

I hit another case of "Python really makes me angry" today and I thought
I would share it with you all, since I know how much you love reading
about things that enrage me.

<p>
I have a chunk of code that (while being significantly more complex)
looks like this:  

    def baz():    print kitties # This works fine.def bar():    print kitties # This one throws an exception!    kitties = 'delicious' # The exception is because of this.def foo():    stuff = {'kitties': 'squishy'}    for k, v in stuff.iteritems():        globals()[k] = v    baz()    bar()

</p>
This is another example of Python's scoping being weird, and in my
opinion, broken.

Let me explain, in case you didn't bother copy & pasting that into a
python shell and running it.

`baz()` will execute properly. `bar()` will not. But the error you get
from `bar()` is worthless - it tells you that you're trying to read from
an unassigned local variable, except you're trying to read from a global
variable. The problem I have is not that `bar()` fails - it's that it is
inconsistent with `baz()` working. I realize that adding a
`global kitties` makes `bar()` work properly; but I think that in this
case, the error should really be when you try to reassign a global
variable that hasn't been declared as global.
