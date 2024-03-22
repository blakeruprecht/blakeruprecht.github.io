---
date: 2024-03-17
title: Artificial Intelligence research is the best way to Learn Python
description: '"In this essay I take readers on a journey from Noob to Python master, the same journey I undertook during my Masters degree to study AI."'
---
![The python logo is cool](/python-logo.png)

Let me guess, you want to learn Python, but there is a disconnect between practicing it on your web browser and actually getting programs to run on your machine locally? Well, maybe not, but this was the case for me, and I dented the wall next to my desk with the amount of times I banged my head in frustration trying to get software to work on my computer.

I started my Python journey as a mechanical engineering student with lots of math and some coding knowledge, or so I thought. Things were still pretty rough in the beginning, to say the least. Who knew how complicated computers were? No wonder there's an entire major dedicated to them. I had some previous Matlab coding experience, but this barely scratched the surface of what I would need to learn to get up to speed with AI developments. Everything I found and read online seemed to be tailored towards people with bachelor's degrees in CS already. I wished there was something to explain everything to me simply, so I'm writing that now. You can get pretty far in AI without knowing any math, but you can't really get anywhere without knowing coding, and specifically, knowing Python. Here's what you need to know, from five long years of banging my head against a wall trying to figure all of this stuff out.

## Hardware and Operating Systems
Okay, first things first, you need a computer. Assuming you're reading this online, step one (probably) done. What computer? Any. You can learn and code on basically any functioning computer. Sure, training large AI models requires some pretty intense computing power, but if you're just interested in learning like I was, you won't need anything powerful. A used $100 Lenovo Thinkpad X220 is a great option if you need something cheap. I have a used $300 Dell XPS 13 9370 that came with Windows 11 and is now running Linux, and an old 2015 Macbook Pro running MacOS. I also have a dedicated desktop with a fancy GPU, mainly for gaming. If you want to keep up with OpenAI/Google/Meta, you'll need hundreds of millions of dollars worth of computing power. I was never interested in running massive experiments, so I just use what I have. You could probably figure out how to run code on a cellphone, but Android and iOS are both annoying to use, so I wouldn't recommend it unless you know more than me.

As for operating systems, the vast majority of research and online code I found was setup for people running MacOS or Ubuntu/Debian Linux. Windows is fine, especially if you install Windows Subsystem for Linux. Microsoft has made some impressive strides recently to support Linux and open-source software, it'll just be slightly trickier since all of the tutorials will be tailored for Unix-based systems (MacOS, Linux-variants, BSD-variants). I personally love Linux because it gives me total control over my laptop, and I'm a big proponent of free and open source software, but if you don't care about this, use Mac or Windows.

## Directory Structure
What the hell is a directory? This is some secret CS juju I learned later, but a "directory" is the fancy computer term for a folder. Like the "Documents", "Downloads", and "Pictures" folder that are probably on your computer already. So much of coding is figuring out where you currently are in the overall computer directory structure. Regardless of what OS you have, you likely have a user directory specific to your profile.


I'm a literal *master of computer science* and have been working with computers for 20+ years, I have two degrees in engineering, and yet, all of this stuff is still confusing as fuck to me. Trust me, it's not you, it's computers that are confusing, they're so damn complicated with archaic software tacked on top of and under new software, and the whole thing is resting on a precarious foundation.

