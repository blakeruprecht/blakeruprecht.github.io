---
date: 2023-11-20
title: Simple software follows Unix principles
description: "The Unix philosophy of computer software is difficult to learn, but once you do, the rewards are well worth it because it makes using a computer much simpler."
draft: false
---
 
![Screenshot of my Linux env running DWM](/linux-setup.png)

## Update 2024-09-27
Of course, I did this as a fun experiment to see if Linux was worth it. It's been a few months of daily driving this setup on my computer, and I can confidently say that it works great. Maybe I'll do it again, maybe I'll install Linux Mint next, maybe I'll go back to MacOS.

I appreciate being able to do this, I'm not sure I ever personally want to dedicate the time to this much coding again.

## Software is hard
I just want to say that I find software quite difficult to work with, and I in theory have a masters degree in computer science. My argument against that is my degree focuses on math, not programming, so anything to do with turning on a computer and getting it to work makes me feel like a monkey. Eventually, I learned that software is a lot like building Lego sets -- the instructions tell you everything you need to know.

After years of banging my head against the wall trying to get different computer programs to work with each other, I've settled on using just a few essential programs to get all of my computing done. What does this mean for you?

If you're a fellow computer scientist, AI researcher, or engineer who likes to dive into the weeds, read on! If you're an average person, I only recommend diving into this stuff if you love to tinker. It's rewarding and cool to learn, but all of the others spent learning how to do this could otherwise be spent drinking beer on a beach, so up to you.

## First Principles
As with anything, let's break it down to the bare requirements -- why do I have a computer in the first place? For my requirements, it's basically 50% browsing the internet, and 50% editing text and code files and syncing those to the cloud. I don't need hardly anything on my laptop. Weather app? Nah, just go to weather.com. Excel? I just use Google Sheets. Texting? Hell no. I had a Mac, which came with a bunch of default crap that I didn't need on my computer. For example, the file manager -- on MacOS, that thing is terrible, it never tells you your absolute file path, confuses different drives, etc. Windows and MacOS are great operating systems, but they also come with a lot of crap and bloat that every user doesn't need.

Free and Open Source Software (FOSS) is software distributed by one or multiple people entirely for free, with all of the source code readily available for anyone to look at, and propose changes to, or change themselves. It's yours to do what you want with. If you buy a new laptop or phone today, chances are it runs a proprietary operating system like Windows/MacOS/Android/iOS. These are all good operating systems from a technical standpoint, but they are closed source and cost money. But wait, doesn't every product cost money?

Not in the software world. I know, it's weird. Back in 1983 a wacky programmer named Richard Stallman set out to create an entire computing environment and make it free for every one to obtain and modify, called GNU (Gnu's Not Unix). In 1991, Linus Torvalds wrote the Linux kernel, and ever since, we've had the totally FOSS combination of GNU and Linux to provide free software to the world.

Since then, GNU & Linux have been an integral part of coding culture. Free software isn't just the cheap alternative to good paid software, it's actually better in many scenarios. Open-source means more eyes are looking at the code, finding bugs, and improving it. Linux is a much safer operating system than Windows for this reason. Most of the tools work exceptionally well because they've been refined by thousands of people over the course of decades. The wheel hasn't been reinvented over and over by private companies, it's just been made rounder by thousands of people.

FOSS has been an integral part of coding culture. Many programmers willingly choose to give away their work. Often done as a way to gain influence and following, build resumes, and just contribute cool stuff to the wider community, it's an anomaly in the modern world that I rarely see elsewhere. The FOSS spirit is stronger in some than others, but most programmers use free & open-source software in parts of their workflow. Even those who develop on Mac (closed source) computers often use VS Code (a FOSS text editor distributed by Microsoft of all people). 

## Unix philosophy
GNU, Linux, and most Free & Open-source Software follows the Unix philosophy, summarized here by Peter H. Salus in *A Quarter-Century of Unix* (1994).
1. Write programs that do one thing and do it well. (DOTADIW)
2. Write programs to work together.
3. Write programs to handle text streams, because that is a universal interface.

