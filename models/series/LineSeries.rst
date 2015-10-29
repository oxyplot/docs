==========
LineSeries
==========

.. note:: This section is under construction. Please contribute!

A ``LineSeries`` is used to render data as a polyline in the plot. It is
also possible to render markers at each point of the polyline.

.. image:: LineSeries.png

Axes
----

A ``LineSeries`` requires a horizontal and a vertical axis.

By default, the ``LineSeries`` will use the default horizontal and
vertical axes in the parent ``PlotModel``. If there are more than one
horizontal/vertical axis, the axes can be specified by the ``XAxisKey``
and ``YAxisKey`` properties. This requires the ``Key`` property to be
set on the desired axes.

Data
----

Use the ``Points`` collection to add data to the ``LineSeries``:

.. code:: csharp

    lineSeries1.Points.Add(new DataPoint(0, 0));
    lineSeries1.Points.Add(new DataPoint(100, 40));

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

The ``TrackerFormatString`` property is used to format the string shown
in the `tracker <../tracker>`_. The format string may use the following arguments:

- ``{0}`` the title of the current series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the title of the y-axis
- ``{4}`` the y-value
- ``{PropertyX}`` the value of ``PropertyX`` in the nearest item (extended format string syntax)

To show the x and y values with one digit, use the format string
``"{2:0.0},{4:0.0}"``.

If an item was hit, it is also possible to use the extended format
string syntax, e.g. ``{PropertyX:0.##}``, where the value of
``PropertyX`` will be found by reflection of the item.

The default format string for ``LineSeries`` is
``"{0}\n{1}: {2:0.###}\n{3}: {4:0.###}"``

See `MSDN <http://msdn.microsoft.com/en-us/library/system.string.format(v=vs.110).aspx>`_ for more information about format strings.

The ``CanTrackerInterpolatePoints`` property should be set to ``false``
if the tracker should not interpolate values between the points. The
default value is ``true``.

The ``TrackerKey`` property may be used to specify a `custom tracker <../tracker>`_.
This makes it possible to use different trackers for each series.

Color
-----

The ``Color`` defines the color of the line. The default value is
``Automatic``. In this case the color will be set automatically from the
colors specified in the ``DefaultColors```property of the parent ``PlotModel``.
