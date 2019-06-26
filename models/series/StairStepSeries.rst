===============
StairStepSeries
===============

.. note:: This section is under construction. Please contribute!

A ``StairStepSeries`` shows a stairstep curve at each data point. It is
also possible to render markers at each point of the stairstep curve.

.. image:: StairStepSeries.png

Axes
----

A ``StairStepSeries`` requires a horizontal and a vertical axis.

By default, the ``StairStepSeries`` will use the default horizontal and
vertical axes in the parent ``PlotModel``. If there are more than one
horizontal/vertical axis, the axes can be specified by the ``XAxisKey``
and ``YAxisKey`` properties. This requires the ``Key`` property to be
set on the desired axes.

Data
----

Use the ``Points`` collection to add data to the ``StairStepSeries``:

.. code:: csharp

    stairStepSeries1.Points.Add(new DataPoint(0, 0));
    stairStepSeries1.Points.Add(new DataPoint(10, 5));
    stairStepSeries1.Points.Add(new DataPoint(20, 8));

Alternatively, you can specify a collection in the ``ItemsSource``
property.

- If the ``Mapping`` property is set, each element in the collection
  will be transformed
- If the collection is a list of ``DataPoint``, or a type that implements ``IDataPointProvider``, it will be used with no
  mapping
- If the ``DataFieldX`` and ``DataFieldY`` properties are set, each
  element of the collection will be reflected to create a data point

Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the title of the y-axis
- ``{4}`` the y-value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the x and y values with one digit, use the format string ``"{2:0.0},{4:0.0}"``.

The default format string for ``StairStepSeries`` is ``"{0}\n{1}: {2:0.###}\n{3}: {4:0.###}"``

Color and Style
---------------

The ``Color`` defines the color of the line. The default value is
``Automatic``. In this case the color will be set automatically from the
colors specified in the ``DefaultColors`` property of the parent ``PlotModel``.

The ``LineStyle`` defines the line style. The default is ``Solid``. You can also
qualify the ``VerticalLineStyle``, which also has the default ``Solid``.

Example
-------

.. sourcecode:: csharp

    // prepare the model
    var model = new PlotModel()
    {
        Title = "Gillespie Simulation",
        LegendPlacement = LegendPlacement.Outside,
        LegendPosition = LegendPosition.TopCenter,
        LegendOrientation = LegendOrientation.Horizontal
    };

    // add two linear axes
    model.Axes.Add(new LinearAxis() { Title = "Time (hours)", Position = AxisPosition.Bottom });
    model.Axes.Add(new LinearAxis() { Title = "Count", Position = AxisPosition.Left });

    // initialise series
    var stairStepSeries1 = new StairStepSeries() { Title = "Species 1" };
    model.Series.Add(stairStepSeries1);
    var stairStepSeries2 = new StairStepSeries() { Title = "Species 2" };
    model.Series.Add(stairStepSeries2);

    // perform simple Gillespie simulation
    var rnd = new Random(0);
    double sampleExponentialDistribution(double λ) => System.Math.Log(1 - rnd.NextDouble()) / -λ;
    int s1 = 10;
    int s2 = 0;

    double t = 0;
    while (true)
    {
        // add data-points to series
        stairStepSeries1.Points.Add(new DataPoint(t, s1));
        stairStepSeries2.Points.Add(new DataPoint(t, s2));

        if (s1 + s2 == 0)
        {
            break;
        }

        var r1 = 0.2 * s1;
        var r2 = 0.1 * s2;
        t += sampleExponentialDistribution(r1 + r2);
        if (rnd.NextDouble() * (r1 + r2) < r1)
        {
            s1--;
            s2++;
        }
        else
        {
            s2--;
        }
    }
