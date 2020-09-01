+++
title = "Fuchsia OS: The State of Operating Systems"
date = 2019-01-28
updated = 2020-09-01
+++

In a world where every device is connected, an operating system to connect them all.

Google's been making a new operating system from scratch for a few years now (well, it actually has a foundation in something new and uses a bunch of new technologies for a lot of foundations, but whatever).
You probably haven't heard of it unless you like reading one of the Google-focused websites or you've been looking deep into Google's projects that they post online.

Why?

Well, one line of reasoning is the age of current operating systems.
None of the major operating systems have been rebuilt ground-up recently, they've only been iterated on and have seen some design changes.
As the major OS companies (Apple, Google, Microsoft) have been rushing to keep up with each other, they've been forced to update their code instead of redesigning it.
While that's something that happens everywhere, and is usually not problematic, down the line you'll end up with a program with a lot of code, which can get quite out of hand.
Linux, which is what Android and Chrome OS is built on, is 15 million lines of "privileged" code.
Zircon, which is the Fuchsia equivalent, is only 10's of thousands(1).
That's way smaller than even Apple's base code, which is about 1 million lines of code(2).
The smaller code base means that people can better go through the code and find errors whenever they come across bugs.
It means new features won't be spread out across several files, all being redundant because one programmer knows of one area of the code and uses that for their feature, while a different programmer knows another area of the code and uses that for the same feature.
And so on.

There's also going to be increased security on Fuchsia.
All programs will be separated from each other; they won't be able to directly manipulate anything that isn't within their own dedicated "space"(3).
This, in combination with a limited number of tools for malicious developers to use(4), means Fuchsia users will be far safer than anything running Linux, and even Apple's software won't be as secure.

Lastly, there's the convenience.
It appears as though the developers of Fuchsia are trying to make Fuchsia be as convenient as possible to everyone.
For device manufacturers, this means that few changes will have to be made to Fuchsia to get it up-and-running.
For custom software developers, the code is online and directly accessible(5), and you can even load up Android on top of a part of Fuchsia(6) if that tickles your fancy (please don't do that).
For app developers, creating an application for Fuchsia also means creating an application for Android and iOS (more on that in my next article, I think).
For end users, a beautiful user interface that works fluidly and allows apps to share information without being opened(7) (think widgets, but with more information accessible(8)).

So, date?
Well, nobody's really sure (the developers probably have an idea, and definitely have a plan, but haven't shared with us).
The theory I find most likely is that Fuchsia will first come to IoT devices, replacing what's on Chromecast, Google Home, and any other devices Google can get Fuchsia to work on first.
Phones will probably come a year or two later.
And even then, it may not be called "Fuchsia" when it hits shelves: it could be called "Android" or "Thanos" or any other name Google chooses (I'm willing to bet not Android).
Just a theory.

Of course, there's so much more to Fuchsia than I talked about, and new things are being added by the day.
These are the top 3 favorite things that I've come across, which I'm really excited about.


1. Zircon and Linux line counts according to Reddit user bartturner, who has a great comment [here](https://www.reddit.com/r/Fuchsia/comments/aewu7a/what_can_we_understand_from_fuchsia_architectural/edw2jih) for the interested.
2. Got the XNU line count [here](https://flylib.com/books/en/3.126.1.18/1/), citing the Darwin package.
3. For more in-depth information on Fuchsia sandboxing, click [here](https://fuchsia.dev/fuchsia-src/concepts/framework/sandboxing).
4. [Linux syscalls](http://man7.org/linux/man-pages/man2/syscalls.2.html) vs [Zircon syscalls](https://fuchsia.dev/fuchsia-src/reference/syscalls). Look at link from 1 for a bit more analysis.
5. Click [here](https://fuchsia.googlesource.com/) for source code.
6. It hasn't been done, but with Google's [machina](https://fuchsia.googlesource.com/garnet/+/master/bin/guest/) API, should be possible (9to5Google article [here](https://9to5google.com/2018/06/15/fuchsia-friday-machina-brings-support-for-running-linux-on-top-of-fuchsia/))
    - EDIT: the machina link no longer works, and there is no reference to it. Instead, it seems that there is now a hypervisor syscall that allows a guest OS to run closer to the native level.
7. Look at the Armadillo UI [here](https://9to5google.com/2017/05/10/fuchsia-os-hands-on/).
8. Using [entitities](https://fuchsia.googlesource.com/peridot/+/master/docs/modular/entity.md?autodive=0%2F%2F), article [here](https://9to5google.com/2018/02/09/fuchsia-friday-entities/). Also, [Tom Cruise](https://fuchsia.googlesource.com/peridot/+/master/docs/modular/agent.md?autodive=0%2F%2F).
    - EDIT: the entities link is broken, and the Tom Cruise link points to a framework that is being deprecated. Instead, [sessions](fuchsia.dev/fuchsia-src/concepts/session/introduction) are being introduced.

[Originally posted to LinkedIn](https://www.linkedin.com/pulse/fuchsia-os-state-operating-systems-colton-donnelly/)

** Edited to update links.
