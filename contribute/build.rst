=====
Build
=====

.. note:: This section is under construction. Please contribute!


Requirements
------------

- .NET 3.5 or later
- Build tool with support for Portable Class Libraries (Visual Studio 201x, MonoDevelop, Xamarin Studio, MsBuild)
- StyleCop (only required for builds on Windows)

The OxyPlot solutions can be opened in

- VS 2010 (with the `Portable Library Tools <http://visualstudiogallery.msdn.microsoft.com/b0e0b5e9-e138-410b-ad10-00cb3caf4981>`_ extension)
- VS 2012 (with the latest update)
- VS 2013
- VS 2013 CE
- VS 2015
- MonoDevelop
- Xamarin Studio (for GTK#, Android, iOS and OSX apps)

VS Express does not support Portable Class Libraries, and cannot be used
to build OxyPlot. But, you can use VS Express to build applications that
reference the OxyPlot assemblies!

Depending on what platform you want to build, you may need to install
extra SDKs or target framework profiles

- `.NET 3.5 <http://www.microsoft.com/en-us/download/details.aspx?id=22>`_
- `.NET 4.0 <http://www.microsoft.com/nb-no/download/details.aspx?id=17851>`_
- `.NET 4.5 <http://www.microsoft.com/nb-no/download/details.aspx?id=30653>`_
- `Portable library tools 2.0 <http://visualstudiogallery.msdn.microsoft.com/b0e0b5e9-e138-410b-ad10-00cb3caf4981/>`_
- `Microsoft .NET Portable Library Reference Assemblies 4.6 <http://www.microsoft.com/en-us/download/details.aspx?id=40727>`_
- `StyleCop <http://stylecop.codeplex.com/>`_
- `Silverlight 4 SDK <http://www.microsoft.com/en-us/download/details.aspx?id=7335>`_
- `Silverlight 5 SDK <http://www.microsoft.com/en-us/download/details.aspx?id=28359>`_
- `Windows Store App <http://msdn.microsoft.com/en-us/windows/desktop/bg162891.aspx>`_
- `GTK# <http://www.mono-project.com/docs/gui/gtksharp/>`_
- `Xwt <https://github.com/mono/xwt>`_
- `Xamarin.iOS <http://xamarin.com/ios>`_
- `Xamarin.Android <http://xamarin.com/android>`_
- `Xamarin.Mac <http://xamarin.com/mac>`_


Obtain the source code
----------------------

OxyPlot is using `Git <http://git-scm.com/>`_ distributed version
control system (DVCS). To obtain the code, it is recommended to install
one of the following Git clients

- `GitHub for Windows <https://windows.github.com/>`_
- `SourceTree <http://www.sourcetreeapp.com/|SourceTree>`_ (for Windows and Mac)
- `TortoiseGit <https://code.google.com/p/tortoisegit/>`_ (Windows shell extension)
- `Git <http://git-scm.com/>`_ (command line)

Clone the repository from ``https://github.com/oxyplot/oxyplot.git``. This can be done by the following command line:

.. sourcecode:: bat

    git clone https://github.com/oxyplot/oxyplot.git

If you don't want to use Git, you can also obtain the complete source
code as a .zip archive from the `repository page <https://github.com/oxyplot/oxyplot>`_.
Click the "Download Zip" button.


Build
-----

It should be possible to open the solution and build with Visual Studio or msbuild without any
additional steps.


Build output
------------

The build output of the *Release* configurations are placed in the
``Output/`` folder. The output of the *Debug* configurations are placed
under the ``Source/*/bin/Debug`` folders.
