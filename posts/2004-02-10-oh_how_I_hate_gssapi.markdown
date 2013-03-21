---
title: oh how I hate gssapi
published: true
---

so now that I have a local kerberos server, and it hands out tickets
like a champ, and life is good, the next (logical) step is to want to
have single-sign-on for things like (say) my email.

KDE has a custom ground-up SASL implementation that supports LOGIN,
PLAIN, CRAM-MD5 and DIGEST-MD5, but not GSSAPI (which is a layer on top
of Kerberos). I took a look at it and decided that I could implement a
GSSAPI function for the KDE SASL implementation. I had no idea that it'd
be so damned frustrating. why is GSSAPI so complicated, and
poorly-designed to boot?

if you think I'm joking, or complaining about nothing - the main
function, gss\_init\_sec\_context, takes THIRTEEN parameters. that's a
lot of margin-for-error. one would think they might use custom data
structures, ones more complicated than the standard struct with a void
pointer and an int to indicate the length of the data, but no. of course
not.

oh well. when I'm done, KDE will have a GSSAPI implementation, meaning
that it should Just Work (TM) with any Kerberized service that uses
SASL. Namely, this means IMAP servers and probably a few SMTP servers -
having single-sign-on for these services will be great.
