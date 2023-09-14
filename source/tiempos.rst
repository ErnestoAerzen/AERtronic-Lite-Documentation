Tiempos Nextion Page
=====================

Description
-----------

Introduction
-------------

This document provides a detailed explanation of a Nextion display script that controls various user interface elements, including navigation drawers, navigation icons, page containers, page titles, and text localization. The script uses the Nextion scripting language to create an interactive user interface.

Script Overview
----------------

The script consists of several sections, each serving a specific purpose:

1. **Navigation Drawer**
   - The navigation drawer section creates a user interface element with four circular icons, connecting lines, and filled rectangles. This section defines the layout of the navigation drawer.
   - Elements are positioned and styled using the `cirs`, `line`, and `fill` commands.

2. **Navigation Drawer Icons**
   - This section determines the appearance of navigation icons within the navigation drawer based on the value of the `fondo` variable, representing the selected theme.
   - Six different themes are defined, each with its set of icon IDs and colors. The selected theme is determined by the value of `fondo`.

3. **Page Containers**
   - Two main containers are created to organize the content of the display. Each container contains circular elements and connecting lines.
   - The `cirs` and `line` commands are used to define the containers' layout and appearance.

4. **Page Title**
   - A page title section creates two circular icons and connecting lines to form a title bar for the active page.
   - Elements are positioned and styled using the `cirs` and `line` commands.

5. **Page Text**
   - Text elements are displayed on the page based on the value of the `sys0` variable, representing the selected language.
   - Text content and positioning are controlled using the `xstr` command, with different text for each language.

6. **Conclusion**
   - This section summarizes the script's functionality and explains how it creates an interactive user interface with navigation elements and localized text.

Conclusion
----------

This documentation provides a comprehensive explanation of a Nextion display script that creates an interactive user interface with navigation drawers, navigation icons, page containers, and text localization. Developers can customize this script to create user-friendly Nextion display applications with dynamic content and a visually appealing design.

The provided script serves as a foundation for building Nextion display projects with interactive navigation and multilingual support, leveraging the capabilities of the Nextion scripting language.

Preinitialize event Tiempos
---------------------------

.. code-block:: javascript

    // Changes the page's background color
    Tiempos.bco=fondo
    // Sets the main color of the container
    topTime.bco=color
    // Sends the page's number over serial
    sendme

Postinitialize event Tiempos
----------------------------

.. code-block:: javascript

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
    //Nav Drawer icons start
    if(fondo==65534)
    {
      //Font color
      fontColor.val=0
      //Theme 1
      pic 25,30,78
      pic 25,120,144
      pic 25,400,146
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
    }
    //Nav Drawer icons end
    //Page containers start
    //First container
    cirs 200,130,30,color
    cirs 700,130,30,color
    line 200,100,700,100,color
    line 200,160,700,160,color
    fill 200,100,500,60,color
    //Pages containers end
    //Page title start
    cirs 310,40,30,color
    cirs 540,40,30,color
    line 310,10,540,10,color
    line 310,70,540,70,color
    fill 310,10,240,60,color
    //Page title end
    //Page text start
    if(sys0==0)
    {
      //spanish
      xstr 320,25,210,25,4,fontColor.val,color,1,1,3,"Tiempo de operación"
      xstr 220,120,250,25,0,fontColor.val,0xDF39,0,1,3,"Horas en funcionamiento"
    }else if(sys0==1)
    {
      //italian
      xstr 300,25,245,25,4,fontColor.val,color,1,1,3,"Tempo di funzionamento"
      xstr 220,120,250,25,0,fontColor.val,0xDF39,0,1,3,"Ore in funzione"
    }else if(sys0==2)
    {
      //french
      xstr 320,25,210,25,4,fontColor.val,color,1,1,3,"Moment de l'opération"
      xstr 220,120,250,25,0,fontColor.val,0xDF39,0,1,3,"Heures de fonctionnement"
    }else if(sys0==3)
    {
      //english
      xstr 320,25,210,25,4,fontColor.val,color,1,1,3,"Operation time"
      xstr 220,120,250,25,0,fontColor.val,0xDF39,0,1,3,"Hours in operation"
    }else if(sys0==4)
    {
      //german
      xstr 320,25,210,25,4,fontColor.val,color,1,1,3,"Betriebszeit"
      xstr 220,120,250,25,0,fontColor.val,0xDF39,0,1,3,"Betriebsstunden"
    }else if(sys0==5)
    {
      //portuguese
      xstr 320,25,210,25,4,fontColor.val,color,1,1,3,"Tempo de operação"
      xstr 220,120,250,25,0,fontColor.val,0xDF39,0,1,3,"Horas de operação"
    }
    //Page text end

Touch press event bInfoT
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
    Info.returnPage.val=dp

Touch release event bInfoT
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
    //
    page Info

Touch press event bHomeT
------------------------

.. code-block:: javascript

    //Changes the image according the theme selected
    if(fondo==65534)
    {
      pic 25,120,145
    }else if(fondo==63391)
    {
      pic 25,120,149
    }else if(fondo==65438)
    {
      pic 25,120,153
    }else if(fondo==63421)
    {
      pic 25,120,157
    }else if(fondo==6339)
    {
      pic 25,120,161
    }else if(fondo==8484)
    {
      pic 25,120,165
    }

Touch release event bHomeT
--------------------------

.. code-block:: javascript

    //Restores the image according the theme selected
    if(fondo==65534)
    {
      pic 25,120,144
    }else if(fondo==63391)
    {
      pic 25,120,148
    }else if(fondo==65438)
    {
      pic 25,120,152
    }else if(fondo==63421)
    {
      pic 25,120,156
    }else if(fondo==6339)
    {
      pic 25,120,160
    }else if(fondo==8484)
    {
      pic 25,120,164
    }
    //
    page Home

Touch press event bBackT
------------------------

.. code-block:: javascript

    //Changes the image according the theme selected
    if(fondo==65534)
    {
      pic 25,400,147
    }else if(fondo==63391)
    {
      pic 25,400,151
    }else if(fondo==65438)
    {
      pic 25,400,155
    }else if(fondo==63421)
    {
      pic 25,400,159
    }else if(fondo==6339)
    {
      pic 25,400,163
    }else if(fondo==8484)
    {
      pic 25,400,167
    }

Touch release event bBackT
--------------------------

.. code-block:: javascript

    //Restores the image according the theme selected
    if(fondo==65534)
    {
      pic 25,400,146
    }else if(fondo==63391)
    {
      pic 25,400,150
    }else if(fondo==65438)
    {
      pic 25,400,154
    }else if(fondo==63421)
    {
      pic 25,400,159
    }else if(fondo==6339)
    {
      pic 25,400,162
    }else if(fondo==8484)
    {
      pic 25,400,166
    }
    //
    page Menu
