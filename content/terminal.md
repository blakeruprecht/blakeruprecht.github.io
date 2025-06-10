---
title: Terminal
date: 2024-02-27
description: '"The terminal is an essential tool of the modern computer scientist, up there with the text editor and ChatGPT. Haha, at least the terminal has been around since the dawn of computing."'
---
Once you're logged into your [computer](computer.md) [os](/os), the most useful program is the **terminal**, a text-based application/program that enables you to navigate the storage of your computer and manipulate files and run programs directly through the terminal.

Why use it, isn't it just a glorified folder navigator?
- Yes, basically, I don't recommend the terminal to anyone who isn't trying to code.
- If you are trying to code, the terminal will remove a lot of headaches caused by paths -- it makes every path obvious, and helps you figure out where all your files are relative to each other, essential for coding.
- I don't code much and mainly use the Terminal as a folder navigator and simple script runner -- not needed for most people.

## Usage
- *Note*: I use {curly brackets} to represent the path to a file or folder. In terminal speak, there are absolute paths and relative paths. Every single file or folder has one absolute path, described using the complete path notation: from top-level folder all the way to that specific file/folder. There are a lot of shorthand techniques used in the terminal to avoid typing the full path every time.
- Opens up a command prompt in your home folder
	- `/` is shorthand for the top-level folder on your system -- where the Operating System is installed. You can think of this as a folder with no name or a blank name, e.g. instead of `top/`, `everything/`, `blank/`, or anything like that, they just named this folder `/`.
	- `folderName/` any other folder is usually represented by it's name, and a slash afterward. You'll see directories/folders referenced with and without the slash, so it's not mandatory.
	- `fileName` -- files never have a slash after them, but they may have a file ending, e.g. `fileName.txt`, `filename.png`, etc that doesn't always show up.
	- `~` is shorthand for your user folder's path (e.g. `/home/blake/`. A path is basically the location of any given folder or file on your system. E.g. if I save a file `ex.py` in my home folder, the path for that file will be `/home/blake/ex.py` or `~/ex.py`. This tells us that from the top folder, navigate to the home folder, then the blake folder, and then you'll find `ex.py` in the `blake/` folder.
- **Navigate folders and files**
	- `ls` lists all the files in the current folder
		- `ls -la` lists all files the long way
		- `ls /home/blake/dirName/` lists all files in the directory specified by the path, can be any directory, not just the one you are currently in
	- `cd {path/to/dir/}` changes directory to the one specified by the path, this is the main function I use to move around the folders
		- `cd ..` takes you to the directory above you
			- `..` is shorthand for the parent directory (above you), 
			- `.` is shorthand for your current directory path
- **Move files and folders around**
	- `mv ..` moves to the folder above the current one
	- `mv {dir1/fileName} {dir2/fileName}` moves a file from the first dir position to the second dir position
		- You can change the fileName as well during this move, e.g. `mv folderOld/ folderNew/`
	- `mv {dir1} {dir2}` changes the name of the folder
- **Create files and folders**
	- `touch {filename}` creates a new empty file
	- `mkdir {dirname}` creates a new directory
- **Misc**
	- `grep [options] pattern {files}` searchs all the files in {files} for the "pattern" specified, e.g. `grep -r "my random phrase" ~/*` if you want to search all of your home directory (~/\*) files recursively (-r) for the string "my random phrase"
	- `man {command}` pulls up the MANual (documentation) for any command, it's the best place to learn about what a command does

**Why text?** It's pretty simple, and easy for us humans to remember key words that actually relate to what's going on. At least, that's the idea. The terminal is the place we give the computer commands. That's why it's also called the command line, or command prompt. The most minimal representation of the terminal/command line/command prompt is a special symbol that changes, I don't know why. Typically, the symbol is `$`, `>`, `%`, `#`, or something like that. On my personal computer, I use a little ghost symbol that doesn't show up here.

**What is a terminal?** The terminal is a computer application that enables you to run commands, programs, executables, and navigate your folders and files (just like file explorer). You can do everything on your computer through the terminal. The alternative is to do everything through Graphical User Interfaces (GUIs), which are the windows that pop up when you click on an app. Oftentimes, GUIs are simpler and more intuitive since they have pictures and pretty colors, but if you learn how to use the Terminal, it unlocks many computing superpowers. 
- On Mac, the default terminal app is called "Terminal"
- On Windows, the default app is called "Command Prompt", but you can and should download "PowerShell", a newer, better version.

**What does all this text mean when I open a terminal?** If you're in a terminal, the key thing to know is the terminal prompt: this is a symbol like `$`, `%`, `>` or something else, and it is just a random symbol that tells you to type your commands after the symbol. All of the text before the "prompt" is just for display.
- On Mac, you'll typically see something like `Blake@MyMac ~ $`. The `$` is the prompt, `Blake` is your username, `MyMac` is the name of your computer, and `~` represents the folder you're currently in. In this case, the tilde `~` is shorthand for `home/Blake/`, your home directory where most of your files live. The tilde is just shorthand used in the terminal for your home folder.
- On Windows, you'll typically just see the current folder, `C:\Users\Blake>` with the prompt touching the folder name. In PowerShell, you'll see a "PS" attached to the front for no good reason, e.g. `PS C:\Users\Blake>`

**What is a command?** Typically, anything that you do in a terminal is called a "command", rather ambiguously. These commands are mostly shell scripts, programs, and executables. You can use commands to directly open applications through the terminal, as well as manipulate files and folders.

**What is the shell?** The terminal comes with a "shell" interpreter that lets you use a shell scripting language, like Bash. Bash is a language that includes commands like `cd`, `ls`, `mv`, `grep`, and many more that you can run in a terminal. These do actions like change the current directory, list files in the current directory, move files and folders around, and many more.
