Presion Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides an in-depth explanation of a Nextion display script responsible for managing touch components, navigation drawers, navigation bars, main containers, themes, text, and visual elements. The script enables touch controls and sets the visual theme based on user preferences and language selections.

Script Overview
---------------

The script comprises the following sections:

1. **Disabling Touch Components (tsw h0,0 and tsw h1,0)**
   - This section disables touch components `h0` and `h1`, preventing user interactions with these elements.

2. **Navigation Drawer**
   - This section defines the visual elements of the navigation drawer, including circles, lines, and fills, using specified colors. The navigation drawer provides a menu interface.

3. **Navigation Bar**
   - This section creates the navigation bar with circles, lines, and fills, using the specified colors. It also divides the navigation bar into individual segments for navigation.

4. **Main Containers**
   - Two main containers are defined, each consisting of circles, lines, and fills, with separate visual configurations for different sections of the application interface.

5. **Themes**
   - The script checks the selected theme (`fondo`) and applies theme-specific visual configurations, including font color, slider background color (`h0` and `h1`), values font color, and icons for turn on/off. This section allows users to customize the display's look and feel.

6. **Text**
   - The script displays navigation bar text based on the selected language (`sys0`). Language-specific text is set for each navigation bar segment and card titles within the main containers.

7. **Visual Elements**
   - Visual elements are configured to highlight the currently selected navigation tab with a line and set the visibility of various components, such as values (`value1` and `value3`), sliders (`h0` and `h1`), and text components (`t0` and `t1`).

8. **Values Background Color**
   - The background color of the values components (`value1` and `value3`) is set to match the selected theme's color.

9. **Text and Background Color**
   - The text (`t0` and `t1`) and background color are configured based on the selected theme and font color.

Script Explanation
------------------

Let's delve into the details of each section:

1. **Disabling Touch Components**
   - Touch components `h0` and `h1` are disabled (`tsw h0,0` and `tsw h1,0`) to prevent user interactions.

2. **Navigation Drawer and Navigation Bar**
   - These sections define visual elements, such as circles, lines, and fills, to create the navigation drawer and navigation bar.

3. **Main Containers**
   - Two main containers are defined with separate visual configurations. These containers may represent different sections of the application.

4. **Themes**
   - The script checks the selected theme (`fondo`) and adjusts visual elements accordingly, including font color, slider background color, and icons.

5. **Text**
   - Navigation bar text is set based on the selected language (`sys0`). Text is configured for different segments and card titles.

6. **Visual Elements**
   - A line is used to highlight the selected navigation tab. Various components are made visible or hidden based on user interactions.

7. **Values Background Color**
   - The background color of values components is set to match the selected theme.

8. **Text and Background Color**
   - Text components' text and background colors are configured based on theme and font color selections.

Conclusion
----------

This documentation provides a comprehensive understanding of a Nextion display script that manages touch components, navigation elements, themes, and text based on user preferences. Developers can adapt and extend this script to create customized and interactive Nextion display interfaces for their applications.

Please note that this script serves as an example and should be integrated into a complete Nextion display project with appropriate user interactions, logic, and additional features as needed.

Preinitialize event Presion
---------------------------

.. code-block:: javascript

    // Changes the page's background color
    Presion.bco=fondo
    // Sends the current page number over serial
    sendme

Postinitialize event Presion
----------------------------

