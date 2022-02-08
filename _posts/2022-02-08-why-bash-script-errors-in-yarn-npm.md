---
layout:     post
title:      'Why my Bash script ran in yarn/npm is throwing errors?'
date:       2022-02-08 11:30:00
author:     Niklas Engblom
summary:    How to fix an erroring Bash script when ran in yarn or npm
categories: Tech
thumbnail:  terminal
tags:
 - linux
 - scripting
---

I've encountered this error a few times in different projects. Unfortunately I usually tend to forget why this is happening, because it's not such frequent error. Now I decided to write it down, at least as a note for myself. Hopefully it helps someone else too!

Without further ado, when running a script via yarn, I get something like this:

```bash
./scripts/my-script.sh: 24: [[: not found
```

But when running in my terminal, the error does not occur. Pretty peculiar indeed. This is usually due to yarn script defined as `"domagic": "sh ./scripts/my-script.sh"`. What that does is, it is forcing the script to be run with `sh` interpreter. Since I'm using Linux Mint, this means it will be ran in Dash (Debian Almquist Shell) instead of Bash, even though the script file has a shebang `#!/bin/bash`. So [what is Dash and why it is set as a default shell in Linux Mint? Here's a writing in ubuntu wiki](https://wiki.ubuntu.com/DashAsBinSh) which also applies to Linux Mint, because it uses ubuntu as a base.

How can I see what shell my Linux distro is using? It's rather easy with `readlink` and `which`. `readlink` is used to read symbolic links and `which` locates a command, thus by running `readlink $(which sh)` you'll get the interpreter used for `sh`. For me it outputs `dash`.
