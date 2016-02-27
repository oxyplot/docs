=============
Export to PDF
=============

.. note:: This section is under construction. Please contribute!

You have two options when you want to export your plots to PDF. You can use the ``OxyPlot.PdfExporter`` that is included in the portable OxyPlot core library, or the ``OxyPlot.Pdf.PdfExporter`` included in the OxyPlot.Pdf library. The latter depends on `PdfSharp`_/`SilverPdf`_ and is not portable.


OxyPlot Pdf writer
------------------

- Simple PDF export is included in the OxyPlot core library
- There are limitations on text encoding, fonts and images

.. sourcecode:: csharp

    using (var stream = File.Create(fileName))
    {
        var pdfExporter = new PdfExporter { Width = 600, Height = 400 };
        pdfExporter.Export(plotModel, stream);
    }

See also the section :doc:`../extras/portable-documents` about the underlying Pdf writer.


OxyPlot.Pdf
-----------

- based on the PdfSharp_/SilverPdf_ open-source projects
- better handling of fonts and images

.. _PdfSharp: http://www.pdfsharp.net/
.. _SilverPdf: https://silverpdf.codeplex.com/