.. code-block:: javascript

    //Disables touch components
    tsw h0,0
    tsw h1,0
    //Nav Drawer start
    cirs 30,30,20,color
    cirs 80,30,20,color
    cirs 30,450,20,color
    cirs 80,450,20,color
    line 30,10,80,10,color
    line 100,30,100,450,color
    line 30,470,80,470,color
    line 10,30,10,450,color
    fill 10,30,90,420,color
    fill 30,10,50,20,color
    fill 30,450,50,20,color
    //Nav Drawer end
    //Nav bar start
    cirs 150,40,30,color
    cirs 210,40,30,color
    line 150,10,210,10,color
    line 150,70,210,70,color
    fill 150,10,60,60,color
    //
    cirs 280,40,30,color
    cirs 340,40,30,color
    line 280,10,340,10,color
    line 280,70,340,70,color
    fill 280,10,60,60,color
    //
    cirs 410,40,30,color
    cirs 470,40,30,color
    line 410,10,470,10,color
    line 410,70,470,70,color
    fill 410,10,60,60,color
    //Nav bar end
    //Main containers start
    //First
    cirs 170,120,30,color
    cirs 730,120,30,color
    line 170,90,730,90,color
    cirs 170,240,30,color
    cirs 730,240,30,color
    line 170,270,730,270,color
    line 140,120,140,240,color
    line 760,120,760,240,color
    fill 170,90,560,180,color
    fill 140,120,30,120,color
    fill 730,120,30,120,color
    //Second
    cirs 170,320,30,color
    cirs 730,320,30,color
    line 170,290,730,290,color
    cirs 170,440,30,color
    cirs 730,440,30,color
    line 170,470,730,470,color
    line 140,320,140,440,color
    line 760,320,760,440,color
    fill 170,290,560,180,color
    fill 140,320,30,120,color
    fill 730,320,30,120,color
    //Main container end
    //Theme starts
    if(fondo==65534)
    {
      //Font color
      fontColor.val=0
      //slider bg color
      h0.bco=fondo
      h1.bco=fondo
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      //Theme 1
      pic 25,30,78
      pic 25,120,80
      //Changes the color of the turn on and turn off icons
      if(sys2==0)
      {
        pic 25,320,82
        pic 25,400,83
      }else if(sys2==1)
      {
        pic 25,320,84
        pic 25,400,85
      }
      //Nav icons
      pic 166,18,86
      pic 296,18,87
      pic 426,18,88
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //slider bg color
      h0.bco=fondo
      h1.bco=fondo
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      //Theme 2
      pic 25,30,89
      pic 25,120,91
      //Changes the color of the turn on and turn off icon
      if(sys2==0)
      {
        pic 25,320,93
        pic 25,400,94
      }else if(sys2==1)
      {
        pic 25,320,95
        pic 25,400,96
      }
      //Nav icons
      pic 166,18,97
      pic 296,18,98
      pic 426,18,99
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //slider bg color
      h0.bco=fondo
      h1.bco=fondo
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      //Theme 3
      pic 25,30,100
      pic 25,120,102
      //Changes the color of the turn on and turn off icon
      if(sys2==0)
      {
        pic 25,320,104
        pic 25,400,105
      }else if(sys2==1)
      {
        pic 25,320,106
        pic 25,400,107
      }
      //Nav icons
      pic 166,18,108
      pic 296,18,109
      pic 426,18,110
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //slider bg color
      h0.bco=fondo
      h1.bco=fondo
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      //Theme 4
      pic 25,30,111
      pic 25,120,113
      //Changes the color of the turn on and turn off icon
      if(sys2==0)
      {
        pic 25,320,115
        pic 25,400,116
      }else if(sys2==1)
      {
        pic 25,320,117
        pic 25,400,118
      }
      //Nav icons
      pic 166,18,119
      pic 296,18,120
      pic 426,18,121
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //slider bg color
      h0.bco=fontColor.val
      h1.bco=fontColor.val
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      //Theme 5
      pic 25,30,122
      pic 25,120,124
      //Changes the color of the turn on and turn off icon
      if(sys2==0)
      {
        pic 25,320,126
        pic 25,400,127
      }else if(sys2==1)
      {
        pic 25,320,128
        pic 25,400,129
      }
      //Nav icons
      pic 166,18,130
      pic 296,18,131
      pic 426,18,132
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //slider bg color
      h0.bco=fontColor.val
      h1.bco=fontColor.val
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      //Theme 6
      pic 25,30,133
      pic 25,120,135
      //Changes the color of the turn on and turn off icon
      if(sys2==0)
      {
        pic 25,320,137
        pic 25,400,138
      }else if(sys2==1)
      {
        pic 25,320,139
        pic 25,400,140
      }
      //Nav icons
      pic 166,18,141
      pic 296,18,142
      pic 426,18,143
    }
    //Theme ends
    //Text start
    if(sys0==0)
    {
      //Nav bar text Spanish
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"INICIO"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESIÓN"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
      //Cards titles
      xstr 170,100,250,35,0,fontColor.val,color,0,1,3,"Presión de aspiración"
      xstr 170,300,250,35,0,fontColor.val,color,0,1,3,"Presión final"
    }else if(sys0==1)
    {
      //Nav bar text Italian
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"INIZIO"
      xstr 275,45,70,25,2,fontColor.val,color,1,1,3,"PRESSIONE"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
      //Cards titles
      xstr 170,100,250,35,0,fontColor.val,color,0,1,3,"Pressione di aspirazione"
      xstr 170,300,250,35,0,fontColor.val,color,0,1,3,"Pressione finale"
    }else if(sys0==2)
    {
      //Nav bar text French
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"DÉBUT"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSION"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPÉRATURE"
      //Cards titles
      xstr 170,100,250,35,0,fontColor.val,color,0,1,3,"Pression d'aspiration"
      xstr 170,300,250,35,0,fontColor.val,color,0,1,3,"Pression ultime"
    }else if(sys0==3)
    {
      //Nav bar text English
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"HOME"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSURE"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURE"
      //Cards titles
      xstr 170,100,250,35,0,fontColor.val,color,0,1,3,"Suction pressure"
      xstr 170,300,250,35,0,fontColor.val,color,0,1,3,"Final pressure"
    }else if(sys0==4)
    {
      //Nav bar text German
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"ANFANG"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"DRUCK"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATUR"
      //Cards titles
      xstr 170,100,250,35,0,fontColor.val,color,0,1,3,"Saugdruck"
      xstr 170,300,250,35,0,fontColor.val,color,0,1,3,"Enddruck"
    }else if(sys0==5)
    {
      //Nav bar text Portuguese
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"COMEÇO"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSÃO"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
      //Cards titles
      xstr 170,100,250,35,0,fontColor.val,color,0,1,3,"Pressão de sucção"
      xstr 170,300,250,35,0,fontColor.val,color,0,1,3,"Pressão final"
    }
    //Text end
    //Line to show tab selected
    line 270,65,350,65,fontColor.val
    vis value1,1
    vis value3,1
    vis h0,1
    vis h1,1
    //Values bg color
    value1.bco=color
    value3.bco=color
    //
    t0.bco=color
    t1.bco=color
    t0.pco=fontColor.val
    t1.pco=fontColor.val

