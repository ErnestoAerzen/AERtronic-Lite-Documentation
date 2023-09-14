Varios Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script that controls various user interface elements, including navigation drawers, navigation icons, page titles, buttons, and text localization. The script uses the Nextion scripting language to create an interactive user interface.

Script Overview
---------------

The script consists of several sections, each serving a specific purpose:

1. **Navigation Drawer**
   - The navigation drawer section creates a user interface element with four circular icons, connecting lines, and filled rectangles. This section defines the layout of the navigation drawer.
   - Elements are positioned and styled using the `cirs`, `line`, and `fill` commands.

2. **Page Title**
   - A page title section creates two circular icons and connecting lines to form a title bar for the active page.
   - Elements are positioned and styled using the `cirs` and `line` commands.

3. **First Button**
   - This section defines the appearance of a button with two circular icons and connecting lines. The button has a unique color (45347) and is positioned below the page title.

4. **Navigation Drawer Icons**
   - This section determines the appearance of navigation icons within the navigation drawer based on the value of the `fondo` variable, representing the selected theme.
   - Six different themes are defined, each with its set of icon IDs and colors. The selected theme is determined by the value of `fondo`.

5. **Page Text**
   - Text elements are displayed on the page based on the value of the `sys0` variable, representing the selected language.
   - Text content and positioning are controlled using the `xstr` command, with different text for each language.

6. **Conclusion**
   - This section summarizes the script's functionality and explains how it creates an interactive user interface with navigation elements, buttons, and text localization.

Conclusion
----------

This documentation provides a comprehensive explanation of a Nextion display script that creates an interactive user interface with navigation drawers, page titles, buttons, and text localization. Developers can customize this script to create user-friendly Nextion display applications with dynamic content, navigation, and multilingual support, leveraging the capabilities of the Nextion scripting language.

The provided script serves as a foundation for building Nextion display projects with interactive navigation, buttons, and localized text, enhancing the user experience and user interface design.

Preinitialize event Varios
--------------------------

.. code-block:: javascript

    // Changes the page's background color
    Varios.bco=fondo

Postinitialize event Varios
---------------------------

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
    //Page title start
    cirs 300,40,30,color
    cirs 550,40,30,color
    line 300,10,550,10,color
    line 300,70,550,70,color
    fill 300,10,250,60,color
    //Page title end
    //First button
    cirs 520,150,20,45347
    cirs 620,150,20,45347
    line 520,130,620,130,45347
    line 520,170,620,170,45347
    fill 520,130,100,40,45347
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
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Varios"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Deshabilitar arranque remoto"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Apagar"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Parecchi"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Disabilita l'avvio remoto"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Per disattivare"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Nombreuses"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Désactiver le démarrage à distance"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Éteindre"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Divers"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Disable remote start"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Turn off"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Mehrere"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Fernstart deaktivieren"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Ausschalten"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Vários"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Desativar início remoto"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Desligar"
    }
    //Page text end

Touch press event m0
--------------------

.. code-block:: javascript

    //First button
    cirs 520,150,20,fondo
    cirs 620,150,20,fondo
    line 520,130,620,130,fondo
    line 520,170,620,170,fondo
    fill 520,130,100,40,fondo
    //Send command
    printh 43 F2 FF FF FF

Touch release event m0
----------------------

.. code-block:: javascript

    //First button
    cirs 520,150,20,45347
    cirs 620,150,20,45347
    line 520,130,620,130,45347
    line 520,170,620,170,45347
    fill 520,130,100,40,45347
    //Text
    if(sys0==0)
    {
      //Spanish
      xstr 520,140,100,25,6,65535,45347,1,1,3,"Apagar"
    }else if(sys0==1)
    {
      //Italian
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Per disattivare"
    }else if(sys0==2)
    {
      //French
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Éteindre"
    }else if(sys0==3)
    {
      //English
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Turn off"
    }else if(sys0==4)
    {
      //German
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Ausschalten"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Desligar"
    }

Touch press event bInfoV
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

Touch release event bInfoV
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

Touch press event bHomeV
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

Touch release event bHomeV
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

Touch press event bBackV
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

Touch release event bBackV
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
    page ControlSystem
    