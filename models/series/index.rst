======
Series
======

.. note:: This section is under construction. Please contribute!

Position
--------

The position of the axes is defined by the ``Position`` property.

Visibility
----------

The visibility of the series can be controlled by the ``IsVisible``
property. The default value is ``true``. If set to ``false``, the series
will not be rendered.

Title
-----

The ``Title`` property defines the title to show in the plot :doc:`../legend`.
The default value is ``null`` (not shown in legend).

Background
----------

If the ``Background`` property is set to a color, the area defined by
the X and Y axes will be filled with the specified color. The default
value is ``Undefined`` (not showing a background).

Tracker
-------

The `TrackerFormatString` property is used to format the string shown in the :doc:`../../views/tracker`. The arguments that can be used for the format string is documented for each series.

If an item was hit, it is also possible to use the extended format string syntax, e.g. ``{PropertyX:0.##}``, where the value of ``PropertyX`` will be found by reflection of the item.

See `MSDN <http://msdn.microsoft.com/en-us/library/system.string.format(v=vs.110).aspx>`_ for more information about format strings.


.. toctree::

    AreaSeries.rst
    BarSeries.rst
    BoxPlotSeries.rst
    CandleStickSeries.rst
    ColumnSeries.rst
    ContourSeries.rst
    ErrorColumnSeries.rst
    FunctionSeries.rst
    HeatMapSeries.rst
    HighLowSeries.rst
    HistogramSeries.rst
    IntervalBarSeries.rst
    LineSeries.rst
    PieSeries.rst
    RectangleBarSeries.rst
    ScatterSeries.rst
    StairStepSeries.rst
    StemSeries.rst
    TornadoBarSeries.rst
    TwoColorAreaSeries.rst
    TwoColorLineSeries.rst
