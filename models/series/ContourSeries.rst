=============
ContourSeries
=============

.. note:: This section is under construction. Please contribute!

A ``ContourSeries`` renders a 2D array of values as contours.

.. image:: ContourSeries.png

Axes
----

Data
----

Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the title of the y-axis
- ``{4}`` the y-value
- ``{5}`` the title of the contour level axis
- ``{6}`` the contour level
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the contour level with one digit, use the format string ``"{6:0.0}"``.

The default format string for ``ContourSeries`` is ``"{0}\n{1}: {2}\n{3}: {4}\n{5}: {6}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "ContourSeries" };
