---
date: 2024-03-04
title: Python
description: The hardest part of coding in Python is setting up the coding environment. Downloading all of the software and making sure it's all in the right place will stop your Python journey before you even start.
---
General-purpose programming language. Easy to learn, widely used for AI/data science. Free to download, free packages, it's awesome

**Install Python**
1. Download the latest version of Python from [python.org/downloads](https://python.org/downloads)
2. Check "add to PATH" during install
	- Note, if you download python and it doesn't run, it's most like because the python executable file is not in your PATH variable.
3. Open a [terminal](/terminal) and type `python --version` to verify installation
	- Some systems require you to type `python3` to run python, annoying.

**Run Python code**
1. Create a file with the .py extension, e.g. `test.py`
	- Use a text editor to write code in test.py, e.g. you could add:
		- `print("hello world!")` <-- that's python code right there
2. In the [terminal](/terminal), navigate to the folder that contains test.py
3. Run `python test.py` in the terminal to execute the python script.

**Install Python packages**
- NOTE: A package is an extension of Python that adds more functionality. Most packages only really do 1 or 2 things and aren't very hard to learn.
1. In a [terminal](/terminal), run the command `pip install name`, and replace name with the name of the package you want, which is often different from the marketing name of the package. Here are some solid starter packages for data analysis:
	- `pandas` = for importing data (in .csv, etc) and using it
	- `numpy` = put imported data into an array/matrix and manipulate it
	- `matplotlib` = for plotting graphs
	- `scipy` = has fancy math equations
	- `torch` = huge package has all the modern AI/ML stuff (this is PyTorch)

