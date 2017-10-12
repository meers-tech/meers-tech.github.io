---
layout: post
title: Handbrake not shutting down ubuntu after encoding
tags: Ubuntu, Handbrake, linux, Shutdown, Prompt
---

I recently had an issue where Ubuntu 16.04.3 wasn't shutting down after Handbrake finished encoding its files. This was my first steps into using Handbrake on Ubuntu, had had no idea it it was a bug, accepted, or Ubuntu related. Basically, I would wake up in the morning and the computer would be on, after signing into my user account, I would find handbrake with a dialog box countdown stuck on 1 second. It wouldn't do anything until I clicked cancel and then the computer would shut down.  

I googled it and nothing came up. So I decided to try a quick encoding run and see if it was handbrake hanging or something else. Sure enough after a few minutes of a small file encoding the Shutdown Countdown popped up and at 1 Second to my suprise Ubuntu popped up a prompt for shutdown. This prompt was a “are you sure you want to shutdown” kind of prompt with a few options. Seems we found what was stopping the shutdown; with no selection the computer would just sit. Just to push it a bit further I waited for the screen to time out. Sure, enough as soon as I logged back in I was greeted with the sight of a “frozen” handbrake prompt at 1 second and the Ubuntu shutdown prompt had disappeared. 

To disable the Ubuntu prompt at shutdown you simply copy and paste the bit of code below into terminal

`gsettings set com.canonical.indicator.session suppress-logout-restart-shutdown true`

Now no more wasting power at night with an idle computer.
