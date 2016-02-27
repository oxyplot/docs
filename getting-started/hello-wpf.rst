===
WPF
===

.. note:: This section is under construction. Please contribute!


This example shows how to create a WPF application with a ``PlotView`` control, where the content of the plot is defined in code as a ``PlotModel``. If you want to define the content of the plot in XAML, see :doc:`hello-wpf-xaml`.


Create project
--------------

Start Visual Studio and select "FILE -> New -> Project..." to create a new WPF application:

.. image:: wpf-new-project.png


Add references
--------------

You need references to the OxyPlot and OxyPlot.Wpf assemblies. The easiest way to add these is to right click on the "References" item in the Solution Explorer and select "Manage NuGet Packages..." (this requires that the "NuGet Package Manager" extension is installed):

.. image:: wpf-add-reference.png

In the "Manage NuGet packages" dialog, search for "OxyPlot" and select the "OxyPlot.Wpf" package:

.. image:: wpf-install-package.png

You can also use the `Package Manager Console <http://docs.nuget.org/docs/start-here/using-the-package-manager-console>`_ to install the package:

.. sourcecode:: bat

    PM> Install-Package OxyPlot.Wpf -Pre


Create a view model
-------------------

Add a class that creates a ``PlotModel`` with a ``FunctionSeries``.

.. sourcecode:: csharp

    namespace WpfApplication1
    {
        using System;
    
        using OxyPlot;
        using OxyPlot.Series;
    
        public class MainViewModel
        {
            public MainViewModel()
            {
                this.MyModel = new PlotModel { Title = "Example 1" };
                this.MyModel.Series.Add(new FunctionSeries(Math.Cos, 0, 10, 0.1, "cos(x)"));
            }
    
            public PlotModel MyModel { get; private set; }
        }
    }

Create the view
---------------

Define the namespace in the ``Window`` element, set the ``DataContext`` and add a ``PlotView`` control:

.. sourcecode:: xml

    <Window x:Class="WpfApplication1.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:oxy="http://oxyplot.org/wpf"
            xmlns:local="clr-namespace:WpfApplication1"
            Title="Example 1 (WPF)" Height="350" Width="525">
        <Window.DataContext>
            <local:MainViewModel/>
        </Window.DataContext>
        <Grid>
            <oxy:PlotView Model="{Binding MyModel}"/>
        </Grid>
    </Window>

The application should now look like this:

.. image:: wpf-example1.png

The source code can be found in the `HelloWorld\\WpfApplication1 <https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/WpfApplication1>`_ folder in the `documentation-examples <https://github.com/oxyplot/documentation-examples>`_ repository.