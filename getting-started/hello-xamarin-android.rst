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

	using OxyPlot;
	using OxyPlot.Axes;
	using OxyPlot.Series;
	...		
    view.Model = CreatePlotModel();
     
    private PlotModel CreatePlotModel()
	{	
		var plotModel = new PlotModel { Title = "OxyPlot Demo" };
	
		plotModel.Axes.Add(new LinearAxis { Position = AxisPosition.Bottom });
		plotModel.Axes.Add(new LinearAxis { Position = AxisPosition.Left, Maximum = 10, Minimum = 0 });
	
		var series1 = new LineSeries
		{
			MarkerType = MarkerType.Circle,
			MarkerSize = 4,
			MarkerStroke = OxyColors.White
		};
	
		series1.Points.Add(new DataPoint(0.0, 6.0));
		series1.Points.Add(new DataPoint(1.4, 2.1));
		series1.Points.Add(new DataPoint(2.0, 4.2));
		series1.Points.Add(new DataPoint(3.3, 2.3));
		series1.Points.Add(new DataPoint(4.7, 7.4));
		series1.Points.Add(new DataPoint(6.0, 6.2));
		series1.Points.Add(new DataPoint(8.9, 8.9));
	
		plotModel.Series.Add(series1);
	
		return plotModel;
	}


References
----------

The source code can be found in the `HelloWorld\\AndroidApp1 <https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/AndroidApp1>`_ folder in the `documentation-examples <https://github.com/oxyplot/documentation-examples>`_ repository.
