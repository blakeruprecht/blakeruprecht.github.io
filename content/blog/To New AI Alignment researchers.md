---
title: To New AI Alignment Researchers
date: 2023-05-25
---

If I started over, here's what I would want to get state-of-the-art right away.

1. Get a computer with MacOS or some Linux distrubition (a flavor of OS) as the operating system. If you don't know what an OS is, get a Mac (or if you just like them). Linux is great too, but you'll have to do that side quest outside of this post. Windows is plenty workable, but also a few steps harder with every software install. BSD is another good option, but if you know what that is, you don't need my advice. Ubuntu and Mac are basically the defaults for every project you'll come across.
	1. The computer just needs to work, it doesn't need to be powerful unless you are actually running big experiments, a used Lenovo Thinkpad X220 is fine. For running experiments, a good CPU, good GPU, and lots of RAM help a lot. Use what you have for now.
	2. SideQuest: Learn all about different Linux distros and gain proficiency in all of them by installing Arch Linux and figuring out how all of the pieces of the install work. This is useful and helped me learn Linux, which translated to using MacOS and WSL on Windows more proficiently. 

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