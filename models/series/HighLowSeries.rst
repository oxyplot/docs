=============
HighLowSeries
=============

.. note:: This section is under construction. Please contribute!

A ``HighLowSeries`` shows a set of points. The points can also have a size and color value.

.. image:: HighLowSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the high value
- ``{4}`` the low value
- ``{5}`` the open value
- ``{6}`` the close value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the close value with one digit, use the format string ``"{6:0.0}"``.

The default format string for ``HighLowSeries`` is ``"{0}\n{1}: {2}\nHigh: {3:0.###}\nLow: {4:0.###}\nOpen: {5:0.###}\nClose: {6:0.###}"``



Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "HighLowSeries" };
