======
Legend
======

.. note:: This section is under construction. Please contribute!

Overview
--------

For a legend to appear, the ``Series.Title`` property must be set.  

Basic Options
-------------
Legend options are specified in the ``PlotModel``.

1. LegendPlacement
  * Place the legends inside/outside the plot area
2. LegendPosition
  * Place the legend box in the top/middle/bottom left/center/right corner
3. LegendOrientation
  * Orient the items horizontally/vertically
4. LegendBackground
  * Gets or sets the background color of the legend. Defaults to no background
5. LegendFontSize
  * Set the size of the legend font
6. LegendMaxWidth
  * Set the max width of the legend
7. LegendMaxHeight
  * Set the max height of the legend
8. IsLegendVisible
  * Show/hide the legend. If the ``Title``s of the chart's series are properly set, defaults to showing the legend.
  
Example
-------

.. code:: csharp

    var model = new PlotModel();
    model.LegendPosition = LegendPosition.BottomCenter;
    model.LegendPlacement = LegendPlacement.Outside;
    model.LegendOrientation = LegendOrientation.Horizontal;
                
    var lineSeries = new LineSeries()
    { 
      Title = "MyTitle", //this is required for legends
      ItemsSource = dataPoints
    }
    model.Series.Add(lineSeries);
