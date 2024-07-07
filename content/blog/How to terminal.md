---
title: What is the terminal?
date: 2024-02-27
description: '"The terminal is an essential tool of the modern computer scientist, up there with the text editor and ChatGPT. Haha, at least the terminal has been around since the dawn of computing."'
---


The terminal, command line, prompt, command prompt -- what's going on there? I'm sure most of you remember or have seen pictures of the old computers -- big metal frames, tiny curved screens, probably black with green text or something. Old school, hacker looking stuff. Those computers were all text-based -- there were no pictures. No graphics. No images. Well, except for the words used to give the computer commands. The whole word concept has stuck around since the very beginning, and is still the main way that computer scientists communicate with the computer. Text.

Why text? It's pretty simple, and easy for us humans to remember key words that actually relate to what's going on. At least, that's the idea. The terminal is the place we give the computer commands. That's why it's also called the command line, or command prompt. The most minimal representation of the terminal/command line/command prompt is a special symbol that changes, I don't know why. Typically, the symbol is `$`, `>`, `%`, `#`, or something like that. I particularly like `>` because it looks like an arrow.

**What is a terminal?** The terminal is a computer application that enables you to run commands, programs, executables, and navigate your folders and files (just like file explorer). You can do everything on your computer through the terminal. The alternative is to do everything through Graphical User Interfaces (GUIs), which are the windows that pop up when you click on an app. Oftentimes, GUIs are simpler and more intuitive since they have pictures and pretty colors, but if you learn how to use the Terminal, it unlocks many computing superpowers. 
- On Mac, the default terminal app is called "Terminal"
- On Windows, the default app is called "Command Prompt", but you can and should download "PowerShell", a newer, better version.

**What does this text mean when I open a terminal?** If you're in a terminal, the key thing to know is the terminal prompt: this is a symbol like `$`, `%`, `>` or something else, and it is just a random symbol that tells you to type your commands after the symbol. All of the text before the "prompt" is just for display.
- On Mac, you'll typically see something like `Blake@MyMac ~ $`. The `$` is the prompt, `Blake` is your username, `MyMac` is the name of your computer, and `~` represents the folder you're currently in. In this case, the tilde `~` is shorthand for `/home/Blake`, your home directory. Those two things are equivalent in this case.
- On Windows, you'll typically just see the current folder, `C:\Users\Blake>` with the prompt touching the folder name. In PowerShell, you'll see the PS attached to the front for no good reason, e.g. `PS C:\Users\Blake>`

**What is a command?** Typically, anything that you do in a terminal is called a "command", rather ambiguously. These commands are mostly shell scripts, programs, and executables. You can use commands to directly open applications through the terminal, as well as manipulate files and folders.

**What is the shell?** The terminal comes with a "shell" interpreter that lets you use a shell scripting language, like Bash. Bash is a language that includes commands like `cd`, `ls`, `mv`, `grep`, and many more that you can run in a terminal. These do actions like change the current directory, list files in the current directory, move files and folders around, and many more.