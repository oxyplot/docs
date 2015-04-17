=================
ErrorColumnSeries
=================

.. note:: This section is under construction. Please contribute!

An ``ErrorColumnSeries`` shows a column series with error indicators.

.. image:: ErrorColumnSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the value
- ``{Error}`` the error value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the error value with one digit, use the format string ``"{Error:0.0}"``.

The default format string for ``ErrorColumnSeries`` is ``"{0}\n{1}: {2}, Error: {Error:0.###}"``


Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "ErrorColumnSeries" };
