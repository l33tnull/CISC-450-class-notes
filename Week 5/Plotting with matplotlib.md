- first create a plot with `pyplot`
	- import library using dot notation
		- Ex: `import matplotlib.pyplot as plt`

### `pyplot`

- can display different objects within a figure

| **Object Name**      | **What it Does**                                                                                                       |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `plt.plot(x, y)`     | - where `x` and `y` are arrays of the same size<br>	- creates a line plot connecting consecutive x- and y- coordinates |
| `plt.scatter(x, y)`  | - creates a scatter plot showing all pairs of x- and y- coordinates                                                    |
| `plt.figure()`       | - creates a new figure                                                                                                 |
| `plt.show()`         | - displays the figure and all the objects the figure contains                                                          |
| `plt.savefig(fname)` | - saves the figure in the current working directory with the filename `fname`                                          |
>[!Note] 
>`plt.figure()` is only needed when changing the default size of the figure. The size of the figure can be specified using the `figsize` parameter. Since a figure is implicitly created whenever `plt.plot(x, y)` or `plt.scatter(x, y)` functions are called, calling `plt.figure()` is not necessary if the default figure size is acceptable.
>
>When using Jupyter Notebooks or any other IDLE, all the elements of each figure is automatically displayed when the cell or line of code is ran so `plt.show()` is only necessary when `matplotlib` is used in a script or terminal.

![](../Images/Images/IMG-20260914170142707.png)