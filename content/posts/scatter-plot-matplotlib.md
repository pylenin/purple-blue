---
title: "Scatter Plots with Matplotlib"
description: "Drawing insightful scatter plots with pyplot class of Matplotlib."
date: 2020-12-24T17:56:23+05:30
draft: false
image: /img/matplotlib/scatter_plot/scatter-plot-1.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this matplotlib tutorial, we will learn to draw insightful scatter plots using the pyplot class in Matplotlib.

Matplotlib is one of the data visualization libraries in Python. The `pyplot`, a matplotlib class, is a collection of functions that helps in creating different kinds of plots. Line plots help you with analyzing trends. On the other hand, scatter plots allow you to observe the relationship between two variables and how the change in one affects the other.

#### Syntax of Scatter function

The syntax of `scatter()` function is given below.

```editorconfig
matplotlib.pyplot.scatter(x_axis_data, y_axis_data, s=None, 
                          c=None, marker=None, cmap=None, 
                          vmin=None, vmax=None, alpha=None, 
                          linewidths=None, edgecolors=None)
```

* `x_axis_data` - An array containing x-axis data
* `y_axis_data` - An array containing y-axis data
* `s` - marker size (can be scalar or array of size equal to size of x or y)
* `c` - color of sequence of colors for markers
* `marker` - marker style
* `cmap` - cmap name
* `linewidths` - width of marker border
* `edgecolor` - marker border color
* `alpha` - blending value, between 0 (transparent) and 1 (opaque)

Except `x_axis_data` and `y_axis_data`, all other parameters are optional. Their default value is None. 

#### Simple Scatter Plot

Let's plot a simple `sin` curve using scatter plot.

```python3
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 5, 50)
y = np.sin(x)

plt.scatter(x, y, color='black')
plt.show()
```

![Simple Scatter Plot](/img/matplotlib/scatter_plot/scatter-plot-2.PNG)

#### Comparing two scatter plots

Let's plot both `sin` and `cos` curves using scatter plot in the same plot.

```python3
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 5, 50)
y1 = np.sin(x)
y2 = np.cos(x)

plt.scatter(x, y1, label='Sin curve')
plt.scatter(x, y2, label='Cos curve')
plt.legend()
plt.show()
```

![Simple Scatter Plot with Numpy](/img/matplotlib/scatter_plot/scatter-plot-4.PNG)

#### Using Colors in your plot

We can set our own colour for each scatter plot by using the `c` or the `color` parameter.

```python3
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 5, 50)
y1 = np.sin(x)
y2 = np.cos(x)

plt.scatter(x, y1, label='Sin curve', c='green')
# You can also mention Hex codes of colors
plt.scatter(x, y2, label='Cos curve', color='#FF0000')
plt.legend()
plt.show()
```

The above code should produce a similar graph.

![Choosing colors in Matplotlib Scatter Plot](/img/matplotlib/scatter_plot/scatter-plot-5.png)

We can also pass in a sequence of `n` numbers to be mapped to colors.

Let's look at the below example.

```python3
import matplotlib.pyplot as plt
import numpy as np

# Fix random state for reproducibility
np.random.seed(12345)

N = 50
x = np.random.rand(N)
y = np.random.rand(N)
colors = np.random.rand(N)
plt.scatter(x, y, alpha=0.5, c=colors )
plt.show()
```

As you can see we are passing `np.random.rand(N)` array as our colours parameter. When you run this, it produces the following result.

![Passing an array as colors in Matplotlib Scatter Plot](/img/matplotlib/scatter_plot/scatter-plot-6.png)

#### Colormap

Based on the above image, it would be nice to know what each color represents. For this purpose, you can use a **colormap**.

The Matplotlib module has a number of available colormaps.

A colormap is like a list of colors, where each color has a value that ranges from 0 to 100.

Let's add a colormap to our above plot. We can add it by using `plt.colorbar()`.

```python3
import matplotlib.pyplot as plt
import numpy as np

# Fix random state for reproducibility
np.random.seed(12345)

N = 50
x = np.random.rand(N)
y = np.random.rand(N)
colors = np.random.rand(N)
plt.scatter(x, y, alpha=0.5, c=colors)
plt.colorbar()
plt.show()
```

The above code should produce the following plot.

![Add colormap to a Matplotlib Scatter Plot](/img/matplotlib/scatter_plot/scatter-plot-7.png)

#### Using different scatter symbols

Scatter symbols don't have to be circular. You can use any symbol that fits the requirement of your graph.

Let's plot a scatter plot using the `dagger` symbol. We will use the `marker` parameter to pass in necessary symbol for our plot.

```python3
import matplotlib.pyplot as plt
import numpy as np

# Fixing random state for reproducibility
np.random.seed(19680801)


x = np.arange(0.0, 50.0, 2.0)
y = x ** 1.3 + np.random.rand(*x.shape) * 30.0
s = np.random.rand(*x.shape) * 800 + 500

plt.scatter(x, y, s, c="g", alpha=0.5, marker=r'$\dagger$',
            label="Luck")
plt.xlabel("Leprechauns")
plt.ylabel("Gold")
plt.legend(loc='upper left')
plt.show()
```

![Change marker style of a Matplotlib Scatter Plot](/img/matplotlib/scatter_plot/scatter-plot-8.png)

Check out the [marker documentation of matplotlib](https://matplotlib.org/3.3.3/api/markers_api.html#module-matplotlib.markers) to learn more about markers.

#### Plotting the Iris dataset from Scikit Learn

Let's plot the **sepal length vs sepal width** from the famous iris dataset.

```python3
from sklearn.datasets import load_iris
iris = load_iris()

from matplotlib import pyplot as plt

# The indices of the features that we are plotting
x_index = 0
y_index = 1

# this formatter will label the colorbar with the correct target names
formatter = plt.FuncFormatter(lambda i, *args: iris.target_names[int(i)])

plt.figure(figsize=(10, 8))
plt.scatter(iris.data[:, x_index], iris.data[:, y_index], c=iris.target)
plt.colorbar(ticks=[0, 1, 2], format=formatter)
plt.xlabel(iris.feature_names[x_index])
plt.ylabel(iris.feature_names[y_index])

plt.tight_layout()
plt.show()
```

![Scatter Plot of sepal length vs sepal width of iris dataset](/img/matplotlib/scatter_plot/scatter-plot-9.png)

**Pylenin has a dedicated Youtube playlist for Matplotlib Tutorial. Check out our entire [Matplotlib playlist here](https://youtube.com/playlist?list=PLqEbL1vopgvs1p90E3Ig_OTY08wBTCj9B).**


