=============
Xamarin.Forms
=============

.. note:: This section is under construction. Please contribute!


This example shows how to create a `Xamarin.Forms <http://xamarin.com/forms>`_ app where both the user interface and the plot is defined in portable code.

Create the project
------------------

Start Visual Studio and select the blank Xamarin.Forms app template.

Update and add references
-------------------------

Update the ``Xamarin.Forms`` NuGet packages to the latest version.

Add the ``OxyPlot.Xamarin.Forms`` NuGet package in both the portable and platform specific projects. Tip: Use the "Manage NuGet packages for solution..." command when you install the package to a lot of projects.

Initialize renderers
--------------------

You need to initialize the OxyPlot renderers by adding the following call just after ``Xamarin.Forms.Forms.Init()``:

- iOS (Unified API): ``OxyPlot.Xamarin.Forms.Platform.iOS.PlotViewRenderer.Init();``
- Android: ``OxyPlot.Xamarin.Forms.Platform.Android.PlotViewRenderer.Init();``
- Universal Windows: ``OxyPlot.Xamarin.Forms.Platform.UWP.PlotViewRenderer.Init();``
- Windows Phone: ``OxyPlot.Xamarin.Forms.Platform.WP8.PlotViewRenderer.Init();``

Tip: Search for "Xamarin.Forms.Forms.Init()" in your solution to find all the places you need to add code.

Add the PlotView to a page (in code)
------------------------------------

In the portable/shared app project, add the plot view to a page:

.. sourcecode:: csharp

    public App()
    {
        this.MainPage = new ContentPage
        {
            Content = new PlotView
            {
                Model = new PlotModel { Title = "Hello, Forms!" },
                VerticalOptions = LayoutOptions.Fill,
                HorizontalOptions = LayoutOptions.Fill,
            },
        };
    }

Note that the `VerticalOptions` and `HorizontalOptions` properties must be set, otherwise the plot view will have `0` width and height.

Add the PlotView to a page (XAML)
---------------------------------

Add a "Forms Xaml Page" to your project. In the page element, add a namespace declaration:

.. sourcecode:: xml

    xmlns:oxy="clr-namespace:OxyPlot.Xamarin.Forms;assembly=OxyPlot.Xamarin.Forms"

Then add the plot view:

.. sourcecode:: xml

    <oxy:PlotView Model="{Binding Model}" VerticalOptions="Center" HorizontalOptions="Center" />

This view will now be bound to a ``PlotModel`` in the binding context of the page.

References
----------

The source code can be found in the `HelloWorld\XamarinFormsApp1 <https://github.com/oxyplot/documentation-examples/tree/master/HelloWorld/XamarinFormsApp1>`_ folder in the `documentation-examples <https://github.com/oxyplot/documentation-examples>`_ repository.
