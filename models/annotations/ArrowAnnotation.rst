===============
ArrowAnnotation
===============

.. note:: This section is under construction. Please contribute!

To add an arrow to your `PlotModel`:

.. code:: csharp

    var arrowAnnotation = new ArrowAnnotation { 
        StartPoint = new DataPoint(0, 0), 
        EndPoint = new DataPoint(10, 10) 
    };
    myPlotModel.Annotations.Add(arrowAnnotation);

- The ``ArrowDirection`` property can be used to create an arrow that has a fixed size in screen coordinates. If this property is set, the ``StartPoint`` property is not used.
- ``HeadLength``, ``HeadWidth`` and ``Veeness`` controls the shape of the arrow head. The values are relative to the thickness.
- The ``Text`` property can be used to set text that is shown at the start point of the arrow. The alignment is automatic and related to the direction of the arrow.
