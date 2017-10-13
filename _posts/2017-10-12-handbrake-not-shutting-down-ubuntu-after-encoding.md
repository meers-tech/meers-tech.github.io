---
layout: post
title: Handbrake not Shutting Down Ubuntu after Encoding
tags: Ubuntu, Handbrake, linux, Shutdown, Prompt
---

I recently had an issue where Ubuntu 16.04.3 wasn’t shutting down after Handbrake finished encoding its files. This was my first time using Handbrake on Ubuntu, so had no idea it was a known bug, a new bug, setting related or Ubuntu (OS) related. Basically, I would wake up in the morning and the computer would be on, after signing into my user account, I would find handbrake with a dialog box countdown stuck on 1 second. It wouldn’t do anything until I clicked cancel on the dialog box and then the computer would shut down.

I googled it and nothing came up with nothing but similar windows issues but no Linux. So I decided to try a quick encoding run and see if it was handbrake hanging or something else. Sure enough after a few minutes of a small file encoding the Shutdown Countdown popped up and at 1 second to my surprise Ubuntu popped up a prompt for shutdown. This prompt was an “are you sure you want to shutdown” kind of prompt with a few options. Seems we found what was stopping the shutdown; with no selection the computer would just sit. Just to push it a bit further I waited for the screen to time out. Sure, enough as soon as I logged back into the user I was greeted with the sight of a “frozen” handbrake prompt at 1 second and the Ubuntu shutdown prompt had disappeared. A look at the Ubuntu Wiki and there is a simple way to turn that prompt off.

To disable the Ubuntu prompt at shutdown you simply copy and paste the bit of code below into terminal:

`gsettings set com.canonical.indicator.session suppress-logout-restart-shutdown true`

Now no more wasting power over night with an idling computer.
