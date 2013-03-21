---
title: build system notes
published: true
---

We had a discussion in \#kde-devel earlier about what KDE's requirements
for a build system are. What are the current problems we have with
autoconf/automake/libtool? What features do they provide that we really
care about? How hard would it be to replace any/all of them with things
that suck less?

I took notes of the discussion. They're below; I'd like to get more
feedback on this.

(One of the first points that I'm sure someone will make is "auto\* is
cross-platform! We need to support KDE on platforms that aren't Linux!"
etc. Look, we realize this. However, auto\* provides lots of problems
for us on platforms we do care about, including MacOS X and Windows.
(Ask RangerRick or js about them on IRC, or email them.)

Just because we're using auto\* and friends doesn't mean that our code
works; as a matter of fact, RangerRick noted that so far, all of his
issues with the Mac port of the work-in-progress KDE4 have been build
issues, and none of them have been code-related yet.

This is clearly a problem and since KDE4 is an aggressive new major
release, we should solve it in the KDE4 timeframe. We don't want to have
to wait until KDE5 for a build system that doesn't suck, do we?

Without further ado, the notes from the discussion.

Must support:  

-   generating binaries (duh)
-   generating shared libs (on all ELF platforms + MacOS X; Windows?)
-   icon installation
-   uic, moc, KConfigXT, etc
-   GCC visibility
-   automatic dependency resolution
-   manual hints for dependency resolution
-   flex/bison
-   non-recursive (flat) builds
-   --enable-final
-   builddir != srcdir
-   simple to the point of being learnable within 5 minutes
-   kdeinit support (?)
-   multiple build targets (libfoo, libbar, libbaz) in one file
-   --compile-slots, like in unsermake
-   pkg-config support
-   support rpath sanely
-   ability to link & run uninstalled binaries
-   easily integrated into KDevelop
-   'admin' needs to be shipped in KDE instead of in src of each app (if
    we keep the 'admin' dir, that is)

</p>
Would be nice, but not necessary:  

-   having a standard and distributed build system and test suite
-   ability to build from svn:/trunk/KDE

</p>
Thoughts?