## A Note on Social Media
*The Social Dilemna* is a great documentary summing up the path the internet has taken the past two-decades. It went from a place built by nerds, for nerds, to a place now mostly run by large corporations harvesting our collective attention for profit. This is great for the companies, but devastating for the average person. I don't believe that the average person benefits from social media and the internet at large. It's turned into a distraction economy that profits from keeping people as engaged as possible, tuned into crap. The television's distracting powers have been amplified tenfold, since the computer now rests in everyone's pockets, just a click away from insane content.

There's a solution besides abstension -- and don't get me wrong, I think the Mennonites are doing much better with modern technology than the majority of western society because they have intentionally chosen to reject most modern computing in favor of maintaining their local communities.

## What I need
The absolute basic requirements are an operating system to manage system resources, a window manager to draw pretty boxes on the screen, and a command prompt to navigate my file directories and perform basic scripting commands like viewing files (`ls -la`), deleting files (`rm`), moving files (`mv`), etc. Mac and Windows both achieve this excellently, but they come with a bunch of extra junk, so I installed a Linux distribution instead. A barebones Debian install comes with -- an OS. I installed a window manager (dwm) and a command prompt/terminal (st), and boom, I'm setup to computer.

Beyond the core necessities, I need a few programming languages installed on my computer (C, Python, Go, HTML, CSS), all of which come on a normal Linux install except for Go, so I had to download that, as well as a few packages like "git". After that, using the default text editors (Nano and Vim (okay, upgraded that to Neovim)), I can edit all of the code I want to my heart's content. Cool.

And I installed a *web browser* (Firefox). Now, I can do everything I want on a computer -- edit text, edit code, browse the web. That's it. I don't need a million other programs to do who knows what, just those few.

## My Software List
In order of install, this is all of the major software I currently use on my laptop. I have not included the countless packages that are installed concurrently with these programs as necessary binaries and utilities, since I don't know what the heck those are. For reference, I have hardly anything installed on my laptop (seriously, less than 1GB of software), and still have around 1000 software packages.

In order of install:
- Operating System: LINUX, barebones DEBIAN 12 distribution
- Window System: XORG
- Window Manager: DWM
- Terminal Emulator: ST
- Statusbar: .xinitrc script with "xsetroot" variable
- Shell Language: BASH
- Text Editor: NANO and NEOVIM (Still learning vim)
- File Browser: none (I just use cd/ls/mv unix utilities)
- Image Viewer: FEH
- Video Viewer: MPV
- PDF/EPUB Viewer: ZATHURA
- Scripting Language: PYTHON (My main language for all things coding)
- Markup Language: MARKDOWN
- Markdown Editor: OBSIDIAN (I use it just as a text editor)
- Website Language: GO (HUGO compiles Markdown into HTML)
- Design Language: CSS (used for Obsidian and Hugo)
- Web Browser: MOZILLA FIREFOX (this is the only alternative to Chromium (FOSS) browsers, trying to keep it alive)

## Installation
Installing Debian, DWM, and ST are really the only tricky things to do here, once you have those, installing all of the other programs is as easy as `sudo apt install neovim`. If you need help with any of this, please email me, I'm happy to help set you free!

**Install Debian 12**
1. Download the Debian .iso from Debian's website for your computer architecture. You need to put this .iso file on a flash drive, but the trick here is you have to make it "bootable", which means you can plug it into a computer and the computer recognizes that the flash drive has an operating system on it.
	1. I followed the [Ubuntu Tutorial](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview) to create a bootable flash drive using Balena Etcher. Of course, I downloaded the Debian .iso rather than the Ubuntu .iso, but the process is the same for either. Ubuntu is a fork of the Debian project with a bunch of extra crap included that I would just delete anyways, so I went with Debian because it has an installer and allows you to install nothing besides the OS (similar to Arch, which is another good option, but more labor intensive during install. The big difference is choosing between the "pacman" rolling-release package manager (bleeding edge, more likely to fail) and the "apt" stable debian package manager (fewer updates, more, well, stable)).
