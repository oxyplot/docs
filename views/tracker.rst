=======
Tracker
=======

.. note:: This section is under construction. Please contribute!

The "tracker" is shown when you press down the left mouse button over some data in the plot. By default the tracker shows the values of the current point.


Format string
=============

The easiest way to modify the information shown in the tracker, is to modify the `TrackerFormatString` of the series.

The arguments are specific to each class.

|| Class || ~{0} || ~{1} || Examples |
| LineSeries | X | Y | `"{0:0.00} {1:0.00}"` |

If you need to include extra information in the tracker beyond the standard parameters (e.g. series name, x and y values), you can use the ``Series.ItemSource`` property to populate the data points (see e.g. `LineSeries <../../latest/models/series/LineSeries.html>`_ for more details).
The format string can also contain formatting codes for properties in the ``ItemSource`` list item that defines the data point closest to the tracker hit.
Use the property name inside the curly braces: `{MyProperty:0.00}`.

The culture of the tracker format string can be set in the `Culture` property in the `PlotModel`. The default culture is the current UI culture. 

Template
========

The WPF/Silverlight `Plot` controls contain a dependency property `DefaultTrackerTemplate` where a custom `ControlTemplate` can be defined.
When the tracker is shown, the `DataContext` will be set to a `TrackerHitResult`. You can bind `Position` and data properties from the hit results. 

    TODO: example template

See the `Source\Examples\WPF\CustomTrackerDemo` application for examples on how to make custom trackers.

Tracker control
===============

The WPF and Silverlight projects contain a `TrackerControl` that can be used in tracker templates.
You should bind the `Position`, `LineExtents` and `Content` properties to data in the `TrackerHitResult`.
Example

    TODO: template using TrackerControl

TrackerHitResult
================

This class contains data about the current hit of the tracker:

| `Position` | the XY screen coordinates of the tracker.|
| `DataPoint` | the data point if the tracker shows an item from a DataPointSeries.|
| `Series` | the current series.|
| `PlotModel` | the current plot model.|
| `LineExtents` | the rectangle that should be used to draw the horizontal and vertical lines.|
| `XAxis` | the current x axis.|
| `YAxis` | the current y axis.|
| `Item` | the current item if an `ItemsSource` was used to generate the data.|
| `Text` | the text to be shown in the tracker. If this property is set, the series' `TrackerFormatString` will not be used.|
 
The TrackerHitResult for the current tracker state can be obtained by handling the PlotModel.TrackerChanged event.
However, this event occurs after the text has been set on the tracker UI, so you cannot use this event handler to set custom tracker text.
 
Tracker definitions
===================

If you want to specify different trackers for the series, you should define `TrackerDefinition`s in the `Plot` control.
Set the `TrackerKey` of the series to select which `TrackerDefinition` to use.  
