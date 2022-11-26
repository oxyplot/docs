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

The most important property of the axis is the `Position`. This property determines where the axis is drawn. A standard XY plot requires a horizontal axis (bottom or top position) and a vertical axis (left or right position).

The `PositionTier` property allows the user to control how axis with the same position are arranged: axes with a lower `PositionTier` will be positioned closer to the plot area. If two axis have the same `PositionTier` will occupy the same margin: this can be useful if you want two non-overlapping axes on one side of a plot.


Title
-----

The title is shown next to the axis, and is controlled by the `Title` property.

The title is rotated to align with the axis: a horizontal axis with have a horizontally aligned title; a vertical axis with have 

The position of the title along the axis is determined by the `TitlePosition` property. The default is `0.5`, which positions the title half way along the axis (i.e. in the middle)

The `AxisTitleDistance` properties determines the spacing between the axis tick labels and the title.

An optional unit can be specified with the `Unit` property. The `TitleFormatString` property determines how the title and unit are rendered if a unit is specified. It has a default value of `{0} [{1}]`, where `{0}` expands to the title, and `{1}` expands to the unit.

The title font can be configured with the `TitleFont`, `TitleFontSize`, `TitleFontWeight`, and `TitleColor` properties. By default, these are derived from properties on the `PlotModel`.


Minimum/Maximum
---------------

These properties defines the minimum and maximum values on the axis. If any of them are not specified, they will be calculated from the data. In that case, a "padding" value will be included to make sure there is some whitespace outside the extreme values.

The `ViewMinimum` and `ViewMaximum` are set when the user zooms or pans the axis, and override the `Minimum` and `Maximum` values, and the default range when not `NaN`.

The `AbsoluteMinimum` and `AbsoluteMaximum` properties restrict how far the user can pan. The `MinimumRange` and MaximumRange` properties restrict how far the user can zoom.

You can determine the actual logical range of an axis by interrogating the readonly `ActualMaximum` and `ActualMinimum` properties. The visible range (which may be wider than the actual range if a data margin is set) is indicated by the readonly `ClipMinimum` and `ClipMaximum` properties.


Padding and data margins
------------------------

By default, axes will be scaled to show all the data that is associated with them. To ensure that the data are visible, padding and margins can be added.

The `MinimumPadding` and `MaximumPadding` properties (default value `0.02`) will expand the range presented by the axis by the given proportion of the data range. For example, setting `MinimumPadding = 0.1` and `MaximumPadding = 0` would decrease the minimum value shown on the axes by 10% of the data range, but leave the maximum equal to the maximum data value observed.

The `MinimumDataMargin` and `MaximumDataMargin` properties (default value `0`) also increase the data-range shown by the axis, but directly increase the amount of screen-space available. They are useful if you want a consistent margin around your data, regardless of the plot dimensions.


Major/minor intervals
---------------------

The major intervals define the steps between the numeric labels on the axis. The minor intervals define the sub-division between the labels. 

Major and minor ticks may be drawn at each interval. The `TickStyle` property determines the style of the ticks, and is either `Inside`, `Outside` (the default), `Crossing`, or `None`.

The length and color of major and minor ticks are determined by the `MajorTickSize`, `MinimumTickSize`, and `TicklineColor`.

By default, intervals are computed automatically based on the screen space available for an axis and the `IntervalLength` property. The `IntervalLength` determines the maximum amount of scree space between major ticks.

The major and minor intervals can set directly by setting the `MajorStep` and `MinorStep` properties to a non-`NaN` value.

You can override the tick computation mechanism by overriding the `Axis.GetTickValues` method.


Grid lines
----------

Grid lines can be added, aligned with the axis ticks.

Their style depends on the `MajorGridlineColor`, `MajorGridlineStyle`, `MajorGridlineStyle`, `MajorGridlineThickness`, and corresponding properties for minor intervals.

By default, no grid lines are shown as the `MajorGridlineStyle` and `MinorGridlineStyle` default to `LineStyle.None`.

Gridline thickness also determines the thickness of ticks.

Additional grid lines can be added that do not correspond to interval ticks. An additional grid line will be shown for every value in the `ExtraGridlines` property (a `double[]`).

These are formatted by the `ExtraGridlineColor`, `ExtraGridlineStyle`, and `ExtraGridlineThickness` properties.


Tick labels
-----------

Labels are added to every major tick on any axis. By default, the format of the string depends on the `Axis.StringFormat` property. If this property is `null`, then a default of `g6` is used.

You can use a custom formatter by specifying the `Axis.LabelFormatter` - a `Func<double, string>` - or by overriding the `Axis.FormatValueOverride` method.

The angle of the axis labels is determined by the `Angle` property.

Additional spacing can be added between the axis ticks and their labels with the `AxisTickToLabelDistance` property (default value `4`).


StartPosition/EndPosition
-------------------------

The start and end position properties are used to define the relative position of the axis. The default values [0,1] will fill the available plot area. 

To reverse the direction of an axis, set `StartPosition = 1` and `EndPosition = 0`.

The screen space available to the axis can be further controlled with the `MinimumMargin` and `MaximumMargin` properties (default value `0`), which allow you to add a fixed margin between axes (i.e. one that does not depend on the dimensions of the plot).


Axis keys
---------

Axes can be assigned an axis key, which should be a unique string that identifies the key. The default value of the `Axis.Key` property is `null`.

Using axis keys is essential when creating plots with many axes, as it enables you to assign series to the appropriate axes (for example, with the `LineSeries.XAxisKey` and `LineSeries.YAxisKey` properties).


Adding axes to a PlotModel
--------------------------

.. code:: csharp

    var model = new PlotModel();
    model.Axes.Add(new LinearAxis(AxisPosition.Bottom, -20, 80));
    model.Axes.Add(new LinearAxis(AxisPosition.Left, -10, 10) { Key = "y1" });
    model.Axes.Add(new LinearAxis(AxisPosition.Right, -10, 10) { Key = "y2" });

If no axes are defined, linear axes will be added to the bottom and left.


Axis lines
----------

An axis line can be drawn along an axis.

Its style depends on the `AxislineStyle`, `AxislineColor`, and `AxislineThickness` properties.

By default, `AxislineStyle` is set to `LineStyle.None`, so no line is drawn. The default color is black, and the default thickness is `1`.


Filtering
---------

An axis can be configured to filter values within a range, or based on a custom function. The behaviour of the filter is determined by the series that use the axis, and the properties do not influence the layout or rendering of the axis itself.

The `FilterMinValue` and `FilterMaxValue` determine the range of values to be allowed on the axis. By default, any value is allowed (except `NaN`).

The `FilterFunction` property (a `Func<double, bool>`) can be set to provide a custom filter function.



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



