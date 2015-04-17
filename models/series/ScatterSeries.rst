=============
ScatterSeries
=============

.. note:: This section is under construction. Please contribute!

A ``ScatterSeries`` shows a set of points. The points can also have a size and color value.

.. image:: ScatterSeries.png

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
- ``{5}`` the title of the value/color-axis
- ``{6}`` the color-value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the x and y values with one digit, use the format string ``"{2:0.0},{4:0.0}"``.

The default format string for ``ScatterSeries`` is ``"{0}\n{1}: {2:0.###}\n{3}: {4:0.###}"``



Example
-------

.. sourcecode:: csharp

    var model = new PlotModel { Title = "ScatterSeries" };
    var scatterSeries = new ScatterSeries { MarkerType = MarkerType.Circle };
    var r = new Random(314);
    for (int i = 0; i < 100; i++)
    {
        var x = r.NextDouble();
        var y = r.NextDouble();
        var size = r.Next(5, 15);
        var colorValue = r.Next(100, 1000);
        scatterSeries.Points.Add(new ScatterPoint(x, y, size, colorValue));
    }

    model.Series.Add(scatterSeries);
    model.Axes.Add(new LinearColorAxis { Position = AxisPosition.Right, Palette = OxyPalettes.Jet(200) });
