---
layout:     post
title:      'Help! I forgot my WSL password'
date:       2022-09-19 09:00:00
author:     Niklas Engblom
summary:    How to reset your WSL (Windows Subsystem Linux) sudo password easily
categories: Tech
thumbnail:  terminal
tags:
 - windows
 - linux
 - scripting
---

Ok, I'm pretty sure I am not the only one who has set up their WSL (Windows Subsystem Linux) password and thought something like "yeah, I'll surely remember this, it's so simple and easy to remember". Just to notice a couple weeks later you indeed forgot the password, because you didn't use it actively. Also maybe because it was so easy (and at the same time different from other passwords?). Before judging me completely, I have to say that I do use credentials manager to keep my credentials in a good place. Then again, there's times when you just think "meh, I don't need to save this, it's so simple" or simply forget to save it. Okay, okay, enough of rambling; let's get to the point 😅

Notice! There's also short video guides at the end of the post

## Changing your WSL password for default distribution (or when you only have one distribution installed)

1. Open Command Prompt (Hit `Windows key` on your keyboard and type in `cmd`) - following steps are executed in the Command Prompt
1. Run `wsl whoami` to get your WSL username
1. Run `wsl --user root`
1. Run `passwd <your-username>` and enter a new password for your user
1. Run `logout` or hit `Ctrl`+`D` (will log out as root)
1. Now your password has been changed

## In case you have multiple WSL distros installed

1. Open Command Prompt (Hit `Windows key` on your keyboard and type in `cmd` and launch `Command Prompt` by hitting `Enter`) - following steps are executed in the Command Prompt
1. Run `wsl --list` to get your WSL distribution name - the list shows distribution names in `Ubuntu-22.04` format, but for the next steps you have to transform it into e.g. `ubuntu2204` (replace `<your-distro-name>` with this)
1. Run `<your-distro-name> run whoami` to get your WSL username
1. Run `<your-distro-name> run --user root`
1. Run `passwd <your-username>` and enter a new password for your user
1. Run `logout` or hit `Ctrl`+`D` (will log out as root)
1. Now your password has been changed

## And here's a recap in form of short videos

Reset sudo password in WSL:
{% include youtube.html video_id="mnwgz-TnfxE" %}

Reset sudo password in WSL when you have multiple Linux distributions installed:
{% include youtube.html video_id="QhzSq6LEUQM" %}
