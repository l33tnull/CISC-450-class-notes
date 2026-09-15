# Labeling Plots


| **Function Name**             | **What it Does**                                                             |
| ----------------------------- | ---------------------------------------------------------------------------- |
| `plt.title()`                 | - add title to a figure                                                      |
| `plt.xlabel()`                | - adds text for the x-axis                                                   |
| `plt.ylabel()`                | - adds text for the y-axis                                                   |
| `plt.text(x, y, s)`           | - adds string `s` to the figure at coordinates `(x, y)`                      |
| `plt.annotate(s, xy, xytext)` | - links string `s` at coordinates given by `xytext` to a point given by `xy` |
| `plt.legend()`                | - adds legend in the figure                                                  |
> [!Note]
> Adding mathematical expressions using LaTeX is supported. It can be done by enclosing an expression within a string with dollar signs. The letter `r` should precede a string so that a backslash is not treated as a Python escape. 
> Ex: `plt.title(r'Standard normal distrobution $f(x) = \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}x^2}$')` 

![](../Images/Images/IMG-20260914185040972.png)

### `arrowprops=dict()`

|Option|Purpose|
|---|---|
|`arrowstyle`|Shape of the arrow, such as `"->"`, `"<->"`, or `"-\|>"`|
|`connectionstyle`|Shape of the shaft, such as `"arc3,rad=0.3"` for a curve|
|`color`|Overall arrow color|
|`linewidth` or `lw`|Arrow outline width|
|`alpha`|Transparency from 0 (invisible) through 1 (opaque)|
|`shrinkA`|Space between the arrow start and its object, in points|
|`shrinkB`|Space between the arrow tip and its target, in points|
|`headwidth`|Width of a simple arrowhead|
|`headlength`|Length of a simple arrowhead|
 - Ex: 
	 `arrowprops=dict(`
    `arrowstyle="->",`
    `connectionstyle="arc3,rad=0.3",`
    `color="blue",`
    `lw=2,`
    `shrinkA=5,`
    `shrinkB=5`
	`)`