---
date: 2024-03-04
title: Python install guide
description: The hardest part of coding in Python is setting up the coding environment. Downloading all of the software and making sure it's all in the right place will stop your Python journey before you even start.
---

Python is the most useful general purpose programming language, probably because it is easy to use. It's also the *lingua franca* of [AI research](/ai), because it has awesome [science packages](/python-packages) for free.

Don't let that fool you, it's still difficult to get this anaconda up and running on your own computer.

## Installation instructions
Here's what you'll typically see, as concisely as possible. Bold terms are explained in the FAQ.

1. Download the latest **version** of Python from the [official website](https://www.python.org/downloads/) for your operating system (Mac, Windows, Linux, etc.)
2. Follow the installer, making sure to "add python.exe to **PATH**"
3. Open up a **Terminal** app and type the command `python --version` to verify you have Python installed correctly. It should print out something like `Python 3.11.2`

## FAQ

**What version should I get?** Install the latest version, unless you know you need an earlier version. Typically, there's not too much difference, unless you need Python 2, which is older, and no longer updated and supported.

**What is 32-bit versus 64-bit?** This refers to a specific detail about your CPU architecture. Most modern computers use 64-bit, so you'll probably never need to use 32-bit.

**What is PATH?** Environment variables store data about a system's environment, so the system knows where to look for certain information. The PATH variable is used in Windows, Mac, and Linux as the main user environment variable. It's simply a group of folders represented as a string that tell your system where to look for programs, executables, etc. If you don't add the folder where you installed Python to your path, your computer won't know where to look for the Python executable. Usually, when you install an application, it's automatically added to your path. In the case of installing Python, you have to make sure to check the box to add Python to your PATH.

**What is a directory?** Computer nerds use a secret word called directory instead of just saying folder. I have no idea why we do this.

**What is a terminal?** --> [How to use the terminal](/blog/terminal.md). On MacOS or Linux, it's the app called "Terminal." On Windows, the default is Command Prompt, but you can download PowerShell or Windows Terminal, or even Windows Subsystem for Linux, which runs native Linux commands and tools.

**The** `python` **command didn't work?** There's a chance you must type `python3` to run Python. Otherwise, if it's not working, you may not have the folder/directory location of the Python executable in your PATH.

## References
As always, the best way to learn about a piece of software -- read the docs!
- For more Windows info: [Python 3.12.4 Documentation >> Python Setup and Usage >> 5. Using Python on Windows](https://docs.python.org/3/using/windows.html)
- For more MacOS info: [Python 3.12.4 Documentation >> Python Setup and Usage >> 5. Using Python on a Mac](https://docs.python.org/3/using/mac.html)

## Related
- [python-packages](/python-packages)
- [computers](/computers)


