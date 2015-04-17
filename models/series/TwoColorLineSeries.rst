==================
TwoColorLineSeries
==================

.. note:: This section is under construction. Please contribute!

A ``TwoColorLineSeries`` shows a line where the the color is different above and below a specified limit.

.. image:: TwoColorLineSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the title of the y-axis
- ``{4}`` the y-value

To show the x and y values with one digit, use the format string ``"{2:0.0},{4:0.0}"``.

The default format string for ``TwoColorLineSeries`` is ``"{0}\n{1}: {2:0.###}\n{3}: {4:0.###}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "TwoColorLineSeries" };