Touch press event m0
--------------------

.. code-block:: javascript

    //Nav bar start
    cirs 150,40,30,fondo
    cirs 210,40,30,fondo
    line 150,10,210,10,fondo
    line 150,70,210,70,fondo
    fill 150,10,60,60,fondo

Touch release event m0
----------------------

.. code-block:: javascript

    //Nav bar start
    cirs 150,40,30,color
    cirs 210,40,30,color
    line 150,10,210,10,color
    line 150,70,210,70,color
    fill 150,10,60,60,color
    //Restores the icons according the theme selected
    if(fondo==65534)
    {
      pic 166,18,86
    }else if(fondo==63391)
    {
      pic 166,18,97
    }else if(fondo==65438)
    {
      pic 166,18,108
    }else if(fondo==63421)
    {
      pic 166,18,119
    }else if(fondo==6339)
    {
      pic 166,18,130
    }else if(fondo==8484)
    {
      pic 166,18,141
    }
    //
    if(sys0==0)
    {
      //Spanish
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"INICIO"
    }else if(sys0==1)
    {
      //Italian
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"INIZIO"
    }else if(sys0==2)
    {
      //French
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"DÉBUT"
    }else if(sys0==3)
    {
      //English
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"HOME"
    }else if(sys0==4)
    {
      //German
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"ANFANG"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"COMEÇO"
    }
    //Line to show tab selected
    line 152,65,212,65,fontColor.val
    //
    page Home

Touch press event m1
--------------------

.. code-block:: javascript

    //
    cirs 280,40,30,fondo
    cirs 340,40,30,fondo
    line 280,10,340,10,fondo
    line 280,70,340,70,fondo
    fill 280,10,60,60,fondo

Touch release event m1
----------------------

.. code-block:: javascript

    //
    cirs 280,40,30,color
    cirs 340,40,30,color
    line 280,10,340,10,color
    line 280,70,340,70,color
    fill 280,10,60,60,color
    //Restores the icons according the theme selected
    if(fondo==65534)
    {
      pic 296,18,87
    }else if(fondo==63391)
    {
      pic 296,18,98
    }else if(fondo==65438)
    {
      pic 296,18,109
    }else if(fondo==63421)
    {
      pic 296,18,120
    }else if(fondo==6339)
    {
      pic 296,18,131
    }else if(fondo==8484)
    {
      pic 296,18,142
    }
    //
    if(sys0==0)
    {
      //Spanish
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESIÓN"
    }else if(sys0==1)
    {
      //Italian
      xstr 275,45,70,25,2,fontColor.val,color,1,1,3,"PRESSIONE"
    }else if(sys0==2)
    {
      //French
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSION"
    }else if(sys0==3)
    {
      //English
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSURE"
    }else if(sys0==4)
    {
      //German
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"DRUCK"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSÃO"
    }

Touch press event m2
--------------------

.. code-block:: javascript

    //
    cirs 470,40,30,fondo
    cirs 410,40,30,fondo
    line 410,10,470,10,fondo
    line 410,70,470,70,fondo
    fill 410,10,60,60,fondo

Touch release event m2
----------------------

.. code-block:: javascript

    //
    cirs 410,40,30,color
    cirs 470,40,30,color
    line 410,10,470,10,color
    line 410,70,470,70,color
    fill 410,10,60,60,color
    //Restores the icons according the theme selected
    if(fondo==65534)
    {
      pic 426,18,88
    }else if(fondo==63391)
    {
      pic 426,18,99
    }else if(fondo==65438)
    {
      pic 426,18,110
    }else if(fondo==63421)
    {
      pic 426,18,121
    }else if(fondo==6339)
    {
      pic 426,18,132
    }else if(fondo==8484)
    {
      pic 426,18,143
    }
    //
    if(sys0==0)
    {
      //Spanish
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
    }else if(sys0==1)
    {
      //Italian
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
    }else if(sys0==2)
    {
      //French
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPÉRATURE"
    }else if(sys0==3)
    {
      //English
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURE"
    }else if(sys0==4)
    {
      //German
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATUR"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
    }
    //
    page Temperatura

