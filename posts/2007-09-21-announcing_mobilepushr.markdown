---
title: announcing MobilePushr
published: true
---

When I first heard that the iPhone had a camera built-in, as well as
WiFi, those two features triggered the following thought:

> It would be really hot if you could upload the pictures from the
> camera directly to Flickr.

When I got my iPhone, I figured out a workflow that I could use to post
pictures from the phone to my Flickr account, but it ~~totally sucked
balls~~ was less than optimal. For each picture I wanted to upload, I
had to open the picture in the Photos app and email it to a special
address that Flickr had associated with my account.

Negatives of this approach? Impossible to use for more than a couple of
images at a time, primarily, but also, annoyingly, the Mail app on the
iPhone scales and recompresses the JPEG images before sending - and it
strips them of their EXIF data, too.

So I was mildly displeased, but there was a way I could get it to work,
kinda.

Then the iPhone got cracked wide open. People started figuring out how
to write third-party apps and get them installed on their iPhones, and -
to be honest - the UI for it, via Installer.app, is - even though it's
not from Apple - better than anything I've seen on any other mobile
phone, ever.

The Friday before last (September 7th), I decided it was time to take
matters into my own hands. Finally learn Objective C. Start writing my
dedicated "Push all of the images in my Camera Roll to Flickr, right now
dammit" application. And I got a pretty good start! Got the toolchain to
build working iPhone apps, and that only took a few hours. Started
reading through Flickr's API documentation. Started implementing some
functions that didn't require authorization to call - learning how to
use Flickr's REST API, basically. Once the first couple of
unauthenticated calls worked and did what I expected, I knew it would
only be a matter of time before I had my app working.

And then someone pointed me to [iFlickr][].

My first thought was "Dammit, somebody beat me to it." And I was a
little depressed for a bit.

I downloaded it and tried to get it working. No offense to the iFlickr
devs, but they clearly didn't put a lot of thought into the user
experience (or if they did, I posit that their ideas about "good user
experience" work completely differently from mine). I didn't end up
getting it to work, but it's open-source, right?

Naturally, my next thought: "Well, I've been working on mine, and this
doesn't really do what I wanted. But... maybe I can steal some of their
code at least!"

And then I looked at the code.

My eyes still burn a little bit from that. That ... that was not a good
idea. I've had much better ideas in the past.

I worked on this for the next few nights, realized that I could
completely avoid the messy minitoken crap by using the "Desktop app"
authentication mode from Flickr, deleted all of my code that dealt with
mini-tokens, and the other night, I finally got it to actually upload
pictures to my Flickr account. (My friend [Cliff][]'s help was so
valuable as to be incalculable.)

I'll post more technical details later, but the important thing is:
[MobilePushr][] is out. The UI is going to get a lot of love in the next
few days, because the current one doesn't provide nearly enough
feedback, but as of right now, MobilePushr lets me do something that
I've wanted for almost three months.

I can push my JPEGs directly from my iPhone to my Flickr account with
the push of a single, giant red button. (And so can you! If you go
download it and install it on your iPhone, that is. Assuming you have an
iPhone.)

Also, of course, MobilePushr is Open Source / Free Software, released
under the GPLv2. If you use git, you can look at my code by cloning
git://mg8.org/MobilePushr and poking around.

The really awesome thing about all of this is that, through Flickr, I
can see how many people have given my app permission to link to their
account, and in the first twelve hours alone over a thousand people have
activated support for MobilePushr on their Flickr accounts.

I don't even have words to describe how awesome that makes me feel.

  [iFlickr]: http://http://code.google.com/p/iflickr/
  [Cliff]: http://cliffhacks.blogspot.com/
  [MobilePushr]: http://mobilepushr.jottit.com/
