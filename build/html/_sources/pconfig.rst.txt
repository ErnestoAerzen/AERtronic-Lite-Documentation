PConfig Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides an in-depth explanation of a Nextion display script. The script is designed to control a Nextion display and create a user interface, including a navigation drawer, page title, and associated elements.

Script Overview
---------------

The script provided focuses on creating a user interface with the following components:

1. **Navigation Drawer (Nav Drawer)**
   - The navigation drawer is designed to provide menu-like functionality.
   - It consists of four circular buttons, lines forming a rectangular border around them, and filled rectangles for background.
   
2. **Page Title**
   - The page title section is located at the top of the display.
   - It comprises two circular buttons, lines connecting them, and a filled rectangle for background.

3. **Navigation Drawer Icons**
   - Icons within the navigation drawer change based on the background color.
   - The script includes six themes (Theme 1 to Theme 6) with different icon arrangements.
   
4. **Text**
   - Text elements (xstr) are used for displaying menu item names.
   - Text content varies depending on the selected language (Spanish, Italian, French, English, German, Portuguese) specified by the sys0 variable.

Script Explanation
------------------

Below, we provide a detailed explanation of each section and its associated commands within the script:

1. **Navigation Drawer (Nav Drawer)**
   - Four circular buttons (cirs) are created at specific coordinates with defined radii and colors.
   - Four lines (line) form a rectangular shape around the buttons, creating the appearance of a drawer.
   - Two filled rectangles (fill) complete the visual representation of the navigation drawer.

2. **Page Title**
   - Two circular buttons (cirs) at the top form a decorative element, resembling a page title.
   - Lines (line) connect these circles, and a filled rectangle (fill) adds background color to the title section.

3. **Navigation Drawer Icons**
   - Icons (pic) are displayed based on the value of the background color (fondo).
   - Each theme (Theme 1 to Theme 6) defines different icon arrangements based on the background color.

4. **Text**
   - Text elements (xstr) are used to display menu item names.
   - Text content varies according to the selected language specified by the sys0 variable.
   - Multiple language options are available, including Spanish, Italian, French, English, German, and Portuguese.

Conclusion
-----------

This documentation provides a comprehensive understanding of the Nextion display script, highlighting its components, icon themes, and language support. Developers can use this script as a reference to create interactive user interfaces for Nextion displays, enhancing the user experience of their embedded systems.

Please note that this script serves as an example and should be customized to suit your specific Nextion display application.

Preinitialize event PConfig
---------------------------

.. code-block:: javascript

    // Changes the page's background color
    PConfig.bco=fondo
    // Sets the backlight of the system
    blightH.val=dim

Postinitialize event PConfig
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
    //Page title start
    cirs 300,40,30,color
    cirs 550,40,30,color
    line 300,10,550,10,color
    line 300,70,550,70,color
    fill 300,10,250,60,color
    //Page title end
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
    //Text start
    if(sys0==0)
    {
      //Spanish
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Configuración pantalla"
      xstr 140,120,200,25,7,fontColor.val,fondo,0,1,3,"Brillo"
    }else if(sys0==1)
    {
      //Italian
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Configurazione dello schermo"
      xstr 140,120,200,25,7,fontColor.val,fondo,0,1,3,"Incandescenza"
    }else if(sys0==2)
    {
      //French
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Configuration de l'écran"
      xstr 140,120,200,25,7,fontColor.val,fondo,0,1,3,"Briller"
    }else if(sys0==3)
    {
      //English
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Screen configuration"
      xstr 140,120,200,25,7,fontColor.val,fondo,0,1,3,"Brightness"
    }else if(sys0==4)
    {
      //German
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Bildschirmkonfiguration"
      xstr 140,120,200,25,7,fontColor.val,fondo,0,1,3,"Glühen"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Configuração da tela"
      xstr 140,120,200,25,7,fontColor.val,fondo,0,1,3,"Brilho"
    }

Touch move event blightH
------------------------

.. code-block:: javascript

    // Changes the value of the dims backlight 
    dims=blightH.val

Touch press event bInfoPC
-------------------------

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

Touch release event bInfoPC
---------------------------

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

Touch press event bHomePC
-------------------------

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

Touch release event bHomePC
---------------------------

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

Touch press event bBackPC
-------------------------

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

Touch release event bBackPC
---------------------------

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
    page menuServicio
    