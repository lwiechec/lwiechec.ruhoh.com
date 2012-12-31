---
title: Accessing Ipod Nano 5th generation under Linux
date: '2012-12-23'
description:
categories:
tags: [linux, ipod]

type:
---
Here we go again
----------------

I noticed that this subject comes back like a boomerang :) The ipod devide mentioned
in the title was a present from my wife and, as most people feel, it's a good-looking
piece of engineering - that comes with some 'gotchas', introduced by Apple to lock
you in. Namely - the need to use iTunes software to handle everything concerning
ipad (I'm not bitching *too* much, after all they make most of the money through
the store selling music).

I have one Mac machine on loan so I was able to manipulate the contents of it
but the iTunes application is quite hard to work with; it tends to be super slow
when the media are not local to the iTunes (I have them on NAS). Besides it's impossible
to script anything using simple Unix command-line tools, the way I would prefer it the best.
After struggling a bit with 'the normal Apple consumer way' I got a bit impatient
and decided to explore the alternatives.

Trying to use existing tools
----------------------------

From reading the forums, it looks that approaches using 'standard' media players (like Amarok etc.)
will not work (besides, on my workstation I don't use KDE that Amarok depends on and I wouldn't
want to install the whole hunderd-of-megabytes KDE base just for that). After further searching
I have found out that the latest [gtkpod](http://www.gtkpod.org) contains the code
that can finally 'talk' with Ipod Nano 5G. After quick test on my (outdated) Ubuntu installation,
the one shipped with the OS is too old to handle writing to the device (seems to be reading
the contents, though).

So I grabbed the sources and compiled the 'libgpod' library (see for the instructions
[here](http://ubuntuforums.org/showpost.php?p=8573724&postcount=39) on how to get it going
but I think they are incomplete, as I had to extract some extra packages, like 'sqlite3-dev'
and 'libpname-dev'). After fixing this, I managed to get the 'libgpod' library that can talk with
the ipod (for now, compilation of the GUI utility 'gtkpod' wasn't attempted as it requires GTK+ 3.0
and I don't have it easily available on my outdated Ubuntu destribution).

The documentation to the library is avaliable on [its web page](http://www.gtkpod.org/libgpod/docs
/).

The vision
----------

While doing all that I came at the conclusion that the best solution for me would be
to use 'libgpod' and create a file system that will enable accessing the ipod in 'normal'
(eg. via the mount point) way. I can imagine that the structure of the mount point like this:

    <mount point>
      Artists
        artist1
        artist2
  	...
      Albums
        album1
        album2
	...
      Playlists
        playlist1
	playlist2
	...
      Podcasts
	podcast1
	podcast2
	...
      System (? - equivalent of '/proc' filesystem on Linux)

Others for more fancy features of ipod (contacts, photos etc) could come later.

[FUSE project](http://fuse.sourceforge.net/) provides a relatively-easy way to write such filesystem.
It even has language bindings to other than C but as 'libgpod' doesn't, the whole thing would have
to be written in C. Last time I did it, uh-oh. 20 years ago. Maybe it's time to refresh the memory!

Latest update
-------------

The code is now [published on Github](https://github.com/lwiechec/fuseipod). It's of course not ready for
public consumption yet :).