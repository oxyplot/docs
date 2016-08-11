=============
Export to PNG
=============

The PNG export functionality is located in the platform specific libraries (OxyPlot.Wpf, OxyPlot.WindowsForms).
Note that PNG export is not yet supported on all platforms.

Write to a stream
-----------------

.. code:: csharp

    var stream = new MemoryStream();
    var pngExporter = new PngExporter { Width = 600, Height = 400, Background = OxyColors.White };
    pngExporter.Export(plotModel, stream);


Write to a file
---------------

.. code:: csharp

    var pngExporter = new PngExporter { Width = 600, Height = 400, Background = OxyColors.White };
    pngExporter.ExportToFile(plotModel, fileName);


Copy to the clipboard
---------------------

*Warning: Calling the ExportToBitmap method often in a very short period may result in high memory usage.*

.. code:: csharp

    var pngExporter = new PngExporter { Width = 600, Height = 400, Background = OxyColors.White };
    var bitmap = pngExporter.ExportToBitmap(plotModel);
    Clipboard.SetImage(bitmap);
