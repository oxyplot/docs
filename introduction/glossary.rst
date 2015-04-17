========
Glossary
========

.. note:: This section is under construction. Please contribute!

The goal of this page is to help keep documentation, discussions, and APIs consistent.

================= ======================================================
Term              Meaning
================= ======================================================
*Plot*            Also called a graph or chart
*Plot model*      A model represents the contents of a plot
*Plot element*    An element of the plot model that can be displayed 
                  (e.g. a series, annotation or axis)
*Plot controller* Handles user input
*Plot view*       The custom control that displays the plot model and
                  communicates with the plot controller
*Axis*            A plot element that displays an axis
*Series*          A plot element that displays data
*Annotation*      Displays content that is not a series. Annotations are
                  not included in the legend and not used by the tracker
*Plot area*       The area where the series are displayed
*Legend*          Displays the titles and symbol of the series.
*Tracker*         When the user hovers or clicks on a series, the tracker
                  shows the actual values at that point
================= ======================================================




.. note:: Alternative layout (definition syntax)

Plot
    Also called a graph or chart

Plot model
    A model represents the contents of a plot

Plot element
    An element of the plot model that can be displayed 
    (e.g. a series, annotation or axis)

Plot controller
    Handles user input

Plot view
    The custom control that displays the plot model and
    communicates with the plot controller

Axis
    A plot element that displays an axis
Series
    A plot element that displays data

Annotation
    Displays content that is not a series. Annotations are
    not included in the legend and not used by the tracker

Plot area
    The area where the series are displayed

Legend
    Displays the titles and symbol of the series.

Tracker
    When the user hovers or clicks on a series, the tracker
    shows the actual values at that point

Wild deviations from these terms in the API or code should be fixed or raised as issues to fix in a future version.
