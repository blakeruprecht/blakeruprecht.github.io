---
title: Terminal
date: 2024-02-27
description: '"The terminal is an essential tool of the modern computer scientist, up there with the text editor and ChatGPT. Haha, at least the terminal has been around since the dawn of computing."'
---
Ther Terminal is a simple program that uses a text-based interface (read, words) for file navigation and running programs.

**Why use it**: It makes file paths obvious, which is convenient for coding.

**Essential commands:** 
- `ls` = list files 
- `cd folder/` = change directory 
- `cd ..` = go up one level 
- `mv {old/file} {new/file}` = move file from old folder to new folder
- `mv {old/} {new/}` = rename directory from old to new
- `python file.py` = run Python script called file.py

**Shortcuts:** 
- `$`, `%`, `>` = command prompt, whenever you open the terminal, this is the last symbol displayed by the terminal, you type your commands after it
	- Before the command prompt, terminals typically display the folder you are currently in.
- `~` = your home folder, e.g. `/home/blake/` is equivalent
- `/` = system root, the folder that contains all other folders
- `.` = current folder 
- `..` = parent folder
- `{x}` = curly brackets often represent the path to the folder or file you want to manipulate. You don't actually type the curly brackets into the terminal.
	- A path is either the location of a folder, or the location of a file.
	- The Documents folder in my home folder has the path:
		- `~/Documents/`
		- `/home/blake/Documents`
	- A file in my Documents folder called `ex.py` has the path:
		- `~/Documents/ex.py`
		- `/home/blake/Documents/ex.py`