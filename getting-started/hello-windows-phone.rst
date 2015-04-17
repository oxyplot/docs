=========================
Windows Phone Silverlight
=========================

.. note:: This section is under construction. Please contribute!


This example shows how to create a Windows Phone Silverlight app.


Create project
--------------

Start Visual Studio and select "FILE -> New -> Project...". Select "Store Apps -> Windows Phone Apps -> Blank App (Windows Phone Silverlight)" to 
create a new projects for Windows Phone Silverlight.


Add references
--------------

You need references to the `OxyPlot` and `OxyPlot.WP8` assemblies. The easiest way to do this is to right click on the "References" item in the Solution Explorer and select "Manage NuGet Packages..." (this requires that the "NuGet Package Manager" extension is installed).

In the "Manage NuGet packages" dialog, search for "oxyplot windows phone" in the top-right search textbox. 
Select the "OxyPlot for Windows Phone Silverlight apps" package and click install.

You can also use the `Package Manager Console <http://docs.nuget.org/docs/start-here/using-the-package-manager-console>`_ to install the package:

.. sourcecode:: bat

    PM> Install-Package OxyPlot.WP8


Create a view model
-------------------

Add a class that creates a ``PlotModel`` and a ``FunctionSeries``.

.. sourcecode:: csharp

    namespace WinPhoneApp1
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

Define the namespace in the ``PhoneApplicationPage`` element, set the ``DataContext`` and add a ``PlotView`` control:

.. sourcecode:: xml

    <phone:PhoneApplicationPage
        x:Class="WinPhoneApp1.MainPage"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:phone="clr-namespace:Microsoft.Phone.Controls;assembly=Microsoft.Phone"
        xmlns:shell="clr-namespace:Microsoft.Phone.Shell;assembly=Microsoft.Phone"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:oxy="clr-namespace:OxyPlot.WP8;assembly=OxyPlot.WP8"
        xmlns:local="clr-namespace:WinPhoneApp1"
        mc:Ignorable="d"
        FontFamily="{StaticResource PhoneFontFamilyNormal}"
        FontSize="{StaticResource PhoneFontSizeNormal}"
        Foreground="{StaticResource PhoneForegroundBrush}"
        SupportedOrientations="Landscape" Orientation="Landscape"
        shell:SystemTray.IsVisible="True">
        <phone:PhoneApplicationPage.DataContext>
            <local:MainViewModel/>
        </phone:PhoneApplicationPage.DataContext>

        <Grid x:Name="ContentPanel" Margin="12,0,12,0">
            <oxy:PlotView Model="{Binding MyModel}"/>
        </Grid>

    </phone:PhoneApplicationPage>

The application should now look like this (on the Windows Phone emulator):

.. image:: windows-phone-silverlight-app-example1.png

The source code can be found in the `HelloWorld\\WinPhoneApp1 <https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/WinPhoneApp1>`_ folder in the `documentation-examples <https://github.com/oxyplot/documentation-examples>`_ repository.
