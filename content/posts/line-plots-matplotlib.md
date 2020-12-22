---
title: "Line Plots with Matplotlib"
description: "Plotting line charts with pyplot class of Matplotlib."
date: 2020-12-21T23:28:20+05:30
draft: false
image: /img/matplotlib/line_plot/line_plot.png
---
<div class="sharethis-inline-follow-buttons"></div>

*By [Lenin Mishra](https://www.pylenin.com/authors/#lenin-mishra)*

In this matplotlib tutorial, we will learn to draw line plots and decorate them with labels and legends.

Matplotlib is one of the data visualization libraries in Python. The `pyplot`, a matplotlib class, is a collection of functions that helps in creating different kinds of plots. Line plots are used to represent the relation between two variables. It helps us analyze trends over time.

Let's see a few examples.

#### Simple Line Plot

```python3
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0,5,50)
y = np.exp(x)

plt.plot(x, y)
plt.title("Simple Line Plot")
plt.show()
```

The above code should produce a similar graph like below.

![Simple Line Plot with one line](/img/matplotlib/line_plot/line-plot-1.png)

#### Add multiple lines in your plot

Let's try to add multiple lines to our plot.

```python3
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0,5,50)
y1 = np.exp(x)
y2 = np.exp(x-1)
y3 = np.exp(x+1)

plt.plot(x, y1, label='Y1')
plt.plot(x, y2, label='Y2')
plt.plot(x, y3, label='Y3')
plt.title("Simple Line Plot")
plt.legend()
plt.show()
```

As you can see, we are plotting `y1`, `y2` and `y3` against `x`. In order to be able to identify the lines in our plot, we are using an extra parameter called `label`. 

The `plt.legend` function will place legends on our plot and show the `labels` that we have mentioned in our code.

The above code should produce the following plot.

![Simple Line Plot with multiple line](/img/matplotlib/line_plot/line-plot-2.png)

#### Adding X and Y labels for better graphs

The `xlabel` and `ylabel` function in pyplot module of matplotlib library is used to set the label for the x-axis and the y-axis.

Let's add the following lines of code. Make sure to add them before `plt.show()`.

```python3
plt.xlabel('X axis')
plt.ylabel('Y axis')

# Then comes plt.show()
plt.show()
```
Now you can see both x and y labels in our plot.

![Simple Line Plot with x and y labels](/img/matplotlib/line_plot/line-plot-3.png)

#### Fill the area between 2 plots

By using the `pyplot.fill_between` function, we can fill in the region between two lines in the same plot. This will help us in understanding the margin of data between two line plots based on certain conditions.

```python3
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0,5,50)
y1 = np.exp(x)
y2 = np.exp(x-1)

plt.plot(x, y1, label='Y1')
plt.plot(x, y2, label='Y2')

# `alpha` parameter is used to soften 
# colors for more visually appealing plots.

plt.fill_between(x, y1, y2, color='green', alpha=0.5) 

plt.title("Simple Line Plot")
plt.legend()
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.show()
```

![Simple Line Plot with filled area](/img/matplotlib/line_plot/line-plot-5.PNG)

#### Plotting lines in Multiple Charts/axis

Now, what if we wanted to plot graphs in different axis. For that purpose, we will use the `plt.figure` function.

```python3
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0,5,50)
y = np.exp(x)

plt.plot(x, y)
plt.title("Simple Line Plot")

# The figure() function helps in creating a 
# new figure that can hold a new chart in it. 
plt.figure() 
x1 = [2, 3, 4, 5] 
y1 = [120, 130, 140, 150] 
plt.plot(x1, y1, '-.') 
plt.title('Simple line plot in a different axis')
plt.show()
```

The above code should produce the following result.

![Simple Line Plot with different figure](/img/matplotlib/line_plot/line-plot-4.PNG)

**Pylenin has a dedicated Youtube playlist for Matplotlib Tutorial. Check out our entire [Matplotlib playlist here](https://youtube.com/playlist?list=PLqEbL1vopgvs1p90E3Ig_OTY08wBTCj9B).**



