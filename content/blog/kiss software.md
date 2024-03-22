---
date: 2023-11-20
title: KISS Unix is difficult to learn but makes software problems simple to deal with
description: '"The Unix philosophy of computer software is difficult to learn, but once you do, the rewards are well worth it because it makes using a computer much simpler."'
---

![Screenshot of my Linux env running DWM](/unix_pic.png)

## Unix philosophy
This software guide tries to follow the Unix Philosophy, summarized here by Peter H. Salus in *A Quarter-Century of Unix* (1994).
1. Write programs that do one thing and do it well. (DOTADIW)
2. Write programs to work together.
3. Write programs to handle text streams, because that is a universal interface.

Otherwise, Keep It Simple Stupid! I've spent enought time frustrated at software to realize the benefits of small programs that do one thing, rather than huge programs that do many things. Computers are really complex and hard to work with, so breaking up programs into modular parts makes a lot of sense to me, but I have a lot of software knowledge. Don't get me wrong, Windows and Mac are great OS's as well, but they are not free and open source, so I do not support them. Plus, they won't let me remove programs I don't need, which I find annoying. Bloat!

The other important consideration for software is the Attention (Distraction, really) Economy. Watch *The Social Dilemna*, or just open your eyes to see that the internet is unregulated, and destroying valuable parts of our minds and society as a whole. One way to maintain the benefits of software without all of the bad parts is to do as many computing tasks offline as possible, and remember that anything done over the internet is sketchy/suspect.

## My Software List
In order of install, this is all of the software I currently use on my laptop.
- Operating System: LINUX (specifically DEBIAN 12)
- Window System: XORG
- Window Manager: SUCKLESS/DWM
- Statusbar: .xinitrc script with "xsetroot" variable
- Terminal Emulator: SUCKLESS/ST
- Shell Language: BASH
- Text Editor: NANO
- Image Viewer: FEH
- File Viewer: ZATHURA
- File Browser: none (just use cd/ls)
- Markup Language: MARKDOWN (compiled into HTML using HUGO)
- Scripting Language: PYTHON
- Website Language: GO (for using with HUGO)
- Design Language: CSS (used with HUGO)
- Web Browser: MOZILLA FIREFOX (just trying to use a non-chromium one, will probably switch later)

## Installation
1. Install an operating system (Linux, the Debian 12 distribution)
	1. Download the Linux .iso for your system (mine is a Dell XPS 13 9370). You'll need a working computer to create a bootable flash drive, and it changes depending on what system you have, so DuckDuckGo it, or email me and I'll be happy to help you with specifics.
	2. Change BIOS settings to enable booting from flash drive. This is highly dependent on what BIOS version you have from the factory, so look it up for your specific computer. Yes, these first few steps are by far the hardest because they change depending on the machine you have. I had to enable booting from flash drive, and then change the boot order since my laptop came with windows (I since deleted windows, you don't have to, dual-booting is a great option if you just want to test out Linux).
	3. Plug in flash drive and follow the Debian installer (if you're on a different distro, follow their instructions). Keep all basic options, they are fine. Don't install any extra software at the end except for "standard system utilites". A desktop environment is not needed and comes with a lot of bloat, but if you're used to MacOS or Windows, keep GNOME or something.
	4. This step is finished when you can turn on your PC and it does the funny startup stuff until you get to a simple black terminal with "debian login: " and you put in your username and password. After this, it just says "username@hostname" (for me, blake@deb, I named both) in the top left corner of a terminal. Simple, no extra crap, perfect.
2. Once a clean version of Linux is on your system with no extra bloat, you have a working computer. I didn't want to live in the tty (the default terminal that comes with the OS), so I installed a window system (xorg and dependent packages) using `sudo apt install xorg`.
3. I installed xorg so that I could install a window manager. I chose dwm from dwm.suckless.org, a lightweight window manager written in C. I chose this because it is small and simple with no stupid features. I git cloned the repo straight from that website, and ran "sudo make clean install" to install the window manager. Then, create the file ".xinitrc" in your home directory (typically ``~`` or ``/home/username``) with the line ``exec dwm`` at the end (or start since it's a new file). Then, run ``startx`` in the tty, and you should see dwm pop up.
4. I also installed st and dmenu from suckless.org to have a terminal and menu launcher. These were easy, same process, ``sudo make clean install``. After this, your system is good to go. I patched my dwm and st installs with the following patches:
	1. dwm: "alttagsdecoration", "alwayscenter", "truecenteredtitle", "underlinetags", and "uselessgap" 
	2. st: "font2"
5. The rest of the time was spent editing my dwm and st "config.h" files to make the windows look how I wanted, mainly by adding black backgrounds, white borders, and customizing little things here and there.
6. To set a wallpaper, ``sudo apt install feh``, the use ``feh --bg-fill wallpaper_name.jpg`` to apply your wallpaper, then add ``~/.fehbg &`` to your .xinitrc to run feh everytime you startx. Change the wallpaper at any time by using the ``feh bg-fill new_wall.jpg`` command.
7. Install the Obsidian AppImage and figure out to run it on your machine. I won't do this again, and will switch to QOwnNotes or NeoVim to edit Markdown files in the future, since I don't need backlinking in Obsidian. I do like the minimal UI though. I don't use graph view or any other plugins. Obsidian supports wikilinks in the style `[[File_Name]]` as well as `[File_Name](File_Name.md)`
8. Install hugo and git clone your website from github/gitlab or make a new one. This is how I choose to build a website, it's pretty straightforward if you follow the tutorial on Hugo's website and build a Github Pages site. I will eventually switch to a custom HTML/CSS/JS website once I get around to learning JavaScript, but that's not today.
9. Connect to WiFi. Yes, seriously, there is no default way to do this in dwm (that I know of). Debian setup established my original home WiFi connection. To check if your system recognizes your WiFi card, type `lspci | grep Network`, then type `sudo ip link` to check its status. Add more WiFi ssid/psk pairs to the `/etc/wpa_supplicant/wpa_supplicant.conf` file in order of preference. Your laptop will automatically connect to the first network it can find. Yes, kinda janky, but it works, and I have internet now.

## Next Steps
Following the info from [Luke Smith](https://lukesmith.xyz/programs/)
- [ ] neovim for text editing
- [ ] mpd w/ncmpcpp for audio library
- [ ] mpv for audio/video playback
- [ ] neomutt for offline email
- [ ] newsboat for rss feeds
- [ ] ffmpeg for video/audio recording
- [ ] sxiv for image viewing
- [ ] gimp for image editing
