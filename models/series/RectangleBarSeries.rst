==================
RectangleBarSeries
==================

.. note:: This section is under construction. Please contribute!

A ``RectangleBarSeries`` shows rectangles defined by minimum and maximum x and y values.

.. image:: RectangleBarSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the minimum x-value (X0)
- ``{3}`` the maximum x-value (X1)
- ``{4}`` the title of the y-axis
- ``{5}`` the minimum y-value (Y0)
- ``{6}`` the maximum y-value (Y1)
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the minimum x and y values with one digit, use the format string ``"{2:0.0},{5:0.0}"``.

The default format string for ``RectangleBarSeries`` is ``"{0}\n{1}: {2} {3}\n{4}: {5} {6}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "RectangleBarSeries" };
