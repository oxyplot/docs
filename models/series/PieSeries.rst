=========
PieSeries
=========

.. note:: This section is under construction. Please contribute!

A ``PieSeries`` renders a pie chart. Only one pie series is supported per ``PlotModel``.

.. image:: PieSeries.png


Tracker
-------

The format string may use the following arguments:

- ``{0}`` the title of the series
- ``{1}`` the label of the pie slice
- ``{2}`` the value of the pie slice
- ``{3}`` the percentage of the pie slice
- ``{PropertyX}`` the value of ``PropertyX`` in the item (extended format string syntax)

To show the values with one digit, use the format string ``"{2:0.0}"``.

The default format string for ``PieSeries`` is ``"{1}: {2:0.###} ({3:P1})"``


Example
-------

.. sourcecode:: csharp

    namespace ExampleLibrary
    {
        using OxyPlot;
    
        using OxyPlot.Series;
    
        [Examples("PieSeries")]
        public static class PieSeriesExamples
        {
            [Example("PieSeries")]
            public static PlotModel PieSeries()
            {
                return CreateExample();
            }
    
            [Example("PieSeries with inside label color")]
            public static PlotModel InsideLabelColor()
            {
                var model = CreateExample();
                var series = (PieSeries)model.Series[0];
                series.InsideLabelColor = OxyColors.White;
                return model;
            }
    
            private static PlotModel CreateExample()
            {
                var model = new PlotModel { Title = "World population by continent" };
    
                var ps = new PieSeries
                {
                    StrokeThickness = 2.0,
                    InsideLabelPosition = 0.8,
                    AngleSpan = 360,
                    StartAngle = 0
                };
    
                // http://www.nationsonline.org/oneworld/world_population.htm
                // http://en.wikipedia.org/wiki/Continent
                ps.Slices.Add(new PieSlice("Africa", 1030) { IsExploded = true });
                ps.Slices.Add(new PieSlice("Americas", 929) { IsExploded = true });
                ps.Slices.Add(new PieSlice("Asia", 4157));
                ps.Slices.Add(new PieSlice("Europe", 739) { IsExploded = true });
                ps.Slices.Add(new PieSlice("Oceania", 35) { IsExploded = true });
                
                model.Series.Add(ps);
                return model;
            }
        }
    }    


.. sourcecode:  VB

    Create class in a file called PieViewModel.vb

    Imports OxyPlot
    Imports OxyPlot.Series
    
    Public Class PieViewModel
    
        Private modelP1 As PlotModel
        Private modelP2 As PlotModel
        Private modelP3 As PlotModel
        
        Public Sub New()
    
            modelP1 = New PlotModel() With {.Title = "Pie Sample1", .Subtitle = "created with OxyPlot"}
    
            Dim seriesP1 = New PieSeries() With {.StrokeThickness = 2.0, .InsideLabelPosition = 0.8, .AngleSpan = 360, .StartAngle = 0}
    
            'http://www.nationsonline.org/oneworld/world_population.htm
            'http://en.wikipedia.org/wiki/Continent
            
            seriesP1.Slices.Add(New PieSlice("Africa", 1030) With {.IsExploded = False, .Fill = OxyColors.PaleVioletRed})
            seriesP1.Slices.Add(New PieSlice("Americas", 929) With {.IsExploded = True})
            seriesP1.Slices.Add(New PieSlice("Asia", 4157) With {.IsExploded = True})
            seriesP1.Slices.Add(New PieSlice("Europe", 739) With {.IsExploded = True})
            seriesP1.Slices.Add(New PieSlice("Oceania", 35) With {.IsExploded = True})
    
            modelP1.Series.Add(seriesP1)
    
        End Sub
        
        Property Model1() As PlotModel
            Get
                Return modelP1
            End Get
            Set(value As PlotModel)
                modelP1 = value
            End Set
        End Property
    
    End Class
    
    Add the following to the XAML file:
    
    <Window.DataContext>
        <local:PieViewModel/>
    </Window.DataContext>
    <Grid>
        <oxy:PlotView Model="{Binding Model1}"/>
    </Grid>
