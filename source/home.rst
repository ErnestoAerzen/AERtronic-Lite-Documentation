Fecha Nextion Page
============================

Description
-----------

Overview:
---------

Touch Component Disabling:
~~~~~~~~~~~~~~~~~~~~~~~~~~
This script defines a customizable graphical user interface (GUI) layout for an embedded system. It employs various graphical elements, conditional logic, and theming options to create an interactive and visually appealing interface for users. The GUI is designed to display information related to pressure and temperature parameters, with support for multiple languages and theme selections.

Key Features:
-------------

Navigation Drawer:
~~~~~~~~~~~~~~~~~~
A navigation drawer is implemented, featuring four circular icons and horizontal and vertical lines. It employs filled rectangles to create an aesthetically pleasing drawer appearance.

Multiple Cards:
~~~~~~~~~~~~~~~
The GUI layout includes four cards, each consisting of circular icons and lines. These cards serve as containers for displaying information or controls related to various system parameters.

Navigation Bar:
~~~~~~~~~~~~~~~
A navigation bar is provided, with circular icons serving as buttons, separated by horizontal lines. The navigation bar facilitates easy navigation within the GUI.

Theme Selection:
~~~~~~~~~~~~~~~~
The script offers theme selection based on the value of the `fondo` variable. Different themes involve configuring image IDs, font colors, and icons, allowing users to personalize the GUI's look and feel.

Multilingual Support:
~~~~~~~~~~~~~~~~~~~~~
Text labels are used throughout the GUI, including navigation bar labels and card titles. The displayed text content is determined by the `sys0` variable, providing support for multiple languages.

Visibility and Color Customization:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
The script allows users to configure the visibility and background colors of various GUI elements, including text values and sliders. This customization ensures that the GUI matches the desired visual style.

Tab Indicator:
~~~~~~~~~~~~~~
A line is drawn on the navigation bar to indicate the currently selected tab, enhancing the user experience by highlighting the active section.

Usage:
------

Customizable GUI for Embedded Systems:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
This script serves as a template for creating a flexible and visually appealing GUI for embedded systems. It is highly customizable, enabling developers to tailor the interface to their specific requirements, including language preferences and design aesthetics.

Note: To fully implement and use this script, developers should ensure compatibility with the target embedded system's hardware and any software dependencies.

Preinitialize event Home
------------------------

.. code-block:: javascript

    // Change the backgrounf color of the page
    Home.bco=fondo
    // Sends the id of the page over serial in order to the MCU to handle the data
    sendme

Postinitializa event Home
-------------------------