Touch press event bInfoP
------------------------

.. code-block:: javascript

    //changes the images according the theme selected
    if(fondo==65534)
    {
      pic 25,30,79
    }else if(fondo==63391)
    {
      pic 25,30,90
    }else if(fondo==65438)
    {
      pic 25,30,101
    }else if(fondo==63421)
    {
      pic 25,30,112
    }else if(fondo==6339)
    {
      pic 25,30,123
    }else if(fondo==8484)
    {
      pic 25,30,134
    }
    //
    if(sys1==1||sys1==2)
    {
      //page Mensajes
    }else
    {
      Info.returnPage.val=dp
      page Info
    }

Touch release event bInfoP
--------------------------

.. code-block:: javascript

    //restores the images according the theme selected
    if(fondo==65534)
    {
      pic 25,30,78
    }else if(fondo==63391)
    {
      pic 25,30,89
    }else if(fondo==65438)
    {
      pic 25,30,100
    }else if(fondo==63421)
    {
      pic 25,30,111
    }else if(fondo==6339)
    {
      pic 25,30,122
    }else if(fondo==8484)
    {
      pic 25,30,133
    }

Touch press event bHomeP
------------------------

.. code-block:: javascript

    //Changes the image when pressed according the theme selected
    if(fondo==65534)
    {
      pic 25,120,81
    }else if(fondo==63391)
    {
      pic 25,120,92
    }else if(fondo==65438)
    {
      pic 25,120,103
    }else if(fondo==63421)
    {
      pic 25,120,114
    }else if(fondo==6339)
    {
      pic 25,120,125
    }else if(fondo==8484)
    {
      pic 25,120,136
    }

Touch release event bHomeP
--------------------------

.. code-block:: javascript

    //Restores the image when pressed according the theme selected
    if(fondo==65534)
    {
      pic 25,120,80
    }else if(fondo==63391)
    {
      pic 25,120,91
    }else if(fondo==65438)
    {
      pic 25,120,102
    }else if(fondo==63421)
    {
      pic 25,120,113
    }else if(fondo==6339)
    {
      pic 25,120,124
    }else if(fondo==8484)
    {
      pic 25,120,135
    }
    //
    page Menu

Touch press event bStartP
-------------------------

.. code-block:: javascript

    //Only activates if the status is inactive
    if(sys2==0)
    {
      //Start high
      sys2=1
      //prints "Start",0
      //Changes the color of the turn on icon
      if(fondo==65534)
      {
        pic 25,320,84
      }else if(fondo==63391)
      {
        pic 25,320,95
      }else if(fondo==65438)
      {
        pic 25,320,106
      }else if(fondo==63421)
      {
        pic 25,320,117
      }else if(fondo==6339)
      {
        pic 25,320,128
      }else if(fondo==8484)
      {
        pic 25,320,139
      }
      //Changes the color of the turn off icon
      if(fondo==65534)
      {
        pic 25,400,85
      }else if(fondo==63391)
      {
        pic 25,400,96
      }else if(fondo==65438)
      {
        pic 25,400,107
      }else if(fondo==63421)
      {
        pic 25,400,118
      }else if(fondo==6339)
      {
        pic 25,400,129
      }else if(fondo==8484)
      {
        pic 25,400,140
      }
    }

Touch press event bStopP
------------------------

.. code-block:: javascript

    //Only deactivates if the status is active
    if(sys2==1)
    {
      //Start Low
      sys2=0
      //prints "Stop",0
      //Changes the color of the turn on icon
      if(fondo==65534)
      {
        pic 25,320,82
      }else if(fondo==63391)
      {
        pic 25,320,93
      }else if(fondo==65438)
      {
        pic 25,320,104
      }else if(fondo==63421)
      {
        pic 25,320,115
      }else if(fondo==6339)
      {
        pic 25,320,126
      }else if(fondo==8484)
      {
        pic 25,320,137
      }
      //Changes the color of the turn off icon
      if(fondo==65534)
      {
        pic 25,400,83
      }else if(fondo==63391)
      {
        pic 25,400,94
      }else if(fondo==65438)
      {
        pic 25,400,105
      }else if(fondo==63421)
      {
        pic 25,400,116
      }else if(fondo==6339)
      {
        pic 25,400,127
      }else if(fondo==8484)
      {
        pic 25,400,138
      }
    }
