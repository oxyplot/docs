=================
IntervalBarSeries
=================

.. note:: This section is under construction. Please contribute!

A ``IntervalBarSeries`` shows columns defined by start and end values.

.. image:: IntervalBarSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the category axis
- ``{2}`` the category
- ``{3}`` the title of the value axis
- ``{4}`` the start value
- ``{5}`` the end value
- ``{6}`` the item title
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the start and end values with one digit, use the format string ``"{4:0.0},{5:0.0}"``.

The default format string for ``IntervalBarSeries`` is ``"{0}\n{1}: {2}\n{3}: {4}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "IntervalBarSeries" };
