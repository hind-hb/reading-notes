# [Matplotlib](https://github.com/rougier/matplotlib-tutorial)


Most used package for 2-D graphics. 

> Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib: figure size and dpi, line width, color and style, axes, axis and grid properties, text and font properties and so on. While matplotlib defaults are rather good in most cases, you may want to modify some properties for specific cases.

For example, we can change some of the line properties, including color and thickness, using the commands below.

```Python
plt.figure(figsize=(10,6), dpi=80)
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
```

Setting ticks along the Y-axis
```Python
plt.yticks([-1, 0, +1])
```

Setting tick labels along an X-axis
```Python
plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
       [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$'])
```

Add a legend.

```Python
plt.legend(loc='upper left', frameon=False)
```

Overall, there's a ton of cool code to make different kinds of visualizations - scatterplots, 3-D graphs, animate circles or earthquakes, contour graphs, etc. 

## Bokeh

Bokeh is an interactive visualization library that targets modern web browsers for presentation. It is good for:

Interactive visualization in modern browsers
Standalone HTML documents, or server-backed apps
Expressive and versatile graphics
Large, dynamic or streaming data
Easy usage from python (or Scala, or R, or...)
