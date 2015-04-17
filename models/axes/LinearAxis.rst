==========
LinearAxis
==========

.. note:: This section is under construction. Please contribute!

.. image:: LinearAxis.png

Example
-------

.. code:: csharp

    var model = new PlotModel { Title = "LinearAxis" };
    model.Axes.Add(new LinearAxis { Position = AxisPosition.Bottom, Minimum = -20, Maximum = 80});
    model.Axes.Add(new LinearAxis { Position = AxisPosition.Left, Minimum = -10, Maximum = 10});
