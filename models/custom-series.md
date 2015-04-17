=============
Custom series
=============

.. note:: This section is under construction. Please contribute!

How to create a custom series
=============================

You can create your own custom series by implementing the `ISeries` interface, or by deriving from one of the existing `Series` classes.
To make the series available for the tracker, you should also implement the `ITrackableSeries` interface.

Base classes
============

- ``ItemsSeries`` - base class for series that are defined by items.
- ``XYAxisSeries`` - base class for series that use X and Y axes.
- ``DataPointSeries`` - base class for series that contain a collection of `DataPoint`.