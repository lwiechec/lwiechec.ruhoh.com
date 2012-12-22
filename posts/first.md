---
title: First!
date: '2012-12-22'
description:
categories:
tags: []

type:
---
Sooo... I have made another attempt to start writing some thoughts down about more or less interesting
stuff I am working on (also in my free time). Two previous attempts to have blog failed - I used Blogger.com
platform but I guess - I had nothing interesting to say :). I hope with this one it will be better!

This time I wanted to be more hackerish and went to explore 'blog as a generated webpage'. Initially,
I though about using [Jekyll](https://github.com/mojombo/jekyll). But then I have found out about [Ruhoh](http://ruhoh.com/)
written by JD, the author of [Jekyll Bootstrap](http://jekyllbootstrap.com/). As Ruhoh is his new project,
and that he claims it's cleaner, better etc - I will give it a go. Especially that it nicely integrates with
Github's webhook - so each time a change is pushed to the server, the blog is updated at lwiechec.ruhoh.com. Neat!

ruhoh runs on Ruby and as I know very little about it, it took me a while to get it going. For some reason,
installing of ruhoh gem took a while (mwybe the website hosting gems is slow, maybe the dependencies resolution
was slow); also - to make it work I needed to use [RVM](https://rvm.io), tool for easy switching between
various Ruby installations. This is another very cool project, with quite cool/minimalistinc installer that I
really like (installation is done by the shell, you just pipe it through it using curl:
`$ curl -L https://get.rvm.io | bash -s stable --ruby'`. Really neat indeed). Due to the fact that RVM's scripts
are in '~/.bash_profile', to get it initialized I need to run `/bin/bash --login` to get it executed.
This is quite unhandy so I think I will move it to ~/.bashrc.

ruhoh also provides a nice 'preview' mode for the writeups; executing `rackup -p <port>` from the blog's
main directory will start a small HTTP server with the blog on the `localhost:<port>`. This is handy for
inspecting the posts before pushing it to the hosted blog. Using `ruhoh` application the user can control
creation of pages, directories etc.

Well, that's all for the first post!