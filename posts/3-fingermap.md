---
title: Fingermap 
date: 2023-11-16
tags: ['web app','open source']
---

__A few months ago__, I committed my first open source contribution.

This may surprise as I've worked in software for a number of years.

While my previous employers have not been contributors themselves, the real reason that I haven't contributed yet is simply that I've never tried to.

Indeed, the large and welcoming ecosystem for open source software today leaves little excuse to not take part. As noted on <u>[GitHub's blog](https://github.blog/2022-11-17-octoverse-2022-10-years-of-tracking-open-source/)</u>:
> "In 2022 alone, developers started 52 million new open source projects on GitHub—and developers across GitHub made more than 413 million contributions to open source projects."

This is not to say that barriers to entry don't exist, but that there exists, in fact, a vast array of opportunities for developers of many different skill levels across a multitude of domains.

Which brings me to the project in question.

#### <u><b>[MonkeyType](https://monkeytype.com/)</b></u>

Monkeytype was created in 2020 as a single-developer passion project to make an online, minimalist, and customizable typing test. Since then it has grown rapidly, with <u>[365 million tests taken, an active Discord server, and hundreds of supporters and contributors](https://monkeytype.com/about)</u>.

<img src="/images/3-fingermap/monkeytype-home.png"  width="600" alt="monkeytype app screenshot" style="">

I'm a big fan of Monkeytype for my own typing practice, with records to date of 135wpm over 15 seconds and 117wpm over 60 seconds (with 100% accuracy). When I saw that Monkeytype is <u>[open-source on Github](https://github.com/monkeytypegame)</u>, I saw it as a perfect opportunity to contribute.

Looking for candidates for improvement, I observed that the subproject <u>[Fingermap](https://github.com/monkeytypegame/monkeytype-fingermap)</u>, a keyboard finger map editor, exhibited multiple issues I would happily take on, including:

- An inability to select keys with keypress.
- A lack of a mobile-friendly responsive layout.
- A diverged style as compared to the main site.

<img src="/images/3-fingermap/fm-old.png"  width= "600" alt="fingermap old screenshot" style="">

I started by joining the Monkeytype Discord, creating an issue on the repo, forking, and working up a draft solution for keypress selection. I was updating this code as a fun exercise, so I wasn't concerned with negotiating the changes in advance with the project owner _Miodec_. I hypothesized that providing a hosted demo of the updates would offer a strong introduction and elicit a faster response.

<img src="/images/3-fingermap/discord-msg.png"  width= "600" alt="discord message screenshot" style="">

The response was prompt and positive!

_Miodec_ expressed interest in the update and suggested additional changes. Over the course of a week and a few iterations, updates addressing all items of interest were PR'd and merged to the main repo. 

<img src="/images/3-fingermap/fm-new.png"  width="600" alt="fingermap new screenshot" style="">

<br />
<br />

<img src="/images/3-fingermap/fm-new-mobile.png"  width="300" alt="fingermap mobile new screenshot" style="">

Some noteworthy items:

- __Responsiveness__ required a new mobile header as well as a mechanism for keyboard resizing. This proved interesting, as the existing code was resistant to standard sizing mechanisms. In particular, preserving the aspect ratios on resize was tricky given the layout and markup. To solve this, I created a wrapper that I call an _Aspect Ratio Box_ - scaling smoothly while preserving aspect ratio and interactivity. I've posted a <u><b>[demo](https://codepen.io/TheRyjo/pen/ZEmRmgm)</b></u> to Codepen.
- __Keypress selection__ required changing other shortcuts to remove conflicts. Previously, keys 1-10 had been used for finger selection. The shift key also had overlap as a modifier key, which I resolved with logic to differentiate between quick press (selection) and hold (modifier).
- __Header updates__ entailed some questions about icon usage, label presence, and styling. These were ultimately resolved with a healthy deference to the main site.

At the time of writing, Fingermap is hosted at <u>[https://fingermap.monkeytype.com/](https://fingermap.monkeytype.com/)</u>

I've also separately hosted snapshots for:
#### <u><b><a href="https://storage.googleapis.com/ryjo.io/fingermap-before/index.html" target="_blank">Before</a></b></u> | <u><a href="https://storage.googleapis.com/ryjo.io/fingermap-after/index.html" target="_blank">After</a></u>

Thank you for reading!
