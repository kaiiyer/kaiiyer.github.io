---
layout: post
title: Some very useful *NIX tools
---

Linux has no dearth of tools for getting your tasks done. The actual problem is the proliferation of packages that can make it hard for finding the  right tools for the job. Once in a while you come across a gem that makes your life a whole lot easier. Below is a list of gems I collected along my journey through Linux. Hope it will serve you as well.

Midnight Commander [mc]  
The quintessential filemanager for Linux, has the two pane styled interface Supports FTP, SSHFS, provides you with plethora of options for tweaking and still starts under half a second.

kill [kill]  
Kill a misbehaving application, the command does not accept the target application name, rather you have to use the PID

killall [killall]  
Allows you to kill an application using it's name

xkill [xkill]  
Turns your cursor into an X. Point it at the GUI application you want to kill and simply click the left mouse button.

wavemon [wavemon]  
Shows you the strength of a wifi network from where you are standing. Very useful for mapping the reception of your network.

feh [feh]  
Very lightweight picture viewer that can be conveniently launched from the terminal. Use the "-F" switch for full screen viewing.

pidof [pidof]  
Returns the Process ID of a process. Very easy way to find out if a process running. Can also be useful to kill the specific process, ie. [kill 'PID returned by pidof command']

history [history]  
Shows the command history in terminal

Secure Shell [ssh]  
Connect and execute commands on a remote system.

lm-sensors [sensors]  
Prints the system temperature

reset [reset]  
Some weird command messed up your terminal? This is the way out.

Secure Shell File System [sshfs]  
Mount the drive of any computer running an SSH server.

htop [htop]  
The top system monitor on steroids :)

scrot [scrot]  
Simple lighweight screen capture utility with plethora of options to play
with

lsof [lsof]  
The computer wont allow you to unmount a drive or delete a file If some program is still accessing it. The solution is to use lsof command to find the culprint. Combine it with kill to finish the misbehaving application once and for all.

Network Manager Terminal UI [nmtui]  
Allows to manage the Network Manager from terminal, very convenient.

when [when]  
The ultra minimalist calendar application that actually works.

moc [mocp]  
Music and Radio player for the terminal, easy to use.

nano [nano]  
The fuss free terminal text editor. It has the added advantage of being preinstalled with most distros these days.

Vim [vim]  
This list wont be complete without the classic text editor for *NIX systems

emacs [emacs]  
The text editor for people who hate vim. You may find yourself running out of fingers on this editor :)

xbacklight [xbacklight]  
Control the backlight from terminal. Only works on Intel systems at the moment.

mplayer [mplayer]  
It is a media player. It runs from terminal and can give the other players a run for their money.

UDisks [udisksctl]  
allows you to mount partitions with Read/Write access for normal user.

mutt [mutt]  
Probably the best email client ever invented

getmail [getmail]  
fetches mail for the best email client ever invented

youtube-dl [youtube-dl]  
Downloads youtube videos from terminal and looks good while doing it.

Transmission Daemon [transmission-daemon]  
The torrent client with a web interface, access 'localhost:9091' for the interface. A fair amount of configuration will allow you to run the service as a normal user, and enable you to access the client from remote computers.

tar [tar]  
Creates and extracts tarball archives.

pipe [command_1 | command_2]  
not really a command, but a very useful tool nonetheless. Transfers the 
output of one command into the input of another

TLP  
Does your battery life suffer under Linux? This might just be your solution.

grep [grep]  
Probably the most used command in the world. Used to find needles from haystacks. Use it with pipe

dmesg [dmesg]  
Prints the kernel ring buffer. For the uninitiated, this command prints all the mess the kernel has to deal with on your system. Combine it with grep to find what you need.

wtf [wtf]  
Decodes the chat jargon that people have been using for a while

less [less]  
Tried running dmesg? The output of a command might overwhelm you. Less allows you to browse through all that information using just the arrow keys.

cal [cal]  
prints the calendar.

alsamixer [alsamixer]  
Controls the Advanced Linux Sound Architecture. In simple terms, volume 
control :D

ping [ping]  
Find if a system is online.

man [man]  
The manual command (of the RTFM fame). append it with a space and command name to get your share of wisdom.

wget [wget]  
One hell of a command. Can be used for downloading things from the internet. 'things' can be a single file, group of files or an entire website.

top [top]  
For systems which lack htop

authbind [authbind]  
Allows normal user to run a web server at port 80

cdw [cdw]  
Technically an ncurses frontend to some of the bomb-proof terminal cd burning commands, this is the cd writing program to beat when it comes to stability. NOTE: Not so stable when it comes to DVD writing!

ArandR [arandr]  
A lightweight GUI for XrandR. Allows you to setup multiple monitors or projectors. Very useful if you are using an environment which lacks inbuilt display preference application.

trickle [trickle]  
Allows you to control the network bandwidth an application can use. Use it with wget and youtube-dl to avoid people yelling at you.

lscpu [lscpu]  
Lists essential information of the host CPU. A universal command, very useful when working on an unfamiliar system.

IOTop [iotop]  
A very useful command which lists the processes along with their IO rate. Handy, when you want to find the misbehaving program that has been exploiting your hard drive.

Dict [dict]  
Find the meaning of a word without leaving the terminal

pm-susped [pm-suspend]  
Part of the pm-utils package. Allows you to suspend your computer from the terminal.

ELinks [elinks]  
One of the best text mode web browsers. Surprisingly usable with a wide number of websites.

dd [dd]  
One of the older but very robust tools in UNIX. Can be used for myraid number of tasks from writing ISO images to USB media to backing up and cloning entire drives. (The syntax of the command is supposed to be a joke on IBM's Job control language, see if you can find the similarities!)

Smartmontools [smartctl]  
Displays the SMART information from your hard drive. Especially useful after a rough day at the college. You might need to combine it with less to make the output a bit more usable

slock [slock]  
Lock your computer from the terminal.

dmenu [dmenu]  
The fastest program launcher you are ever going to use.

zip [zip]  
Because compression is not out of fashion yet.

unzip [unzip]  
Because you need a command for uncompressing all your zip files created with the previous command.

unrar [unrar]  
Does what the title says.

netdata [netdata]  
A truly beautiful server monitoring tool that might bring out the child in you

pv [pv]  
Have a command that displays utter silence? pv to the rescue!

vnstat [vnstat]  
Know how much data you are consuming? use vnstat. It will also show you how much you might consume at the end of the day and month.

vnstati [vnstati]  
Gets installed with vnstat and outputs beautiful png images graphically showing your data usage

MPD [mpd]  
An audio player daemon to which we can connect using several clients. Not interested? read on

YMPD [ympd]  
A web interface (client) to MPD. Control your audio player from your browser. If you do a bit of web development, this is godsent

lighttpd [lighttpd]  
Want an extremely lightweight web server? Your search ends here.

mps-youtube [mpsyt]  
Search and stream youtube audio (yeah) right from the terminal

pgrep [pgrep]  
Returns the PID of a process. Thats about it.

pkill [pkill]  
Kill processes using their names, very useful for systems without killall