.. code-block:: javascript

    //Disables touch components
    tsw h0,0
    tsw h1,0
    tsw h2,0
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
    //First card start
    cirs 140,100,20,color
    cirs 400,100,20,color
    cirs 140,240,20,color
    cirs 400,240,20,color
    line 140,80,400,80,color
    line 420,100,420,240,color
    line 140,260,400,260,color
    line 120,100,120,240,color
    fill 140,80,260,180,color
    fill 120,100,20,140,color
    fill 400,100,20,140,color
    //First card end
    //Second card start
    cirs 490,100,20,color
    cirs 750,100,20,color
    cirs 490,240,20,color
    cirs 750,240,20,color
    line 490,80,750,80,color
    line 770,100,770,240,color
    line 490,260,750,260,color
    line 470,100,470,240,color
    fill 490,80,260,180,color
    fill 470,100,20,140,color
    fill 750,100,20,140,color
    //Second card end
    //Third card start
    cirs 140,290,20,color
    cirs 400,290,20,color
    cirs 140,430,20,color
    cirs 400,430,20,color
    line 140,270,400,270,color
    line 420,290,420,430,color
    line 140,450,400,450,color
    line 120,290,120,430,color
    fill 140,270,260,180,color
    fill 120,290,20,140,color
    fill 400,290,20,140,color
    //Third card end
    //Fourth card start
    cirs 490,290,20,color
    cirs 750,290,20,color
    cirs 490,430,20,color
    cirs 750,430,20,color
    line 490,270,750,270,color
    line 770,290,770,430,color
    line 490,450,750,450,color
    line 470,290,470,430,color
    fill 490,270,260,180,color
    fill 470,290,20,140,color
    fill 750,290,20,140,color
    //Fourth card end
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
    //Nav Drawer icons start
    if(fondo==65534)
    {
      //pic id info button
      va0.val=78
      //Font color
      fontColor.val=0
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      value2.pco=fontColor.val
      value4.pco=fontColor.val
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
      //Slider bg color
      h0.bco=fondo
      h1.bco=fondo
      h2.bco=fondo
      h3.bco=fondo
    }else if(fondo==63391)
    {
      //pic id info button
      th2.val=89
      //Font color
      fontColor.val=0
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      value2.pco=fontColor.val
      value4.pco=fontColor.val
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
      //Slider bg color
      h0.bco=fondo
      h1.bco=fondo
      h2.bco=fondo
      h3.bco=fondo
    }else if(fondo==65438)
    {
      //pic id info button
      th3.val=100
      //Font color
      fontColor.val=0
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      value2.pco=fontColor.val
      value4.pco=fontColor.val
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
      //Slider bg color
      h0.bco=fondo
      h1.bco=fondo
      h2.bco=fondo
      h3.bco=fondo
    }else if(fondo==63421)
    {
      //pic id info button
      th4.val=111
      //Font color
      fontColor.val=0
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      value2.pco=fontColor.val
      value4.pco=fontColor.val
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
      //Slider bg color
      h0.bco=fondo
      h1.bco=fondo
      h2.bco=fondo
      h3.bco=fondo
    }else if(fondo==6339)
    {
      //pic id info button
      th5.val=122
      //Font color
      fontColor.val=65535
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      value2.pco=fontColor.val
      value4.pco=fontColor.val
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
      //Slider bg color
      h0.bco=65535
      h1.bco=65535
      h2.bco=65535
      h3.bco=65535
    }else if(fondo==8484)
    {
      //pic id info button
      th6.val=133
      //Font color
      fontColor.val=65535
      //Values font color
      value1.pco=fontColor.val
      value3.pco=fontColor.val
      value2.pco=fontColor.val
      value4.pco=fontColor.val
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
      //Slider bg color
      h0.bco=65535
      h1.bco=65535
      h2.bco=65535
      h3.bco=65535
    }
    //Nav Drawer icons end
    //Text
    if(sys0==0)
    {
      //Nav bar text Spanish
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"INICIO"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESIÓN"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
      //Cards titles
      xstr 140,90,200,35,0,fontColor.val,color,0,1,3,"Presión de aspiración"
      xstr 490,90,200,35,0,fontColor.val,color,0,1,3,"Presión final"
      xstr 140,280,200,35,0,fontColor.val,color,0,1,3,"Temperatura final"
      xstr 490,280,200,35,0,fontColor.val,color,0,1,3,"Temperatura del aceite"
    }else if(sys0==1)
    {
      //Nav bar text Italian
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"INIZIO"
      xstr 275,45,70,25,2,fontColor.val,color,1,1,3,"PRESSIONE"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
      //Cards titles
      xstr 140,90,200,35,0,fontColor.val,color,0,1,3,"Pressione di aspirazione"
      xstr 490,90,200,35,0,fontColor.val,color,0,1,3,"Pressione finale"
      xstr 140,280,200,35,0,fontColor.val,color,0,1,3,"Temperatura finale"
      xstr 490,280,200,35,0,fontColor.val,color,0,1,3,"Temperatura dell'olio"
    }else if(sys0==2)
    {
      //Nav bar text French
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"DÉBUT"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSION"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPÉRATURE"
      //Cards titles
      xstr 140,90,200,35,0,fontColor.val,color,0,1,3,"Pression d'aspiration"
      xstr 490,90,200,35,0,fontColor.val,color,0,1,3,"Pression ultime"
      xstr 140,280,200,35,0,fontColor.val,color,0,1,3,"Température finale"
      xstr 490,280,200,35,0,fontColor.val,color,0,1,3,"Température de l'huile"
    }else if(sys0==3)
    {
      //Nav bar text English
      xstr 162,45,40,25,2,fontColor.val,color,1,1,3,"HOME"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSURE"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURE"
      //Cards titles
      xstr 140,90,200,35,0,fontColor.val,color,0,1,3,"Suction pressure"
      xstr 490,90,200,35,0,fontColor.val,color,0,1,3,"Final pressure"
      xstr 140,280,200,35,0,fontColor.val,color,0,1,3,"Final temperature"
      xstr 490,280,200,35,0,fontColor.val,color,0,1,3,"Oil temperature"
    }else if(sys0==4)
    {
      //Nav bar text German
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"ANFANG"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"DRUCK"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATUR"
      //Cards titles
      xstr 140,90,200,35,0,fontColor.val,color,0,1,3,"Saugdruck"
      xstr 490,90,200,35,0,fontColor.val,color,0,1,3,"Enddruck"
      xstr 140,280,200,35,0,fontColor.val,color,0,1,3,"Endtemperatur"
      xstr 490,280,200,35,0,fontColor.val,color,0,1,3,"Öltemperatur"
    }else if(sys0==5)
    {
      //Nav bar text Portuguese
      xstr 152,45,60,25,2,fontColor.val,color,1,1,3,"COMEÇO"
      xstr 280,45,65,25,2,fontColor.val,color,1,1,3,"PRESSÃO"
      xstr 390,45,100,25,2,fontColor.val,color,1,1,3,"TEMPERATURA"
      //Cards titles
      xstr 140,90,200,35,0,fontColor.val,color,0,1,3,"Pressão de sucção"
      xstr 490,90,200,35,0,fontColor.val,color,0,1,3,"Pressão final"
      xstr 140,280,200,35,0,fontColor.val,color,0,1,3,"Temperatura final"
      xstr 490,280,200,35,0,fontColor.val,color,0,1,3,"Temperatura do óleo"
    }
    //Vis
    vis value1,1
    vis value2,1
    vis value3,1
    vis value4,1
    vis t0,1
    vis t1,1
    vis h0,1
    vis h1,1
    vis h2,1
    vis h3,1
    vis t2,1
    vis t3,1
    vis t4,1
    value1.bco=color
    value2.bco=color
    value3.bco=color
    value4.bco=color
    t0.bco=color
    t1.bco=color
    t0.pco=fontColor.val
    t1.pco=fontColor.val
    t2.bco=color
    t3.bco=color
    t4.bco=color
    //Line to show tab selected
    line 152,65,212,65,fontColor.val

