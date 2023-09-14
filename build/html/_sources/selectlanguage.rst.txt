SelectLanguage Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script that displays flag icons and Aerzen icons based on user-defined conditions. The script uses the `pic` function to position and display these icons.

Script Overview
---------------

The script consists of two main sections:

1. **Flag Icons**
   - Six flag icons are displayed using the `pic` function. Each icon is positioned at a specific `(x, y)` coordinate, and a unique `id` number is assigned to each flag icon. The position and `id` determine the flag icon's location and appearance.

2. **Aerzen Icons**
   - Different sets of Aerzen icons are displayed based on the value of the `fondo` variable. An `if` statement is used to conditionally choose which set of Aerzen icons to display. Each set of icons is positioned using the `pic` function, similar to the flag icons.

Script Explanation
------------------

Let's delve into the details of each section:

1. **Flag Icons**
   - Six flag icons are displayed at the following `(x, y)` coordinates:
     - Flag 0: `(60, 150)`
     - Flag 1: `(180, 150)`
     - Flag 2: `(300, 150)`
     - Flag 3: `(420, 150)`
     - Flag 4: `(540, 150)`
     - Flag 5: `(660, 150)`
   - Each flag is uniquely identified by its `id` number (0 to 5), allowing for individual manipulation.

2. **Aerzen Icons**
   - Different sets of Aerzen icons are displayed based on the value of the `fondo` variable. The `if` statement checks the value of `fondo` and selects the appropriate set of Aerzen icons to display.
   - Each set of Aerzen icons is positioned using the `pic` function, and specific `id` numbers are assigned to each icon within the set.
   - The Aerzen icons are displayed at `(x, y)` coordinates determined by the script's logic and the theme selected by the user.

Conclusion
----------

This documentation provides insight into a Nextion display script that displays flag icons and Aerzen icons based on user-defined conditions. The script utilizes the `pic` function to position and display these icons, making it versatile for creating dynamic and theme-customizable user interfaces.

Developers can adapt and extend this script to include additional icons, customize icon positions, and implement logic based on user preferences and themes. The provided script serves as a foundation for creating engaging Nextion display applications with dynamic iconography.

Preinitialize event SelectLanguage
----------------------------------

.. code-block:: javascript

    // Assigns the value of the `fondo` variable to the `bco` property of the `SelectLanguage` page.    
    SelectLanguage.bco=fondo

Postinitialize event SelectLanguage
------------------------------------

.. code-block:: javascript

    // The following lines of code use the pic function to display six flag icons.
    // The pic function takes three arguments: the x-coordinate of the image, the y-coordinate of the image, and the id number of the picture.
    // The x-coordinate and y-coordinate of the flag icon determine the position of the flag icon on the screen.
    // The id number determines which flag icon is displayed.
    // Flags icons
    pic 60,150,0
    pic 180,150,1
    pic 300,150,2
    pic 420,150,3
    pic 540,150,4
    pic 660,150,5
    // The following lines of code use an if statement to display different sets of Aerzen icons based on the value of the fondo variable.
    // Themes
    if(fondo==65534)
    {
      // Aerzen icons
      pic 40,360,6
      pic 130,380,7
    }else if(fondo==63391)
    {
      // Aerzen icons
      pic 40,360,8
      pic 130,380,9
    }else if(fondo==65438)
    {
      // Aerzen icons
      pic 40,360,10
      pic 130,380,11
    }else if(fondo==63421)
    {
      // Aerzen icons
      pic 40,360,12
      pic 130,380,13
    }else if(fondo==6339)
    {
      // Aerzen icons
      pic 40,360,14
      pic 130,380,15
    }else if(fondo==8484)
    {
      // Aerzen icons
      pic 40,360,16
      pic 130,380,17
    }

Touch press event m0
--------------------

.. code-block:: javascript

    // Effect to simulate a click button
    fill 60,150,100,100,fondo

Touch release event m0
----------------------

.. code-block:: javascript

    // Restores the image over the fill effect
    pic 60,150,0
    // Changes the language of the system (sys0)
    sys0=4
    // Advance to Hora page
    page Hora

Touch press event m1
--------------------

.. code-block:: javascript

    // Effect to simulate a click button
    fill 180,150,100,100,fondo

Touch release event m1
----------------------

.. code-block:: javascript

    // Restores the image over the fill effect
    pic 180,150,1
    // Changes the language of the system (sys0)
    sys0=2
    // Advance to Hora page
    page Hora

Touch press event m2
--------------------

.. code-block:: javascript

    // Effect to simulate a click button
    fill 300,150,100,100,fondo

Touch release event m2
----------------------

.. code-block:: javascript

    // Restores the image over the fill effect
    pic 300,150,2
    // Changes the language of the system (sys0)
    sys0=5
    // Advance to Hora page
    page Hora

Touch press event m3
---------------------

.. code-block:: javascript

    // Effect to simulate a click button
    fill 420,150,100,100,fondo

Touch release event m3
----------------------

.. code-block:: javascript

    // Restores the image over the fill effect
    pic 420,150,3
    // Changes the language of the system (sys0)
    sys0=1
    // Advance to Hora page
    page Hora

Touch press event m4
--------------------

.. code-block:: javascript

    // Effect to simulate a click button
    fill 540,150,100,100,fondo

Touch release event m4
-----------------------

.. code-block:: javascript

    // Restores the image over the fill effect
    pic 540,150,4
    // Changes the language of the system (sys0)
    sys0=0
    // Advance to Hora page
    page Hora

Touch press event m5
--------------------

.. code-block:: javascript

    // Effect to simulate a click button
    fill 660,150,100,100,fondo

Touch release event m5
----------------------

.. code-block:: javascript

    // Restores the image over the fill effect
    pic 660,150,5
    // Changes the language of the system (sys0)
    sys0=3
    // Advance to Hora page
    page Hora
