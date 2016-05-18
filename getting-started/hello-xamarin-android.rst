===============
Xamarin.Android
===============

.. note:: This section is under construction. Please contribute!


Add the OxyPlot package
-----------------------

Add the ``OxyPlot.Xamarin.Android`` NuGet package to the project. References to the portable ``OxyPlot.dll`` and the Android-specific ``OxyPlot.Xamarin.Android`` libraries will be added.


Add a PlotView control
----------------------
In your layout:

.. sourcecode:: xml
    <OxyPlot.Xamarin.Android.PlotView
        android:id="@+id/plot_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

then in your Activity/Fragment code:

.. sourcecode:: csharp

    using OxyPlot.Xamarin.Android;
    ...
    PlotView view = FindViewById<PlotView>(Resource.Id.plot_view);


Bind to a PlotModel
-------------------

.. sourcecode:: csharp
			
     view.Model = CreatePlotModel();


References
----------

The source code can be found in the `HelloWorld\\AndroidApp1 <https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/AndroidApp1>`_ folder in the `documentation-examples <https://github.com/oxyplot/documentation-examples>`_ repository.
