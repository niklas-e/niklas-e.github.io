---
layout:     post
title:      Setting up this blog
date:       2020-12-05 10:00:00
author:     Niklas Engblom
summary:    Setting up this blog 
categories: General
thumbnail:  vcard
tags:
 - blog
 - jekyll
 - github pages
---

I had thought of setting up a blog where I could share things I encounter at work and in my home projects. And while I'd be at that, why not share all other interesting stuff and insights. There were just these common problems like finding the time to think about it and making the initial content. Also what platform and so on...

One day I noticed a post in Reddit and thought I'll give a short answer. After scribbling for a while I noticed the short answer had grown to a little more. When I hit the send button, I thought, well, that is already good enough for a short blog post. Sure enough, a little bit later I had this blog up and running. I decided it's better to just set it up and see if I'll get any writings done or not. I could certainly say at this point, I won't get them done by waiting for the right time - it has been several years since the first time I thought about setting up a blog.

So, time to get sh*t done! I wanted something super simple, no tricky platform setup and ideally markdown based content. By quick searching I was already checking prerequisites for Jekyll and GitHub Pages. I had pretty much all in place, because I'm using GH and I've done bunch of web dev stuff on my Linux Mint machine.

Here's the workflow:

1. Check and install missing prerequisites from [Jekyll docs](https://jekyllrb.com/docs/){:target='_blank'}
2. Create a new site with Jekyll command `jekyll new niklas-e.github.io`
3. Download and extract a cool theme from one of the sites listed in [Jekyll resources](https://jekyllrb.com/resources/){:target='_blank'}
4. Copy the theme into the Jekyll site folder you created in step #2
5. Tweak configuration file in the folder
6. Create a GH repository with name `niklas-e.github.io` and commit & push the site into that repo

Now I had the platform setup up and running at [niklas-e.github.io](https://niklas-e.github.io){:target='_blank'} - great!

Everything was falling into place and only missing thing was the content. Thus I wrote a short intro on the frontpage and [my first blog post]({% post_url 2020-12-03-from-software-developer-to-architect %}){:target='_blank'} based on that Reddit answer. I was pretty happy at this point, this setup didn't take much of my time and the writing process was just as simple as I wanted.

Though one thing bugged me, and you might guess what it was. It just didn't feel as personal as it should with that out-of-the-box GH pages URL. Therefore I configured a custom domain for my blog, which was actually delightfully easy to do and did not require any paid plan to do so.

Have you thought about setting up a blog; or have you already done it and have you enjoyed it?
