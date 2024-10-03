---
title: Python scientific computing packages
date: 2024-03-17
description: '"The core useful Python packages for scientific computing are Numpy to make arrays, Scipy for math equations, Pandas for data manipulation, and Matplotlib for visualizations. I go over briefly the basic usage of each."'
---
I've done 5 years of science research and development using mainly Python, and have used the major scientific computing libraries. While this topic may seem intimidating, the actual usage of each library is typically pretty brief (a few lines of code), so you don't need to be an expert in each library, you just need to generally know what they do so you can use them when you need to. Here's a brief overview with some of the most common code explained.

## Installation
All of these package are heavily-used scientific computing Python packages, so they're available through pip or conda (the two main Python package managers).
- Pip or Conda? I use pip as much as I can since it's simple, and then I use Conda when I can't find something on pip.
- `pip install numpy pandas matplotlib` # Just type em out, no need for commas
- `conda install -c conda-forge numpy pandas matplotlib` # Same, but specify conda-forge for the channel (-c) because cf is cool.

## For arrays: Numpy
Numpy is the library you use to turn data into arrays in Python. It is open source on [Github](https://github.com/pandas-dev/pandas). You can use these arrays to perform linear algebra. Back before PyTorch/TensorFlow and tensors, Numpy was the only good way to create arrays in Python. Now, for AI, you'll probably use Tensors more, but arrays are still great to know how to use.

General Usage
- `import numpy as np` # Everyone imports numpy as 'np' for efficiency lol

Creating Arrays
- A Numpy array is called an `ndarray`
- An `ndarray` is processed much faster than a normal `list`
- An array holds one type of data, e.g. floats, so it can't store stuff like words and numbers together. For that, use a Pandas dataframe.
- Once created, the size of the array can't change, but the items within the array are mutable i.e. you can change them
  - WIP: The bracket formatting got messed up, I will fix this later...
- `a1D = np.array([1, 2, 3, 4])` # Creates a 1D array... and so on
- `a2D = np.array([[1, 2], [3, 4]])` # Create a 2D array
- `a3D = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])` # Create a 3D array
- You can create arrays using `np.ones()`, `np.zeros()`, `np.arange()`, `np.linspace()`, `np.eye()`, and more functions for specific behaviors.

Indexing Arrays
- `a1D[:3]` returns `array([1,2,3])`, the 0th-2nd elements of the array
- `a2D[0,1]` returns `2`, the element in row `0`, column `1` 
- `a2D.shape` prints out `(2, 2)` the dimensions of the array

## For loading data: Pandas
Pandas is a great all-around data analysis toolkit for scientific computing. Free and open-source on [Github](https://github.com/pandas-dev/pandas). I pretty much use it to load external files. For AI, this is crucial, since you're often loading external datasets. It also does a great job at a variety of tasks like handling missing data, merging datasets together, converting other Python/Numpy datasets into Pandas Dataframes, and more, but I mostly use the same three lines.

It's pretty easy to install Pandas since it's a heavily used Python package, it's available through Pip and Conda.

General Usage
- `import pandas as pd` # Are you seeing a theme?
- `data = {'column1': [1, 2, 3], 'column2': [4, 5, 6]}` # An example dict
- `df_dict = pd.DataFrame(data)` # Create a dataframe (df) from the `data` dictionary declared above
- `df_csv = pd.read_csv('file.csv')` # Create a df from a csv file
- `df_xlsx = pd.read_excel('file.xlsx')` # Create a df from an Excel file
- `df['column1']` select the data in column1
- `df[['column1','column2']]` # Select the data in columns 1 and 2
- You can do a lot with selecting which columns and rows you want, ommitting data, replacing bad data with NaNs, handling missing data
- `df.isnull()` # Check if there are any NULL values in the df
- `df.fillna(0, inplace=True)` # Replace missing values with a 0
- `df.to_csv('filename.csv', index=False)` # Save the data into a file of your choice

## For scientific algorithms: Scipy
Scipy is a package built on Numpy that adds a lot of built-in functions to run integrations, optimization, interpolation, signal processing, linear algebra, Fourier transforms, eigenvalues, and more. Yes, as you can already see, there is some overlap between different packages. Free and open source on [Github](https://github.com/scipy/scipy).

Scipy is not an everyday style of package, you'll use it more for specific scenarios, so as such, there's not really any code you should memorize. Moreso, just be aware of what kinds of things Scipy can do, and know that you don't need to reinvent the whell every time you want to integrate or optimize an equation.

## For making visualizations: Matplotlib
The go-to plotting tool for making data visualizations. Free and open source on [Github](https://github.com/matplotlib/matplotlib). You can make the following types of plots:
- **Pairwise**: plot(x,y), scatter(x,y), bar(x,height), stem(x,y), fill_between(x,y1,y2), stackplot(x,y), stairs(values)
- **Statistical**: hist(x), boxplot(x), errorbar(x,y,yerr,xerr), violinplot(D), eventplot(D), hist2d(x,y), hexbin(x,y,C), pie(x), ecdf(x)
- **Gridded**: imshow(Z), pcolormesh(X,Y,Z), contour(X,Y,Z), contourf(X,Y,Z), barbs(X,Y,U,V), quiver(X,Y,U,V), streamplot(X,Y,U,V)
- Plus Irregular Gridded Data and 3D and Volumetric data

General Usage
- `import matplotlib.pyplot as plt` # This one's a mouthful, but you'll typically see "plt" everywhere
- `fig, ax = plt.subplots()` # Create the figure
- `ax.plot([1, 2, 3, 4], [1, 4, 2, 3])` # Plot some data on the Axes.
- `plt.show()` # Show the figure.

Editing the plot
![[matplotlib_commands.png]]

## For more visualizations: Seaborn
Check out Seaborn if you need more advanced viz than matplotlib. I've never used it, but I've heard it's cool.
