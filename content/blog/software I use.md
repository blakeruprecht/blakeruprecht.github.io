---
date: 2023-11-20
title: software i use
---

This is mainly a guide to my future self to install this stuff. If you're curious about any of these, find my email on my about page and email me questions, and I'll update this post to be more thorough.

![My Linux environment running DWM](unix_pic.png)

In order of install, this is all of the software I currently use on my work laptop. In summary:
- OPERATING_SYSTEM: Linux (Debian 12)
- WINDOW_SYSTEM: Xorg
- WINDOW_MANAGER: dwm
- TERMINAL: st
- SHELL: bash
- TEXT_EDITOR: nano
- IMAGE_VIEWER: feh
- COLORSCHEME: custom black and white with default terminal colors
- STATUSBAR: custom xsetroot in my .xinitrc
- MARKDOWN_EDITOR: Obsidian
- WEBSITE_CREATION: Hugo

1. Install an operating system (Linux, the Debian 12 distribution)
	1. Download the Debian .iso for your system (mine is a Dell XPS 13 9370). Follow the steps from Ubuntu's [tutorial](https://ubuntu.com/tutorials/install-ubuntu-desktop#3-create-a-bootable-usb-stick) to create a bootable flash drive using balenaEtcher on Windows 11.
	2. Change BIOS settings to enable booting from flash drive. I forget what I had to change, but it was mainly allowing the system to boot from flash drives and .iso files, and then changing the boot order to boot from flash drive before Windows.
	3. Plug in flash drive and follow the Debian installer. Keep all basic options, they are fine. Don't install any extra software at the end except for "standard system utilites". A desktop environment is not needed.
	4. This step is finished when you can turn on your PC and it does the funny startup stuff until you get to a simple black terminal with "debian login: " and you put in your username and password. After this, it just says "username@hostname" (for me, blake@debian) in the top left corner of a terminal. Simple, no extra crap, perfect.
2. Once a clean version of Linux is on your system with no extra bloat, you have a working computer. I didn't want to live in the tty (the default terminal that comes with the OS), so I installed a window system (xorg and dependent packages) using `sudo apt install xorg`.
3. I installed xorg so that I could install a window manager. I chose dwm from dwm.suckless.org, a lightweight window manager written in C. I chose this because it is small and simple with no stupid features. I git cloned the repo straight from that website, and ran "sudo make clean install" to install the window manager. Then, create the file ".xinitrc" in your home directory (typically ``~`` or ``/home/username``) with the line ``exec dwm`` at the end (or start since it's a new file). Then, run ``startx`` in the tty, and you should see dwm pop up.
4. I also installed st and dmenu from suckless.org to have a terminal and menu launcher. These were easy, same process, ``sudo make clean install``. After this, your system is good to go. I patched my dwm and st installs with the following patches:
	1. dwm: "alttagsdecoration", "alwayscenter", "truecenteredtitle", "underlinetags", and "uselessgap" 
	2. st: "font2"
5. The rest of the time was spent editing my dwm and st "config.h" files to make the windows look how I wanted, mainly by adding black backgrounds, white borders, and customizing little things here and there.
6. To set a wallpaper, ``sudo apt install feh``, the use ``feh --bg-fill wallpaper_name.jpg`` to apply your wallpaper, then add ``~/.fehbg &`` to your .xinitrc to run feh everytime you startx. Change the wallpaper at any time by using the ``feh bg-fill new_wall.jpg`` command.
7. Install the Obsidian AppImage and figure out to run it on your machine. I won't do this again, and will switch to QOwnNotes or NeoVim to edit Markdown files in the future, since I don't need backlinking in Obsidian. I do like the minimal UI though.
8. Install hugo and git clone website from github. This is how I choose to build a website, it's pretty straightforward if you follow the tutorial on Hugo's website and build a Github Pages site. I will eventually switch to a custom HTML/CSS/JS website once I get around to learning JavaScript, but that's not today.