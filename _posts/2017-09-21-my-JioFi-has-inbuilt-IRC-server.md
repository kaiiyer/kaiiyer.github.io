---
layout: post
title: I bought a JioFi with an inbuilt IRC Server!
---

At the end of last academic year, we had cut the broadband connection which served us in the hostel to avoid paying rent during vacation. It meant at the start of this year, I was without a working internet connection and was in the market for an ISP. 

If you want a cheap internet provider in India, Reliance Jio is hard to beat. They offer high speed 4G internet at very low price. Sadly My phone is not LTE capable and thus I could not just buy a Reliance Jio SIM and insert it into my phone.  

For the first couple of months, I tried using the 3G internet connection of the state run BSNL and had to put up with slow unusable internet. The connection was not expensive, but what is the use of 3G internet if the download speed is around 15 KiB/s? also, the connection came with no additional calling credits, so I still had to shell out extra for making calls. On top of this, the phone routinely refused to connect to the internet, denying me access when I needed it the most. By the end of second month, I finally came to the conclusion that I was simply wasting my money paying for a connection that was serving me no purpose.

Few days after this, my phone started refusing to make calls. I skipped the prospect of buying a phone as it was expensive. I chose the apparently superior option of buying a JioFi router. The device would allow data transfer upto 1 GB per day in 4G speeds and also allowed unlimited voice calls. But most importantly, it was free for the first six months andi offered a considerably cheap subscription after that. 

I had read from some sites that it was made by an Indian brand called LYF and was expecting a  half baked product. I couldn't have been more wrong. My first impression of the product was how well it was made. The rear cover of the router sits flush with the rest of the product. The matte black plastic body while not extremely solid, has enough quality to take day to day beating and lends the device a minimalist yet smart look. 

The first thing I did after getting the device was changing the password for the WiFi connection. I promptly logged into the device configuration page (192.168.225.1) where the first suprise awaited me. Beneath a title ODM, the text Foxconn was written. So the device was manufactured by Foxconn :D Thus the good initial impresssion. 

Fast forward a few hours, I was trying to study something and became bored. I have a habit of running nmap on new devices I buy, hoping to find something interesting. Also, OS detection feature in nmap helps me to find what OS the device is running. I suddenly remembered I had failed to do so, with JioFi. This is what a basic nmap scan returned:

    aswin@ThinkPad-L440:~$ nmap 192.168.225.1 
	
	Starting Nmap 7.40 ( https://nmap.org ) at 2017-09-21 21:06 IST 
	Nmap scan report for jiofi.local.html (192.168.225.1) 
	Host is up (0.013s latency). 
	Not shown: 996 closed ports 
	PORT     STATE SERVICE 
	53/tcp   open  domain 
	80/tcp   open  http 
	6666/tcp open  irc 
	7777/tcp open  cbt 
	
	Nmap done: 1 IP address (1 host up) scanned in 1.44 seconds 
 
Lets start with the crown jewel. Why the heck is a 4G enabled WifiRouter running an IRC server on port 6666?

There is a DNS server running on port 53 :) which is an okay if not welcome addition. The device must be doing some DNS caching to speed up webpage load performance 
 
On port 80, we have the web server running our configuration interface. That is as typical as it gets, but what is not typical is the service that listens on port 7777 nmap tells me that the service running on the port is cbt, which usually means it is running an Oracle HTTP server. Okay. But seriously, why? 

Trying to detect the OS, nmap gives me the following results: 

    Running: Linux 3.X|4.X 
    OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4 
    OS details: Linux 3.2 - 4.6 

It is running a comparitively newer version of the Linux kernel. Embedded devices usually suck in this regard. My D-Link router still runs on the ancient 2.6 kernel. 

It is very early to jump into any conclusions. But apparently, the JioFi router is running a number of services that is not essential for it to function. I will continue to poke into the device and will update it if I find anything interesting...
