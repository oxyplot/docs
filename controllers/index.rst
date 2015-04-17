==========
Controller
==========

.. note:: This section is under construction. Please contribute!

PlotController
--------------

Explain...


Default input bindings
----------------------

The default input bindings in the `PlotController` are:

================= ===========================================
Action            Gesture                         
================= ===========================================
Pan\*             Right mouse button              
Zoom\*            Mouse wheel                     
Zoom by rectangle Ctrl+Right mouse button         
Reset\*           Right mouse button double-click 
Show 'tracker'    Left mouse button               
Reset axes        'A'                             
Copy bitmap       Ctrl+C                          
Copy code         Ctrl+Alt+C                      
Copy properties   Ctrl+Alt+R                      
================= ===========================================

You can zoom/pan/reset a single axis by positioning the mouse cursor over the axis before starting the zoom/pan.

Customizing the bindings
------------------------

Create a new PlotController:

.. code:: csharp

    var myController = new PlotController();

Set the controller in the `PlotView` control

.. code:: csharp

    plotView.Controller = myController;

Bind an input gesture to a command

.. code:: csharp

    myController.BindMouseDown(OxyMouseButton.Left, PlotCommands.Pan);

Unbind an input gesture

.. code:: csharp
    
    myController.UnbindMouseDown(OxyMouseButton.Right);

Unbind all commands

.. code:: csharp
    
    myController.UnbindAll();

- Creating new commands
- Creating new manipulators
