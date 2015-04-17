============
TimeSpanAxis
============

.. note:: This section is under construction. Please contribute!

This axis will show ``TimeSpan`` values on the axis.

.. image:: TimeSpanAxis.png

If you are adding `DataPoint`s to a series, the `TimeSpan` values should be converted to numeric values by the `TimeSpanAxis.ToDouble` method.

.. code:: csharp

    mySeries.Points.Add(new DataPoint(TimeSpanAxis.ToDouble(myTimeSpan), myValue))

If you are using `DataFieldX` or `DataFieldY` to bind to a `TimeSpan`, OxyPlot will handle the conversion.

The formatting of the axis labels can be controlled by the `StringFormat` property.


Example
-------

.. code:: csharp

    var model = new PlotModel { Title = "TimeSpanAxis" };
    model.Axes.Add(new LinearAxis { Position = AxisPosition.Bottom, Minimum = -20, Maximum = 80});
    model.Axes.Add(new LinearAxis { Position = AxisPosition.Left, Minimum = -10, Maximum = 10});
