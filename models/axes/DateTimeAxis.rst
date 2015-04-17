============
DateTimeAxis
============

.. note:: This section is under construction. Please contribute!

This will show date/time values on the axis.

.. image:: DateTimeAxis.png

If you are adding `DataPoint`s to a series, the `DateTime` values should be converted to numeric values by the `DateTimeAxis.ToDouble` method.

.. code:: csharp

    mySeries.Points.Add(new DataPoint(DateTimeAxis.ToDouble(myDateTime),myValue))

If you are binding `DataFieldX` or `DataFieldY` to a `DateTime`, OxyPlot will handle the conversion.

You can control the axis intervals by `IntervalType`, `MinorIntervalType` and the formatting of the axis labels by the `StringFormat` property.

The following codes are accepted by the ``StringFormat`` property

=========== =========== ============
Code        Description Example
=========== =========== ============
yyyy        year        "2011" 
yy          year        "11" 
MM          month       "01" 
MMM         month       "Jan" 
MMMM        month       "January" 
w           week number "4" 
ww          week number "04" 
dd          day         "26" 
hh          hour        "04" 
HH          hour        "16" 
mm          minute      "37" 
ss          seconds     "23" 
yyyy-MM-dd              "2011-01-26" 
MM/dd/yyyy              "01/26/2011" 
=========== =========== ============


Example
-------

.. code:: csharp

    var model = new PlotModel { Title = "DateTimeAxis" };
    model.Axes.Add(new LinearAxis { Position = AxisPosition.Bottom, Minimum = -20, Maximum = 80});
    model.Axes.Add(new LinearAxis { Position = AxisPosition.Left, Minimum = -10, Maximum = 10});
