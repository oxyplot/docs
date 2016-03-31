=============
HeatMapSeries
=============

.. note:: This section is under construction. Please contribute!

A ``HeatMapSeries`` shows a 2D array of values as a heat map.

Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the title of the x-axis
- ``{2}`` the x-value
- ``{3}`` the title of the y-axis
- ``{4}`` the y-value
- ``{5}`` the title of the value/color-axis
- ``{6}`` the color-value
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the x and y values with one digit, use the format string ``"{2:0.0},{4:0.0}"``.

The default format string for ``HeatMapSeries`` is ``"{0}\n{1}: {2}\n{3}: {4}\n{5}: {6}"``


Example (Linear, Bitmap)
-------

.. image:: HeatMapSeries_linear.png

.. sourcecode:: csharp

    using OxyPlot;
    using OxyPlot.Axes;
    using OxyPlot.Series;
    
	namespace ExampleLibrary
	{
        
		public class LinearHeatMapViewModel
		{
			private PlotModel modelP1;
			public LinearHeatMapViewModel()
			{
				modelP1 = new PlotModel { Title = "Heatmap" };

				//top axis
				modelP1.Axes.Add(new LinearColorAxis
				{
					Palette = OxyPalettes.Rainbow(100)
				});

				//generate 1d normal distribution
				var singleData = new double[100];
				for(int x = 0; x < 100; ++x)
					singleData[x] = Math.Exp((-1.0 / 2.0) * Math.Pow(((double)x - 50.0) / 20.0, 2.0));
				//generate 2d normal distribution
				var data = new double[100, 100];
				for(int x = 0; x < 100; ++x)
					for(int y = 0; y < 100; ++y)
						data[y, x] = singleData[x] * singleData[(y + 30) % 100] * 100;

				var heatMapSeries = new HeatMapSeries
				{
					X0 = 0,
					X1 = 99,
					Y0 = 0,
					Y1 = 99,
					Interpolate = true,
					RenderMethod = HeatMapRenderMethod.Bitmap,
					Data = data
				};

				modelP1.Series.Add(heatMapSeries);
                
			}
            
			public PlotModel Model1
			{
				get { return modelP1; }
				set { modelP1 = value; }
			}
		}
	}
    
Example (Categorized, Rectangle)
-------

The following diagram has categories on both, the x-axis and the y-axis.

It visualizes the amount of cake (y-axis) consumed on the specific day of week (x-axis). As can be seen in the diagram, the amount of cake rises from Monday to Sunday.

.. image:: HeatMapSeries_categorized.png

.. sourcecode:: csharp

    using OxyPlot;
    using OxyPlot.Axes;
    using OxyPlot.Series;
    
	namespace ExampleLibrary
	{
        
		public class LinearHeatMapViewModel
		{
			private PlotModel modelP1;
			public LinearHeatMapViewModel()
			{
				modelP1 = new PlotModel { Title = "Cakes per Weekday" };

				//WeekDay-Axis (Bottom)
				modelP1.Axes.Add(new CategoryAxis
				{
					Position = AxisPosition.Bottom,
					//Key used for specifying this axis in the HeatMapSeries
					Key = "WeekDayAxis",
					//Property of the items in ItemSource that should be used as title
					LabelField = "Title",
					//Array of Categories (see above), mapped to one of the coordinates of the 2D-data array
					ItemsSource = new Category[]
					{
						new Category{ Title = "Monday" },
						new Category{ Title = "Tuesday" },
						new Category{ Title = "Wednesday" },
						new Category{ Title = "Thursday" },
						new Category{ Title = "Friday" },
						new Category{ Title = "Saturday" },
						new Category{ Title = "Sunday" }
					}
				});
				//CakeType-Axis (Left)
				modelP1.Axes.Add(new CategoryAxis
				{
					Position = AxisPosition.Left,
					Key = "CakeAxis",
					LabelField = "Title",
					ItemsSource = new Category[]
					{
						new Category{ Title = "Apple cake" },
						new Category{ Title = "Baumkuchen" },
						new Category{ Title = "Bundt cake" },
						new Category{ Title = "Chocolate cake" },
						new Category{ Title = "Carrot cake" }
					}
				});
				//color axis
				modelP1.Axes.Add(new LinearColorAxis
				{
					Palette = OxyPalettes.Hot(200)
				});

				var rand = new Random();
				var data = new double[7, 5];
				for(int x = 0; x < 5; ++x)
					for(int y = 0; y < 7; ++y)
						data[y, x] = rand.Next(0, 200) * (0.13 * (y + 1));

				var heatMapSeries = new HeatMapSeries
				{
					X0 = 0,
					X1 = 6,
					Y0 = 0,
					Y1 = 4,
					XAxisKey = "WeekDayAxis",
					YAxisKey = "CakeAxis",
					RenderMethod = HeatMapRenderMethod.Rectangles,
					LabelFontSize = 0.2, //neccessary to display the label
					Data = data
				};

				modelP1.Series.Add(heatMapSeries);
                
			}
            
			public PlotModel Model1
			{
				get { return modelP1; }
				set { modelP1 = value; }
			}
		}
	}
