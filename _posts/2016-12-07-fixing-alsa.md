---
layout: post
title: Fixing ALSA once and for all
---

If you have ever done a bare bones installation of a linux distro like Debian on a modern machine, you should know that the soundcard does not work out of the box. Nothing, not even a beep will come out of your linux box. If you try to play something, or try executing "speaker-test" and the terminal will spew something on the lines of...

    ALSA lib pcm_dmix.c:1022:(snd_pcm_dmix_open) unable to open slave
    aplay: main:722: audio open error: No such file or directory

Actually, I included the above lines so that people currently facing the issue can undestand that I am trying to deal with the same issue :D

This happens because, modern machines have two sets of sound cards. One on the motherboard and other on the Intel HD Graphics GPU. When ALSA sees them, it gives higher priority to the one onboard the processor, ie. it makes the so called "Intel HDMI Audio" the default sound card. Apparently, this is not what we want.

What you have to do is pretty simple. Become root and open the file "/etc/modprobe.d/default.conf" with your favorite text editor, then insert the following
line:

    options snd_hda_intel index=1

Reboot the system, and the soundcard should work fine :)
