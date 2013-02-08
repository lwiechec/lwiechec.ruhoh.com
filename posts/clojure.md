---
title: Clojure
date: '2013-02-07'
description:
categories:
tags: [coding,clojure]

---

Recently I decided to clean up my '.emacs' file (after upgrade to Emacs 24 I decided
to try out el-get for package management -- but that's the subject for another post)
and after trying out lots of Emacs Lisp code, I noticed a certain 'cleanness' of
that code. Of course, you have plenty of parentheses (not everyone like's it)
and the different notation than what I was always using in languages like Java, C, Perl
etc.

It has also a bit to do with my colleague Bart's strive to use Scala and to learn
some functional language. Clojure is also functional and I think it will be easier to
learn for me; because it looks different from Java, I think it would be easier
to handle the 'functional' part of it.

The other cool thing about Clojure is that, because it is JVM-based, it can easy
integrate with existing Java code base, something that is quite close to my heart.
The classes can be accessed and used in the Clojure code.

Initially I wanted to experiment with Clojure in its REPL mode, just by running
its simple console utility ('java -cp clojure.jar clojure.main'). But this console
tool was very basic and lacked 'readline'-like behaviour (completion, history etc)
that I am used to (and which is really handy when you are learning - especially
completion). It turns out that a simple build tool for Clojure called
[Leiningen](https://github.com/technomancy/leiningen) that provides spiced-up
version of the REPL tool. I didn't have time to explore it fully but it looks like
it can also export the build to Maven which is a good thing (because I am used
to this build tool).

There are also other goodies like special modes for Emacs that can talk to
REPL server inside 'lein' tool. These are quite handy because - first of all they
implement the 'do not leave your favourite editor' principle so dear to all Emacs users
(haha) and second - offer very cool interface, with completion, syntax highlighting
etc. The 'clojure-mode' offers even also an easy way to edit and run tests in Clojure
from the buffer; the tests need to use
[clojure.test API](http://richhickey.github.com/clojure/clojure.test-api.html) and
the faling tests are highlighted in the buffer (using overlays). This is quite cool
thing, 'malabar-mode' should also have something like that :).

Having installed all that 'goodies' I am ready to start the language - having some
background in Emacs Lisp should help.