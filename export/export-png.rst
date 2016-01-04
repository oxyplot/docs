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
        var pngExporter = new PngExporter();
        pngExporter.Export(plotModel, stream, 600, 400, Brushes.White);
        
        var bitmap = new BitmapImage();
        bitmap.BeginInit();
        bitmap.StreamSource = stream;
        bitmap.CacheOption = BitmapCacheOption.OnLoad;
        bitmap.EndInit();
        bitmap.Freeze();
            
        Clipboard.SetImage(bitmap);
    }