2. If your computer already has another OS installed (mine had windows), you'll have to go into your BIOS settings and fiddle with some stuff. This is a very tricky part of the process, and unique to every computer, so you'll probably have to look up "Boot from flash drive on Dell XPS 9370" (that's what I did). I had to enable booting from flash drive, and then change the default boot order to boot from flash drive before booting from windows.
3. Once I got the computer to actually boot from the flash drive, the rest of the Debian install is a piece of cake -- just follow the installer instructions. Make your passwords, don't install GNOME or any other crappy software, and wipe Windows from your hard drive for good! Woohoo! At the end of this process, you should be able to log into Debian using your credentials (username and password), and then it goes to a totally black screen with something like `blake@debian $` in the top left. This is now a fully functional computer, you can do anything you need on it. This almost blank screen is called the "tty", the default terminal emulator on a Linux system. Every time you start the computer, you'll enter the tty, log in with your username and password, and then run the "startx" command to start your X window system which uses DWM to draw windows on the screen (you see where Windows OS got it's name?). We don't have X or DWM yet, so follow the next step.

**Install DWM & ST**
NOTE: You'll have to learn how to operate dwm, st, and dmenu, which are mostly keyboard driven. Don't be afraid, it's pretty simple once you get the hang of it.
1. Okay, you probably want it to look pretty, which means we need to install a Window Manager to enable the computer to draw little boxes on the screen, like a box for your text editor, terminal, or web browser. Cool, to do this, first install Xorg window system by running `sudo apt install xorg`. Easy as pie.
2. Then, install dwm from dwm.suckless.org by running `git clone https://git.suckless.org/dwm`. If you need to install git first, run `sudo apt install git`. This will clone the dwm folder into `~/dwm` on your computer. Add the line `exec dwm` into your .xinitrc file. If you don't have one, run `nano ~/.xinitrc` to create and open the file in nano, then add the exec dwm line to the top of the file. Close the file. Now you can run `startx`, and it should run the dwm window manager.
3. You could have done this at the same time as the first git clone, but now run `git clone https://git.suckless.org/st` to install a terminal emulator and `git clone https://git.suckless.org/dmenu` to install a menu thingy to launch firefox and other apps (I literally only use it for firefox). I used ChatGPT to help me patch dwm and st, which is a bit of a tricky process if you're not used to C. If you're having trouble figuring out to patch dwm/st like I did (there are seriously no tutorials online), email me.
	1. dwm pathces: "alttagsdecoration", "alwayscenter", "truecenteredtitle", "underlinetags", "uselessgap"
	2. st patches: "font2"
	3. dmenu patches: none
4. I spent a lot of time editing the "config.h" files for dwm and st to make them pretty (aka making it all black and white).

**Install Everything Else**
1. Install a web browser using `sudo apt install firefox`. 
2. `sudo apt install feh`, then add `~/.fehbg` to your .xinitrc file, then run `feh --bg-fill wallpaper_name.jpg` using whatever jpg or png you've donwloaded from the internet to set your wallpaper. Yeah, not super simple.
3. `sudo apt install neovim, mpv, zathura, hugo` and whatever other pieces of software you need.
4. I created the statusbar in the top right of my screen to display the time and my current battery percentage, the only two things I care about using a little script in my .xinitrc file that utilizes the "xsetroot" variable. Ask ChatGPT how to do this.
5. You connected to your default WiFi during Debian install, but if you ever want to go anywhere else and use WiFi, it's a little tricky on Debian. Sure, you can install some program to manage wifi for you, but I'm too lazy, so I just add new SSIDs and passwords to the `/etc/wpa_supplicant/wpa_supplicant.conf` file and restart my computer every time I switch wifi networks. Elegant? No. Easy? Yes. Use `lspci | grep Network` to make sure Debian recognizes your laptop's wifi card, if it doesn't, GGs laptop. `sudo ip link` or `ping google.com` is a good way to check if your internet is working.

**Congrats, you're a computer scientist now!**
Okay, not technically, but if you can go through all of these steps and fill in the gaps that I didn't explain, you'll easily be as skilled as me at Linux. The trickiest part of following software tutorials is nobody ever explains every single step, so please email me if you need help and I'll expand this page to cover everything, it's just hard to remember since I'm writing this after the fact.

## About this website
I built this site using Hugo, a static site generator written in Go. I write custom HTML and CSS for this site to learn the basics of web design and search engine optimization. This site is blazing fast (~1s load times), designed mobile-first, accessible, technically optimized, and on-page optimized. I host it on Github Pages, and use Github Actions to deploy the site locally from the command line.

## References
- http://catb.org/~esr/writings/unix-koans/
- https://lukesmith.xyz/programs/
