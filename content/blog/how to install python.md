---
date: 2024-03-17
title: How to Install Python
description: '"In this essay I take readers on a journey from Noob to Python master, the same journey I undertook during my Masters degree to study AI."'
---
I entered the software field as a mechanical engineer. Even with technical experience and some coding experience, I found the entire software world quite daunting. All of the documentation I read assumed I already knew stuff like what this `~` symbol meant, or how to input something like `$ cd home` into my computer. I didn't even understand why the text looks different with a little box around it.

If you're as fresh and new as I was, you'll probably appreciate a step-by-step guide to figuring all of this out. There's so much more to coding than actually typing code. You have to know where your files are stored, where your software is stored, where your packages are stored, and how they all talk to eachother. Let's break it down.

## Installation instructions
Here's what you'll typically see, as concisely as possible

1. Download the latest version of Python from the [official website](https://www.python.org/downloads/) for your operating system (Mac, Windows, Linux, etc.)
2. Follow the installer, making sure to "add python.exe to PATH"
3. Open up a Terminal app and type the command `python --version` to verify you have Python installed correctly. It should print out something like `Python 3.11.2`

## FAQ

**What version should I get?** Install the latest version, unless you know you need an earlier version. Typically, there's not too much difference, unless you need Python 2, which is older, and no longer updated and supported.

**What is 32-bit versus 64-bit?** This refers to a specific detail about your CPU architecture. Most modern computers use 64-bit, so you'll probably never need to use 32-bit.

**What is PATH?** Environment variables store data about a system's environment so the system knows where to look for certain information. The PATH variable is used in Windows, Mac, and Linux. In actuality, it's just a text string of folders that tell your system where to look for programs, executables, etc. If you don't add the location of your Python installation to your PATH variable, every time you try to type in `python` in the terminal, your system won't know where to look for it. Usually, when you install an application, the application folder is added to yoru PATH variable automatically.

**What is a directory?** Computer nerds use a secret word called directory instead of just saying folder. I have no idea why we do this.

**What is a terminal?** The terminal is a computer application that enables you to run commands, programs, executables, and navigate your folders and files (just like file explorer). You can do everything on your computer through the terminal. The alternative is to do everything through Graphical User Interfaces (GUIs), which are the windows that pop up when you click on an app. Oftentimes, GUIs are simpler and more intuitive since they have pictures and pretty colors, but if you learn how to use the Terminal, it unlocks many computing superpowers. 
- On Mac, the default terminal app is called "Terminal"
- On Windows, the default app is called "Command Prompt", but you can and should download "PowerShell", a newer, better version.

**What does this text mean when I open a terminal?** If you're in a terminal, the key thing to know is the terminal prompt: this is a symbol like `$`, `%`, `>` or something else, and it is just a random symbol that tells you to type your commands after the symbol. All of the text before the "prompt" is just for display.
- On Mac, you'll typically see something like `Blake@MyMac ~ $`. The `$` is the prompt, `Blake` is your username, `MyMac` is the name of your computer, and `~` represents the folder you're currently in. In this case, the tilde `~` is shorthand for `/home/Blake`, your home directory. Those two things are equivalent in this case.
- On Windows, you'll typically just see the current folder, `C:\Users\Blake>` with the prompt touching the folder name. In PowerShell, you'll see the PS attached to the front for no good reason, e.g. `PS C:\Users\Blake>`

**What is a command?** Typically, anything that you do in a terminal is called a "command", rather ambiguously. These commands are mostly shell scripts, programs, and executables. You can use commands to directly open applications through the terminal, as well as manipulate files and folders.

**What is the shell?** The terminal comes with a "shell" interpreter that lets you use a shell scripting language, like Bash. Bash is a language that includes commands like `cd`, `ls`, `mv`, `grep`, and many more that you can run in a terminal. These do actions like change the current directory, list files in the current directory, move files and folders around, and many more.

**The** `python` **command didn't work?** There's a chance you have to type `python3` to run Python. Otherwise, if it's not working, you may not have the folder/directory location of the Python executable in your PATH.

## References
As always, the best way to learn about a piece of software -- read the docs!
- For more Windows info: [Python 3.12.4 Documentation >> Python Setup and Usage >> 5. Using Python on Windows](https://docs.python.org/3/using/windows.html)
- For more MacOS info: [Python 3.12.4 Documentation >> Python Setup and Usage >> 5. Using Python on a Mac](https://docs.python.org/3/using/mac.html)


