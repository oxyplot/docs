============
CategoryAxis
============

.. note:: This section is under construction. Please contribute!

.. image:: CategoryAxis.png

Example
-------

This will add X-Axis line with 3 data point on it "Feb", "Mar", "Apr". In case you want it on the Y-Axis you can change the "Position" property to "AxisPosition.Left"

.. code:: csharp

    var model = new PlotModel { Title = "Category Axis" };
    model.Axes.Add(new CategoryAxis { Position = AxisPosition.Bottom, ItemsSource = new string[] {"Feb","Mar","Apr"}});
    
    
If you want to disable the zoom effect

.. code:: csharp

    model.Axes.Add(new CategoryAxis {IsZoomEnabled = false, Position = AxisPosition.Bottom, ItemsSource = new string[] {"Feb","Mar","Apr"}});
    
In case you do not want any scrolling along this axis, it can be done by using "AbsoluteMaximum" and "AbsoluteMinimum"

.. code:: csharp

    model.Axes.Add(new CategoryAxis {IsZoomEnabled = false, AbsoluteMaximum = 2, AbsoluteMinimum = 0, Position = AxisPosition.Bottom, ItemsSource = new string[] {"Feb","Mar","Apr"}});
