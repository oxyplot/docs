=============
Export to PNG
=============

.. note:: This section is under construction. Please contribute!

The PNG exporters are implemented in the platform specific libraries (OxyPlot.Wpf, OxyPlot.WindowsForms etc.).


Write a PNG file
----------------

.. code:: csharp

    using (var stream = File.Create(fileName))
    {
        var pngExporter = new PngExporter();
        pngExporter.Export(plotModel, stream, 600, 400, Brushes.White);
    }


Copy to clipboard
-----------------

.. code:: csharp

    using (var stream = new MemoryStream())
    {
        var bitmap = OxyPlot.Wpf.PngExporter.ExportToBitmap(
					Model, (int)Model.Width, (int)Model.Height, OxyColors.White);
		Clipboard.SetImage(bitmap);
    }
