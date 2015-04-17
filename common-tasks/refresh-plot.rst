=================
Refreshing a plot
=================

.. note:: This section is under construction. Please contribute!

The OxyPlot views do not automatically refresh when you change the ``PlotModel`` (e.g. changing series, axes, annotations or properties).

To update the plot, you must do one of the following alternatives:

- Change the ``Model`` property of the ``PlotView`` control
- Call ``Invalidate`` on the ``PlotView`` control
- Call ``Invalidate`` on the ``PlotModel``

Examples
--------