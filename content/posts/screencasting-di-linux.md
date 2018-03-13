---
title: "Screencasting Di Linux"
date: 2018-03-13T01:54:13+01:00
---

Screencasting di Linux

<img class="alignnone size-large wp-image-16" src="https://hammashamzah.com/wp-content/uploads/2018/02/Selection_056-1024x576.jpg" alt="" width="840" height="473" />

Currently, I have a project to build educational videos through screencasting. As a linux user, it is (always) not easy to have a decent apps that can handle my needs well without too much hassle. But I didn't want to move to another OS just because a single stuff didn't work. After some googling, I found the best app to do screencast is <a href="https://launchpad.net/kazam">Kazam</a>. Although this app seems not being maintained anymore, it is still working good with some caveats. Here is some fix that I did to make this app works better:
<ol>
 	<li>Set <code>floating enable</code> on i3wm setting
Add this line to the <code>~/.i3/config</code>: <code>for_window[class="Kazam"] floating enable; focus mode_toggle</code>. This little fix makes the kazam float by default so it doesn't distract your window layout in i3.</li>
 	<li>Change the naming mechanism
When autosave set as enable, Kazam will write a file to the saving directory with a filename: <code>[Filename_prefix]_[counter]_[format]</code>, where counter will be set as last recorded file counter + 1. Whenever such previous file doesn't exist, the counter will be resetted to zero.
It sucks since I synchronize the recording files using rsync. The problem is, rsync doesn't resolve filename conflict. I don't want rsync to overwrite my old files with the same counter number from my local directory. I made a fix by hardcoded saving filename format with <code>[Filename]_[date]_[format]</code>. I will make a repo for this fix on my <a href="http://github.com/hammashamzah">github</a> later (Remind me, please :D)</li>
 	<li>What's next? Still many things that can be improved from the app. I will try to update this post if I make a fix to the app.</li>
</ol>