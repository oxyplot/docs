================
TornadoBarSeries
================

.. note:: This section is under construction. Please contribute!

A ``TornadoBarSeries`` shows columns defined by a minimum, maximum and base value.

.. image:: TornadoBarSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the category axis
- ``{2}`` the category
- ``{3}`` the title of the value axis
- ``{4}`` the minimum or maximum value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the value with one digit, use the format string ``"{4:0.0}"``.

The default format string for ``TornadoBarSeries`` is ``"{0}\n{1}: {2}\n{3}: {4}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "TornadoBarSeries" };