Touch press release m0
----------------------

.. code-block:: javascript

    //Nav bar start. Completes the pressed button effect
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

Touch press event m1
--------------------

.. code-block:: javascript

    // Creates a pressed button effect
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
    //
    page Presion

Touch press event m2
--------------------

.. code-block:: javascript

    // Creates a pressed button effect
    cirs 410,40,30,fondo
    cirs 470,40,30,fondo
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

Touch pressed event bInfoH
--------------------------

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
      page Mensajes
    }else
    {
      Info.returnPage.val=dp
      page Info
    }

Touch release event bInfoH
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

Touch press event bMenuH
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

Touch release event bMenuH
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

Touch press event bStartH
-------------------------

.. code-block:: javascript

    //Only activates if the status is inactive
    if(sys2==0)
    {
      //Start high
      sys2=1
      //Start command
      printh 43 F0 FF FF FF
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

Touch press event bStopH
------------------------

.. code-block:: javascript

    //Only deactivates if the status is active
    if(sys2==1)
    {
      //Start Low
      sys2=0
      //Stop command
      printh 43 F1 FF FF FF
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

Timer event tm0
----------------

.. code-block:: javascript

    if(h0.val>maxP1||h1.val>maxP2||h2.val>maxT2||h3.val>maxTO)
    {
      //Saves 2 to indicate Error
      sys1=2
      //va3,va4,va5,va6 used to send "prints" only ONCE when the error occurred
      if(va3.val<1&&h0.val>maxP1)
      {
        //prints "ErrorH0",0
        printh 49 F6 FF FF FF
        va3.val++
      }else if(va4.val<1&&h1.val>maxP2)
      {
        //prints "ErrorH1",0
        printh 49 F8 FF FF FF
        va4.val++
      }else if(va5.val<1&&h2.val>maxT2)
      {
        //prints "ErrorH2",0
        printh 49 FA FF FF FF
        va5.val++
      }else if(va6.val<1&&h3.val>maxTO)
      {
        //prints "ErrorH3",0
        printh 49 FC FF FF FF
        va6.val++
      }else if(va7.val<1&&h0.val>warnP1&&h0.val<=maxP1)
      {
        //prints "WarningH0",0
        printh 49 F7 FF FF FF
        va7.val++
      }else if(va8.val<1&&h1.val>warnP2&&h1.val<=maxP2)
      {
        //prints "WarningH1",0
        printh 49 F9 FF FF FF
        va8.val++
      }else if(va9.val<1&&h2.val>warnT2&&h2.val<=maxT2)
      {
        //prints "WarningH2",0
        printh 49 FB FF FF FF
        va9.val++
      }else if(va10.val<1&&h3.val>warnTO&&h3.val<=maxTO)
      {
        //prints "WarningH3",0
        printh 49 FD FF FF FF
        va10.val++
      }
      //Starts blinking event
      tm0.en=1
      tm0.tim=500
      //Draws a red bar at the top
      cirs 150,40,30,va1.val
      cirs 760,40,30,va1.val
      line 150,10,760,10,va1.val
      line 150,70,760,70,va1.val
      fill 150,10,610,60,va1.val
      //Changes the info image every .tim
      if(fondo==65534)
      {
        pic 25,30,va0.val
      }else if(fondo==63391)
      {
        pic 25,30,th2.val
      }else if(fondo==65438)
      {
        pic 25,30,th3.val
      }else if(fondo==63421)
      {
        pic 25,30,th4.val
      }else if(fondo==6339)
      {
        pic 25,30,th5.val
      }else if(fondo==8484)
      {
        pic 25,30,th6.val
      }
      //
      if(h0.val>maxP1)
      {
        if(sys0==0)
        {
          //Spanish
          xstr 160,30,250,25,4,65535,63488,0,0,3,"Presión de aspiración"
        }else if(sys0==1)
        {
          //Italian
          xstr 160,30,250,25,4,65535,63488,0,0,3,"Pressione di aspirazione"
        }else if(sys0==2)
        {
          //French
          xstr 160,30,250,25,4,65535,63488,0,0,3,"Pression d'aspiration"
        }else if(sys0==3)
        {
          //English
          xstr 160,30,250,25,4,65535,63488,0,0,3,"Suction pressure"
        }else if(sys0==4)
        {
          //German
          xstr 160,30,250,25,4,65535,63488,0,0,3,"Saugdruck"
        }else if(sys0==5)
        {
          //Portuguese
          xstr 160,30,250,25,4,65535,63488,0,0,3,"Pressão de sucção"
        }
      }else if(h1.val>maxP2)
      {
        if(sys0==0)
        {
          //Spanish
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Presión final"
        }else if(sys0==1)
        {
          //Italian
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Pressione finale"
        }else if(sys0==2)
        {
          //French
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Pression ultime"
        }else if(sys0==3)
        {
          //English
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Final pressure"
        }else if(sys0==4)
        {
          //German
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Enddruck"
        }else if(sys0==5)
        {
          //Portuguese
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Pressão final"
        }
      }else if(h2.val>maxT2)
      {
        if(sys0==0)
        {
          //Spanish
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura final"
        }else if(sys0==1)
        {
          //Italian
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura finale"
        }else if(sys0==2)
        {
          //French
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Température finale"
        }else if(sys0==3)
        {
          //English
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Final temperature"
        }else if(sys0==4)
        {
          //German
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Endtemperatur"
        }else if(sys0==5)
        {
          //Portuguese
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura final"
        }
      }else if(h3.val>maxTO)
      {
        if(sys0==0)
        {
          //Spanish
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura del aceite"
        }else if(sys0==1)
        {
          //Italian
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura dell'olio"
        }else if(sys0==2)
        {
          //French
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Température de l'huile"
        }else if(sys0==3)
        {
          //English
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Oil temperature"
        }else if(sys0==4)
        {
          //German
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Öltemperatur"
        }else if(sys0==5)
        {
          //Portuguese
          xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura do óleo"
        }
      }
      //Changes the color depending the theme selected
      if(fondo==65534)
      {
        va0.val=va0.val+91
        va1.val=va1.val+20187
        if(va0.val>169)
        {
          va0.val=78
          va1.val=45347
        }
      }else if(fondo==63391)
      {
        //
        th2.val=th2.val+82
        va1.val=va1.val+18044
        if(th2.val>171)
        {
          th2.val=89
          va1.val=45347
        }
      }else if(fondo==65438)
      {
        th3.val=th3.val+73
        va1.val=va1.val+20091
        if(th3.val>173)
        {
          th3.val=100
          va1.val=45347
        }
      }else if(fondo==63421)
      {
        th4.val=th4.val+64
        va1.val=va1.val+18074
        if(th4.val>175)
        {
          th4.val=111
          va1.val=45347
        }
      }else if(fondo==6339)
      {
        th5.val=th5.val+55
        va1.val=va1.val-39008
        if(th5.val>177)
        {
          th5.val=122
          va1.val=45347
        }
      }else if(fondo==8484)
      {
        th6.val=th6.val+46
        va1.val=va1.val-36863
        if(th6.val>179)
        {
          th6.val=133
          va1.val=45347
        }
      }
      //Ends blinking event
    }else if(h0.val>warnP1&&h0.val<=maxP1)
    {
      //Saves 1 to indicate Warning
      sys1=1
      if(va7.val<1&&h0.val>warnP1&&h0.val<=maxP1)
      {
        //prints "WarningH0",0
        printh 49 F7 FF FF FF
        va7.val++
      }else if(va8.val<1&&h1.val>warnP2&&h1.val<=maxP2)
      {
        //prints "WarningH1",0
        printh 49 F9 FF FF FF
        va8.val++
      }else if(va9.val<1&&h2.val>warnT2&&h2.val<=maxT2)
      {
        //prints "WarningH2",0
        printh 49 FB FF FF FF
        va9.val++
      }else if(va10.val<1&&h3.val>warnTO&&h3.val<=maxTO)
      {
        //prints "WarningH3",0
        printh 49 FD FF FF FF
        va10.val++
      }
      //Starts blinking event
      tm0.en=1
      tm0.tim=500
      //Draws a yellow bar at the top
      cirs 150,40,30,va2.val
      cirs 760,40,30,va2.val
      line 150,10,760,10,va2.val
      line 150,70,760,70,va2.val
      fill 150,10,610,60,va2.val
      //Changes the info image every .tim
      if(fondo==65534)
      {
        pic 25,30,va0.val
        va0.val=va0.val+92
        va2.val=va2.val+6903
        if(va0.val>170)
        {
          va0.val=78
          va2.val=58631
        }
      }else if(fondo==63391)
      {
        pic 25,30,th2.val
        th2.val=th2.val+83
        va2.val=va2.val+4760
        if(th2.val>172)
        {
          th2.val=89
          va2.val=58631
        }
      }else if(fondo==65438)
      {
        pic 25,30,th3.val
        th3.val=th3.val+74
        va2.val=va2.val+6807
        if(th3.val>174)
        {
          th3.val=100
          va2.val=58631
        }
      }else if(fondo==63421)
      {
        pic 25,30,th4.val
        th4.val=th4.val+65
        va2.val=va2.val+4790
        if(th4.val>176)
        {
          th4.val=111
          va2.val=58631
        }
      }else if(fondo==6339)
      {
        pic 25,30,th5.val
        th5.val=th5.val+56
        va2.val=va2.val-52292
        if(th5.val>178)
        {
          th5.val=122
          va2.val=58631
        }
      }else if(fondo==8484)
      {
        pic 25,30,th6.val
        th6.val=th6.val+47
        va2.val=va2.val-50147
        if(th6.val>180)
        {
          th6.val=133
          va2.val=58631
        }
      }
      //
      if(sys0==0)
      {
        //Spanish
        xstr 160,30,250,25,4,65535,63488,0,0,3,"Presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 160,30,250,25,4,65535,63488,0,0,3,"Pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 160,30,250,25,4,65535,63488,0,0,3,"Pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 160,30,250,25,4,65535,63488,0,0,3,"Suction pressure"
      }else if(sys0==4)
      {
        //German
        xstr 160,30,250,25,4,65535,63488,0,0,3,"Saugdruck"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 160,30,250,25,4,65535,63488,0,0,3,"Pressão de sucção"
      }
    }else if(h1.val>warnP2&&h1.val<=maxP2)
    {
      //Saves 1 to indicate Warning
      sys1=1
      if(va7.val<1&&h0.val>warnP1&&h0.val<=maxP1)
      {
        //prints "WarningH0",0
        printh 49 F7 FF FF FF
        va7.val++
      }else if(va8.val<1&&h1.val>warnP2&&h1.val<=maxP2)
      {
        //prints "WarningH1",0
        printh 49 F9 FF FF FF
        va8.val++
      }else if(va9.val<1&&h2.val>warnT2&&h2.val<=maxT2)
      {
        //prints "WarningH2",0
        printh 49 FB FF FF FF
        va9.val++
      }else if(va10.val<1&&h3.val>warnTO&&h3.val<=maxTO)
      {
        //prints "WarningH3",0
        printh 49 FD FF FF FF
        va10.val++
      }
      //Starts blinking event
      tm0.en=1
      tm0.tim=500
      //Draws a yellow bar at the top
      cirs 150,40,30,va2.val
      cirs 760,40,30,va2.val
      line 150,10,760,10,va2.val
      line 150,70,760,70,va2.val
      fill 150,10,610,60,va2.val
      //Changes the info image every .tim
      if(fondo==65534)
      {
        pic 25,30,va0.val
        va0.val=va0.val+92
        va2.val=va2.val+6903
        if(va0.val>170)
        {
          va0.val=78
          va2.val=58631
        }
      }else if(fondo==63391)
      {
        pic 25,30,th2.val
        th2.val=th2.val+83
        va2.val=va2.val+4760
        if(th2.val>172)
        {
          th2.val=89
          va2.val=58631
        }
      }else if(fondo==65438)
      {
        pic 25,30,th3.val
        th3.val=th3.val+74
        va2.val=va2.val+6807
        if(th3.val>174)
        {
          th3.val=100
          va2.val=58631
        }
      }else if(fondo==63421)
      {
        pic 25,30,th4.val
        th4.val=th4.val+65
        va2.val=va2.val+4790
        if(th4.val>176)
        {
          th4.val=111
          va2.val=58631
        }
      }else if(fondo==6339)
      {
        pic 25,30,th5.val
        th5.val=th5.val+56
        va2.val=va2.val-52292
        if(th5.val>178)
        {
          th5.val=122
          va2.val=58631
        }
      }else if(fondo==8484)
      {
        pic 25,30,th6.val
        th6.val=th6.val+47
        va2.val=va2.val-50147
        if(th6.val>180)
        {
          th6.val=133
          va2.val=58631
        }
      }
      //
      if(sys0==0)
      {
        //Spanish
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Pression ultime"
      }else if(sys0==3)
      {
        //English
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Final pressure"
      }else if(sys0==4)
      {
        //German
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Enddruck"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Pressão final"
      }
    }else if(h2.val>warnT2&&h2.val<=maxT2)
    {
      //Saves 1 to indicate Warning
      sys1=1
      if(va7.val<1&&h0.val>warnP1&&h0.val<=maxP1)
      {
        //prints "WarningH0",0
        printh 49 F7 FF FF FF
        va7.val++
      }else if(va8.val<1&&h1.val>warnP2&&h1.val<=maxP2)
      {
        //prints "WarningH1",0
        printh 49 F9 FF FF FF
        va8.val++
      }else if(va9.val<1&&h2.val>warnT2&&h2.val<=maxT2)
      {
        //prints "WarningH2",0
        printh 49 FB FF FF FF
        va9.val++
      }else if(va10.val<1&&h3.val>warnTO&&h3.val<=maxTO)
      {
        //prints "WarningH3",0
        printh 49 FD FF FF FF
        va10.val++
      }
      //Starts blinking event
      tm0.en=1
      tm0.tim=500
      //Draws a yellow bar at the top
      cirs 150,40,30,va2.val
      cirs 760,40,30,va2.val
      line 150,10,760,10,va2.val
      line 150,70,760,70,va2.val
      fill 150,10,610,60,va2.val
      //Changes the info image every .tim
      if(fondo==65534)
      {
        pic 25,30,va0.val
        va0.val=va0.val+92
        va2.val=va2.val+6903
        if(va0.val>170)
        {
          va0.val=78
          va2.val=58631
        }
      }else if(fondo==63391)
      {
        pic 25,30,th2.val
        th2.val=th2.val+83
        va2.val=va2.val+4760
        if(th2.val>172)
        {
          th2.val=89
          va2.val=58631
        }
      }else if(fondo==65438)
      {
        pic 25,30,th3.val
        th3.val=th3.val+74
        va2.val=va2.val+6807
        if(th3.val>174)
        {
          th3.val=100
          va2.val=58631
        }
      }else if(fondo==63421)
      {
        pic 25,30,th4.val
        th4.val=th4.val+65
        va2.val=va2.val+4790
        if(th4.val>176)
        {
          th4.val=111
          va2.val=58631
        }
      }else if(fondo==6339)
      {
        pic 25,30,th5.val
        th5.val=th5.val+56
        va2.val=va2.val-52292
        if(th5.val>178)
        {
          th5.val=122
          va2.val=58631
        }
      }else if(fondo==8484)
      {
        pic 25,30,th6.val
        th6.val=th6.val+47
        va2.val=va2.val-50147
        if(th6.val>180)
        {
          th6.val=133
          va2.val=58631
        }
      }
      //
      if(sys0==0)
      {
        //Spanish
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Température finale"
      }else if(sys0==3)
      {
        //English
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Final temperature"
      }else if(sys0==4)
      {
        //German
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Endtemperatur"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura final"
      }
    }else if(h3.val>warnTO&&h3.val<=maxTO)
    {
      //Saves 1 to indicate Warning
      sys1=1
      if(va7.val<1&&h0.val>warnP1&&h0.val<=maxP1)
      {
        //prints "WarningH0",0
        printh 49 F7 FF FF FF
        va7.val++
      }else if(va8.val<1&&h1.val>warnP2&&h1.val<=maxP2)
      {
        //prints "WarningH1",0
        printh 49 F9 FF FF FF
        va8.val++
      }else if(va9.val<1&&h2.val>warnT2&&h2.val<=maxT2)
      {
        //prints "WarningH2",0
        printh 49 FB FF FF FF
        va9.val++
      }else if(va10.val<1&&h3.val>warnTO&&h3.val<=maxTO)
      {
        //prints "WarningH3",0
        printh 49 FD FF FF FF
        va10.val++
      }
      //Starts blinking event
      tm0.en=1
      tm0.tim=500
      //Draws a yellow bar at the top
      cirs 150,40,30,va2.val
      cirs 760,40,30,va2.val
      line 150,10,760,10,va2.val
      line 150,70,760,70,va2.val
      fill 150,10,610,60,va2.val
      //Changes the info image every .tim
      if(fondo==65534)
      {
        pic 25,30,va0.val
        va0.val=va0.val+92
        va2.val=va2.val+6903
        if(va0.val>170)
        {
          va0.val=78
          va2.val=58631
        }
      }else if(fondo==63391)
      {
        pic 25,30,th2.val
        th2.val=th2.val+83
        va2.val=va2.val+4760
        if(th2.val>172)
        {
          th2.val=89
          va2.val=58631
        }
      }else if(fondo==65438)
      {
        pic 25,30,th3.val
        th3.val=th3.val+74
        va2.val=va2.val+6807
        if(th3.val>174)
        {
          th3.val=100
          va2.val=58631
        }
      }else if(fondo==63421)
      {
        pic 25,30,th4.val
        th4.val=th4.val+65
        va2.val=va2.val+4790
        if(th4.val>176)
        {
          th4.val=111
          va2.val=58631
        }
      }else if(fondo==6339)
      {
        pic 25,30,th5.val
        th5.val=th5.val+56
        va2.val=va2.val-52292
        if(th5.val>178)
        {
          th5.val=122
          va2.val=58631
        }
      }else if(fondo==8484)
      {
        pic 25,30,th6.val
        th6.val=th6.val+47
        va2.val=va2.val-50147
        if(th6.val>180)
        {
          th6.val=133
          va2.val=58631
        }
      }
      //
      if(sys0==0)
      {
        //Spanish
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura dell'olio"
      }else if(sys0==2)
      {
        //French
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Température de l'huile"
      }else if(sys0==3)
      {
        //English
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Oil temperature"
      }else if(sys0==4)
      {
        //German
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Öltemperatur"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 160,30,300,25,4,65535,63488,0,0,3,"Temperatura do óleo"
      }
    }