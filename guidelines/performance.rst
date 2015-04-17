======================
Performance guidelines
======================

.. note:: This section is under construction. Please contribute!

Data binding
------------

How you add data to your model is important for the performance. For series based on the DataPointSeries you have the following options, from fast to slow:

1. Add instances based on ``IDataPoint`` directly to the Points collection
2. Set ItemsSource to a collection of IDataPoints
3. Set ItemsSource and use the `Mapping` delegate
4. Set ItemsSource and use the data field properties (this uses reflection - slow!)

Style
-----

The following style properties are important for the performance of the rendering:

- Solid lines are much faster than dashed/dotted lines
- Grid lines are slow to draw (be careful not creating too many of them)
- Unfilled markers (Plus, Cross, Star) are faster than the filled markers (Circle, Square, Diamond, Triangle)
- Square markers are faster than circles