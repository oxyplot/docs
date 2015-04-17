====
Axes
====

.. note:: This section is under construction. Please contribute!

// TODO - add more info, clean text, add examples

OxyPlot contains the following axis types:

LinearAxis  Represents a numerical axis with a linear scale. 
LogarithmicAxis  Represents a numerical axis with a logarithmic scale. 
DateTimeAxis  Represents a date/time axis based on `DateTime` values. 
TimeSpanAxis  Represents a time axis based on `TimeSpan` values. 
CategoryAxis  Represents an axis that displays categories (typically used for bar/column series). 
LinearColorAxis  Represents an axis that displays a linear color scale. 
RangeColorAxis  Represents an axis that displays a colors for specified ranges. 
MagnitudeAxis  Represents the radial axis in polar plots 
AngleAxis  Represents the angular axis in polar plots 
  
Position
--------

The most important propert of the axis is the `Position`. This property determines where the axis is drawn. A standard XY plot requires a horizontal axis (bottom or top position) and a vertical axis (left or right position).


Title
-----

The title is shown next to the axis. 

About position and rotation of titles.

About ``Unit``


Minimum/Maximum
---------------

These properties defines the minimum and maximum values on the axis. If any of them are not specified, they will be calculated from the data. In that case, a "padding" value will be included to make sure there is some whitespace outisde the extreme values.


Major/minor intervals
---------------------

The major intervals define the steps between the numeric labels on the axis. The minor intervals define the sub-division between the labels. 

Major and minor ticks may be drawn at each interval. The style can be defined (inside, outside, crossing or none)

Grid lines can also be drawn at each interval. These will be drawn across the whole plot area. The style can be defined by color, thickness and line style. 


StartPosition/EndPosition
-------------------------

The start and end position properties are used to define the relative position of the axis. The default values [0,1] will fill the available plot area. 

To reverse the direction of an axis, set `StartPosition = 1` and `EndPosition = 0`


Axis keys
---------

How to use `AxisKey`...


Adding axes in XAML
-------------------

.. code:: xml

    <oxy:Plot Title="Linear axes">
        <oxy:Plot.Axes>
            <oxy:LinearAxis Position="Bottom" Minimum="-20" Maximum="80" />
            <oxy:LinearAxis Position="Left" Minimum="-10" Maximum="10" />
         </oxy:Plot.Axes>
    </oxy:Plot>


Adding axes to a PlotModel
--------------------------

.. code:: csharp

    var model = new PlotModel();
    model.Axes.Add(new LinearAxis(AxisPosition.Bottom, -20, 80));
    model.Axes.Add(new LinearAxis(AxisPosition.Left, -10, 10));

If no axes are defined, linear axes will be added to the bottom and left.


Axis types
----------

.. toctree::

    LinearAxis.rst
    LogarithmicAxis.rst
    DateTimeAxis.rst
    TimeSpanAxis.rst
    CategoryAxis.rst
    LinearColorAxis.rst
    RangeColorAxis.rst
    MagnitudeAxis.rst
    AngleAxis.rst



