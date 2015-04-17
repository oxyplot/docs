===========
Silverlight
===========

.. note:: This section is under construction. Please contribute!


This example shows how to create a Silverlight application where the content of the plot is defined in code.

Create project
--------------

Start Visual Studio and select "FILE -> New -> Project..." to create a new Silverlight application:

.. image:: silverlight-new-project.png

Add references
--------------

You need references to the OxyPlot and OxyPlot.Silverlight assemblies. The easiest way to do this is to right click on the "References" item in the Solution Explorer and select "Manage NuGet Packages..." (this requires that the "NuGet Package Manager" extension is installed):

.. image:: silverlight-add-reference.png

In the "Manage NuGet packages" dialog, search for "OxyPlot" in the top-right search textbox. 
Select the "OxyPlot.Silverlight" package and click install:

.. image:: silverlight-install-package.png

You can also use the [Package Manager Console](http://docs.nuget.org/docs/start-here/using-the-package-manager-console) to install the package:

.. sourcecode:: bat

    PM> Install-Package OxyPlot.Silverlight

Create a view model
-------------------

Add a class that creates a ``PlotModel`` and a ``FunctionSeries``.

.. sourcecode:: csharp

    namespace SilverlightApplication1
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

            public PlotModel MyModel { get; set; }
        }
    }

Create the view
---------------

Define the namespace in the ``Window`` element, set the ``DataContext`` and add a ``PlotView`` control:

.. sourcecode:: xml

    <UserControl x:Class="SilverlightApplication1.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
                 xmlns:oxy="clr-namespace:OxyPlot.Silverlight;assembly=OxyPlot.Silverlight"
                 xmlns:local="clr-namespace:SilverlightApplication1"
                 mc:Ignorable="d"
        d:DesignHeight="300" d:DesignWidth="400">
        <UserControl.DataContext>
            <local:MainViewModel/>
        </UserControl.DataContext>

        <Grid x:Name="LayoutRoot" Background="White">
            <oxy:PlotView Model="{Binding MyModel}"/>
        </Grid>
    </UserControl>

The application should now look like this:

.. image: silverlight-example1.png

The source code can be found in the `HelloWorld\\SilverlightApplication1 <https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/SilverlightApplication1>`_ folder in the `documentation-examples <https://github.com/oxyplot/documentation-examples>`_ repository.