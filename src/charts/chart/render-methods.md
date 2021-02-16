<!-- markdownlint-disable MD036 -->

# Rendering Types

Chart uses following rendering methods.

* SVG
* Canvas

## SVG

SVG is used to render Chart by default for all browsers except IE8 and old versions.

## Canvas

You can switch between SVG and Canvas rendering by using the `EnableCanvas` option. The canvas mode rendering is used in the following scenarios,

* Plotting large number of data points.
* Performing high frequency live updates.

**Limitations**

* Animation is not supported.

## See Also

* [Data label](./data-labels)
* [Tooltip](./tool-tip)
* [Legend](./legend)
* [Marker](./data-markers)