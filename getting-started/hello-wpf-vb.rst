============
WPF (VB.NET)
============

.. note:: This section is under construction. Please contribute!


This example shows how to create a WPF application in VB.NET where the content of the plot is defined in code.

Create a new VB.NET Windows/WPF project and add a reference to the OxyPlot.Wpf NuGet package. Then create a view model class:

.. sourcecode:: vb.net

    Imports OxyPlot
    Imports OxyPlot.Series

    Public Class MainViewModel

        Private mmodel As PlotModel

        Public Sub New()

            Model = New PlotModel()

            Model.Title = "Simple example"
            Model.Subtitle = "using OxyPlot in VB.NET"

            Dim series1 = New LineSeries()
            series1.Title="Series 1"
            series1.MarkerType = MarkerType.Circle
            series1.Points.Add(New DataPoint(0, 0))
            series1.Points.Add(New DataPoint(10, 18))
            series1.Points.Add(New DataPoint(20, 12))
            series1.Points.Add(New DataPoint(30, 8))
            series1.Points.Add(New DataPoint(40, 15))

            Dim series2 = New LineSeries()
            series2.Title="Series 2"
            series2.MarkerType = MarkerType.Square
            series2.Points.Add(New DataPoint(0, 4))
            series2.Points.Add(New DataPoint(10, 12))
            series2.Points.Add(New DataPoint(20, 16))
            series2.Points.Add(New DataPoint(30, 25))
            series2.Points.Add(New DataPoint(40, 5))

            Model.Series.Add(series1)
            Model.Series.Add(series2)

        End Sub

        Property Model() As PlotModel
            Get
                Return mmodel
            End Get
            Set(value As PlotModel)
                mmodel = value
            End Set
        End Property

    End Class


and edit the main window XAML:

.. sourcecode:: xml

    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:oxy="http://oxyplot.org/wpf"
        xmlns:local="clr-namespace:SimleDemoVB"
        Title="OxyPlot in VB.NET" Height="480" Width="640" Icon="OxyPlot.ico">
        <Window.DataContext>
            <local:MainViewModel/>
        </Window.DataContext>
        <Grid>
            <oxy:PlotView Model="{Binding Model}"/>
        </Grid>
    </Window>

The source code can be found in the `Source\\Examples\\WPF\\SimpleDemoVB <https://github.com/oxyplot/oxyplot/tree/master/Source/Examples/WPF/SimleDemoVB>`_ folder in the `oxyplot <https://github.com/oxyplot/oxyplot>`_ repository.