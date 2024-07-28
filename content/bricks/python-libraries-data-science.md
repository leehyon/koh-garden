---
title: Python for Data Science
draft: false
tags:
  - conda
  - data-science
---

Data science involves computational techniques to extract insights from data. On the other hand, a library is a collection of pre-written code that provides a set of functionalities that can be used to solve specific programming problems.

## Prerequisites

Installation methods may include (e.g.: `scipy`):

- ~~Distributions: Anaconda~~
- pip: `pip3 install scipy`
- conda: `conda install -c conda-forge scipy` ✅
- Package manager: `sudo apt-get install python3-scipy`
- Source

With `pip` or `conda`, you can control the package versions for a specific project to prevent conflicts. System package managers, like `apt-get`, install across the entire computer, often have older versions. Source compilation is much more difficult but is necessary for debugging and development.

For more advanced users who will need to install or upgrade regularly, [Miniforge](https://github.com/conda-forge/miniforge) is a more suitable way to install the conda (and mamba, a faster conda alternative) package manager.

### Installing and managing packages in Python

#### Beginning users

- Install Anaconda (it installs all packages you need and all other tools mentioned below).
- For writing and executing code, use notebooks in [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/index.html) for exploratory and interactive computing, and [Spyder](https://www.spyder-ide.org/) or VS Code for writing scripts and packages.

#### Advanced users

Conda

- Install [Miniforge](https://github.com/conda-forge/miniforge).
- Keep the `base` conda environment minimal, and use one or more [conda environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) to install the package you need for the task or project you’re working on.

Alternative if you prefer pip/PyPI

- Install Python from python.org, Homebrew, or your Linux package manager.
- Use [Poetry](https://python-poetry.org/) as the most well-maintained tool that provides a dependency resolver and environment management capabilities in a similar fashion as conda does.

## Python libraries

### NumPy

NumPy is a low level library written in C and FORTRAN for high level mathematical functions. It provides a high-performance multidimensional **array** object, and tools for working with these arrays.

The NumPy API is used extensively in pandas, SciPy, Matplotlib, scikit-learn, scikit-image and most other data science and scientific Python packages.

```shell
# Best practice, use an environment rather than install in the base env
conda create -n ds-env
conda activate ds-env
# If you want to install from conda-forge
conda config --env --add channels conda-forge
# The actual install command
conda install numpy
```

```python
import numpy as np  # import NumPy
a = np.array([1, 2, 3, 4, 5, 6])  # initialize NumPy arrays is from Python lists
```

[NumPy: the absolute basics for beginners — NumPy v1.26 Manual](https://numpy.org/doc/stable/user/absolute_beginners.html)

### SciPy

SciPy is a collection of mathematical algorithms and convenience functions built on NumPy. It uses NumPy arrays as the basic data structure, and comes with modules for various commonly used tasks in scientific programming.

SciPy sub-packages:

- Special functions (scipy.special)
- Integration (scipy.integrate)
- Optimization (scipy.optimize)
- Interpolation (scipy.interpolate)
- Fourier Transforms (scipy.fft)
- Signal Processing (scipy.signal)
- Linear Algebra (scipy.linalg)
- Sparse Arrays (scipy.sparse)
- Sparse eigenvalue problems with ARPACK
- Compressed Sparse Graph Routines (scipy.sparse.csgraph)
- Spatial data structures and algorithms (scipy.spatial)
- Statistics (scipy.stats)
- Multidimensional image processing (scipy.ndimage)
- File IO (scipy.io)

### Matplotlib

Matplotlib is a visualization-building plotting package that is used to plot graphs and charts.

```shell
conda install -c conda-forge matplotlib  # install using conda
```

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 2 * np.pi, 200)
y = np.sin(x)

fig, ax = plt.subplots()  # create a figure containing a single axes
ax.plot(x, y)  # plot some data on the axes
plt.show()
```

[Quick start guide — Matplotlib 3.8.0 documentation](https://matplotlib.org/stable/users/explain/quick_start.html)

### scikit-learn

It is one of the best and a modern library in Machine Learning. It has the ability to supporting learning algorithms, especially unsupervised and supervised ones.

Examples of scikit-learn include the following:

- K-means
- Decision trees
- Linear and logistic regression
- Clustering

This kind of library has major components from NumPy and SciPy.

```shell
conda create -n sklearn-env -c conda-forge scikit-learn
conda activate sklearn-env
```

```python
from sklearn import linear_model
reg = linear_model.LinearRegression()
reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])
```

[scikit-learn: machine learning in Python — scikit-learn 1.3.2 documentation](https://scikit-learn.org/stable/index.html)

### pandas

For example, say you want to explore a dataset stored in a CSV on your computer. pandas will extract the data from that CSV into a DataFrame - a table, basically.

```shell
conda install -c conda-forge pandas
```

pandas is built on top of the NumPy package, meaning a lot of the structure of NumPy is used or replicated in Pandas. Data in pandas is often used to feed statistical analysis in SciPy, plotting functions from Matplotlib, and machine learning algorithms in scikit-learn.

```python
import pandas as pd

mydataset = {
  'cars': ["BMW", "Volvo", "Ford"],
  'passings': [3, 7, 2]
}

myvar = pd.DataFrame(mydataset)

print(myvar)
```

[pandas - Python Data Analysis Library (pydata.org)](https://pandas.pydata.org/)

pandas can collect data from other sources such as Excel, CSV, and even SQL databases. The pandas library consists of two structures that enable it to perform its functions correctly. That is the series, which has only one dimension and data frames that are characterized by being two-dimensional.

pandas is effective in the following areas:

- Splitting of data
- Merging of two or more types of data
- Data aggregation
- Selecting or subsetting data
- Data reshaping

### Seaborn

Seaborn is a Python data visualization library based on [matplotlib](https://matplotlib.org/). It provides a high-level interface for drawing attractive and informative statistical graphics.

```python
# Import seaborn
import seaborn as sns

# Apply the default theme
sns.set_theme()

# Load an example dataset
tips = sns.load_dataset("tips")

# Create a visualization
sns.relplot(
    data=tips,
    x="total_bill", y="tip", col="time",
    hue="smoker", style="smoker", size="size",
)
```

[An introduction to seaborn — seaborn 0.13.0 documentation (pydata.org)](https://seaborn.pydata.org/tutorial/introduction.html)

### PyTorch

Based on the Torch library, PyTorch is an open-source machine learning library used for tasks like computer vision and natural language processing.

Python 3.8 or greater

```shell
sudo apt install python3-pip
```

> [!tip]
> By default, you will have to use the command `python3` to run Python. If you want to use just the command `python`, instead of `python3`, you can symlink `python` to the `python3` binary.

[Start Locally | PyTorch](https://pytorch.org/get-started/locally/)

### Scrapy

Scrapy is another library used for creating crawling programs. 

```shell
conda install -c conda-forge scrapy
```

### statsmodels

statsmodels is a Python module that provides various statistical models and functions to explore, analyze, and visualize data. It is an open-source library that is built on top of NumPy, SciPy, and pandas libraries.

### Theano

Theano is a Python library that allows you to define, optimize, and efficiently evaluate mathematical expressions involving multi-dimensional arrays. It is built on top of [NumPy](http://numpy.scipy.org/).

```shell
conda install -c conda-forge theano
```

It is good to note that Theano works best with GPU compared to the CPU.
