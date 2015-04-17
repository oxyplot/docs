=============
HeatMapSeries
=============

.. note:: This section is under construction. Please contribute!

A ``HeatMapSeries`` shows a 2D array of values as a heat map.

.. image:: HeatMapSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the title of the y-axis
- ``{4}`` the y-value
- ``{5}`` the title of the value/color-axis
- ``{6}`` the color-value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the x and y values with one digit, use the format string ``"{2:0.0},{4:0.0}"``.

The default format string for ``HeatMapSeries`` is ``"{0}\n{1}: {2}\n{3}: {4}\n{5}: {6}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "HeatMapSeries" };
