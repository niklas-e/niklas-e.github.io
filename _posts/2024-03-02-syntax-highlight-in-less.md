---
layout:     post
title:      'Syntax highlighting in less'
date:       2024-03-02 12:00:00
author:     Niklas Engblom
summary:    How to add syntax highlighting into less tool in Linux
categories: Tech
thumbnail:  terminal
tags:
 - linux
---

If you have had to read text based files in Linux environment, you most likely have stumbled upon a tool called `less`. It's very powerful tool, but I quite often wish there'd some level of syntax highlighting when viewing e.g. shell scripts or something similar.

Today I decided to research the topic a bit and found out it is indeed possible to use different styles with less. The most feasible option for me was to use external tool called `pygmentize`. It is a generic syntax highlighter created with Python.

Here's how I made `less` to use syntax highlighting offered by `pygmentize` always when I use `less`.

1. Install `pygmentize` by running `sudo apt install python3-pygments`
2. Select your favorite theme from [the built-in themes](https://pygments.org/styles/){:target='_blank'} (you could also download or create your own). For this post I'll use my favorite: one-dark
3. Add `export LESSOPEN="|pygmentize -P style=one-dark -g %s` and `export LESS="-R"` to your shell profile file (e.g. for bash: `~/.bashrc`)
4. To use in your current shell session, remember to run `source <shell profile file>`, for example on bash `source ~/.bashrc` - instead of this you could also just restart your terminal
5. Open a file with `less` - it should have syntax highlighting now!

{% include video.html filename="less-with-syntax-highlight.webm" type="video/webm" %}

After finding out it is this simple, I wish I had searched for this much earlier since this is a really good improvement 😅

Thanks for reading and enjoy your more colorful `less`!