- Directories
	- All computer files are stored on the "disk", aka your hard drive, could be a solid state drive. This is separate from "memory", which refers to RAM.
	- "Directory" means the same thing as "folder" but is preferred in computer speak for who knows what reason.
	- Every single drive follows the same structure
		- Using Unix terminology, the entire drive is labeled `/`, slash, which refers to the "root" of the directory "tree", aka it's the entire drive, it contains everything.
		- Example using bullet points to display directory depth
			- `/` (this is the top-most level, often called "root", but as you can see, it doesn't have a name, and is just represented by the forward slash. Dunno why.)
				- `/folder1`
					- `/subfolder1`
						- `/subsubfolder1`
							- `file1.txt` (full path is `/folder1/subfolder1/subsubfolder1/file1.txt)
					- `/subfolder2`
						- `file2.txt`
				- `/folder2`
					- `/subfolder1`
						- `file3.txt`
						- `file4.txt`
					- `/subfolder2`
						- (empty, no files yet)
- Terminal / Command Line
	- Some good commands to know
		- `cd` (current directory)
			- `cd ..` (`..` is a special variable name referring to the directory immediately above you, so regardless of where you are in the tree, it will take you one layer higher)
			- `cd /` change directory to your unnamed root
			- `cd ~` change directory to your current user's home directory (for me, `/home/blake/`) (remember `/home` lives in the unnamed root directory, `/`)
			- `cd /new/directory/path/` 
		- `ls` (list)
			- `ls -la`
		- `mv` (move a file/folder from one location to another)
			- `mv /old/example.py /new/example.py`
			- `mv /old/example.py /new/`
				- these two are equivalent
		- `cp` (copy, first argument is the file that already exists and you want to make a copy of, second argument is the place you want to put the new file)
			- `cp name.txt newname.txt`
- OS Package Manager
	- MacOS - homebrew
	- Windows - chocolatey
	- Linux - distro dependent (pacman, apt, etc.)
- Python Package Manager
	- Conda vs. Pip
	- Packages to `pip install`
		- numpy (for dealing with numbers and arrays)
		- pandas (for importing data)
		- matplotlib (for making graphs & graphics)
		- pytorch (the major AI/ML package, along with tensorflow)






2. Figure out how to use the Terminal (oftentimes an Application on modern computers, but originally the only way you talked to a computer) and the basic Shell commands, e.g. ``cd``, ``ls``, ``mv``
	1. SideQuest: dive deep into learning Bash as scripting language, using it for all sorts of useful things and fast programming, data sorting, etc. I've done a bit, and it's really useful. Think of Bash as just another useful programming language in your tool box.

3. Download a text editor like VSCode to edit code and text.
	1. SideQuest: learn about Vim (and Vi), the original Unix text editors which still work amazing, are lightweight, free, have modern extensions for easier coding (e.g. NeoVim), and are almost entirely keyboard based. You don't need to use the mouse, like ever. Downside, it doesn't make you a better coder and takes a while to learn. Most pros just use VSCode.
	- SideQuest: learn about Emacs and the wonders of elisp, the super fancy Linux/GNU text editor that can do some really magical stuff. LISP is crazy cool, but difficult and not practical right off the bat. Of course, the more programming languages you learn, the better programmer you will be, so get familiar with all of the languages and what they're good for.

4. Download Conda, Python, and relevant Python packages into your software environment. You'll have to get good at installing different software packages and setting up the right Environments for testing using the $PATH variable. This took me years to figure out, and is much more difficult than the actual writing of python.
	1. Pip is the default Python package manager and works well. Learn how to use it, as well as Miniconda. If you absolutely hate the command line, look at installing Anaconda which comes with a IDE. Also, follow the [Docs](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)

6. Start writing AI/ML/NN/RL code in Python! As with all coding related endeavors, the most important part of this process is learning how to read documentation yourself. Everything you need to know is in the "man" pages and online documentation, plus there is Stack Overflow for when you get stuck. 

Now you can never touch this lame software stuff again, and just get right to working through OpenAI's [Spinning Up in Deep RL](https://spinningup.openai.com/en/latest/) to become a dope AI Alignment researcher! Haha, I kid, all of this stuff is super cool, and are the tools that you will be building your tools on top of. Sure, you can evaluate math algorithms in any software environment technically, but this is basically the industry standard that will help you play the game a lot easier.

After those six ez pz software steps, we'll move on to actually learning AI. I read the following books as introductions to the field:
- *Artificial Intelligence: A Modern Approach* by Russell & Norvig
- *Deep Learning* by Ian Goodfellow
- *Reinforcement Learning* by Sutton & Barto

I got a great foundation from those. Next, jump into a neural networks class or book and code up all of the ones you find. If you didn't already know Python, *learn here*. You can learn everything you need from Github and Stack Exchange, it just takes a while. I never *really* learned Python any other way but practice. I felt like an imposter for a long time (I still do, with an M.S.). Relax, trust the process, and with practice, you'll improve, just like every other skill in life.

Finally, go to OpenAI's [Spinning Up in Deep RL](https://spinningup.openai.com/en/latest/) to see some modern papers and implementations of Deep Reinforcement Learning, a great start for learning about AI Alignment. Try to code up some DRL stuff, and get as far as you can using Intro packages like *Stable Baselines 3* (look it up, fascinating stuff).