Pantalla Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script used to create a user interface with a navigation drawer, menu buttons, page title, and associated elements. The script allows for customization of colors, icons, and text based on user preferences.

Script Overview
---------------

The script consists of the following sections:

1. **Custom Color (cbutton.val=color)**
   - This command sets the value of `cbutton.val` to the specified color.

2. **Navigation Drawer (Nav Drawer)**
   - The navigation drawer is created with four circular buttons (cirs), lines (line) forming a rectangular border, and filled rectangles (fill) for background.

3. **Menu Buttons**
   - Five sets of menu buttons are defined, each consisting of two circular buttons, lines connecting them, and filled rectangles for background. Button properties, such as color, are determined by `cbutton.val`.

4. **Page Title**
   - The page title is created using two circular buttons, connecting lines, and a filled rectangle for background.

5. **Navigation Drawer Icons**
   - Icons within the navigation drawer change based on the value of `fondo` (background color).
   - Each theme (Theme 1 to Theme 6) defines different icon arrangements based on the background color.
   - Additional icons are defined for menu buttons corresponding to each theme.

6. **Page Text**
   - Text elements (xstr) are used to display menu item names.
   - Text content varies depending on the selected language (Spanish, Italian, French, English, German, Portuguese) specified by the `sys0` variable.

Script Explanation
------------------

Let's break down each section of the script:

1. **Custom Color**
   - This section sets the color value for `cbutton.val`. This color is used to define the appearance of various elements within the interface.

2. **Navigation Drawer (Nav Drawer)**
   - The navigation drawer is visually defined with circular buttons and lines forming a rectangular shape. Colors are based on the specified `color` variable.

3. **Menu Buttons**
   - Five sets of menu buttons are defined. Each set consists of circular buttons, lines, and filled rectangles. The color is determined by `cbutton.val`.

4. **Page Title**
   - The page title section is created with two circular buttons, connecting lines, and a filled rectangle. Colors are defined by `color`.

5. **Navigation Drawer Icons**
   - Icons change according to the background color (`fondo`) and theme.
   - Six themes (Theme 1 to Theme 6) are defined, each with its own icon arrangement. Icons are specified using the `pic` command.
   - For each theme, icons for menu buttons are also defined.

6. **Page Text**
   - Text elements (`xstr`) are used to display menu item names.
   - Text content is determined by the selected language (`sys0`), with support for Spanish, Italian, French, English, German, and Portuguese.

Conclusion
----------

This documentation provides a comprehensive overview of the Nextion display script, including its structure, elements, and customization options. Developers can use this script as a reference to create interactive user interfaces for Nextion displays, tailoring colors, icons, and text to suit their application's requirements.

Please note that this script is an example and should be adapted to meet the specific needs of your Nextion display project.

Preinitialize event Pantalla
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Pantalla.bco=fondo
    // Sets the main color of the buttons
    cbutton.val=0xDF39
    // Custom command see README.md file to learn more.
    printh 52 FE FF FF FF

Postinitialize event Pantalla
-----------------------------

.. code-block:: javascript

    cbutton.val=color
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
    //Menu buttons start
    //First button
    cirs 150,130,30,cbutton.val
    cirs 390,130,30,cbutton.val
    line 150,100,390,100,cbutton.val
    line 150,160,390,160,cbutton.val
    fill 150,100,240,60,cbutton.val
    //Second button
    cirs 500,130,30,cbutton.val
    cirs 740,130,30,cbutton.val
    line 500,100,740,100,cbutton.val
    line 500,160,740,160,cbutton.val
    fill 500,100,240,60,cbutton.val
    //Third button
    cirs 150,210,30,cbutton.val
    cirs 390,210,30,cbutton.val
    line 150,180,390,180,cbutton.val
    line 150,240,390,240,cbutton.val
    fill 150,180,240,60,cbutton.val
    //Fourth button
    cirs 500,210,30,cbutton.val
    cirs 740,210,30,cbutton.val
    line 500,180,740,180,cbutton.val
    line 500,240,740,240,cbutton.val
    fill 500,180,240,60,cbutton.val
    //Fifth button
    cirs 150,290,30,cbutton.val
    cirs 390,290,30,cbutton.val
    line 150,260,390,260,cbutton.val
    line 390,320,390,320,cbutton.val
    fill 150,260,240,60,cbutton.val
    //Menu buttons end
    //Page title start
    cirs 330,40,30,color
    cirs 520,40,30,color
    line 330,10,520,10,color
    line 330,70,520,70,color
    fill 330,10,190,60,color
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
      //Button's icons
      pic 150,115,349
      pic 500,115,350
      pic 150,195,351
      pic 500,195,352
      pic 150,275,353
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Button's icons
      pic 150,115,354
      pic 500,115,355
      pic 150,195,356
      pic 500,195,357
      pic 150,275,358
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Button's icons
      pic 150,115,359
      pic 500,115,360
      pic 150,195,361
      pic 500,195,362
      pic 150,275,363
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Button's icons
      pic 150,115,364
      pic 500,115,365
      pic 150,195,366
      pic 500,195,367
      pic 150,275,368
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Button's icons
      pic 150,115,369
      pic 500,115,370
      pic 150,195,371
      pic 500,195,372
      pic 150,275,373
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Button's icons
      pic 150,115,374
      pic 500,115,375
      pic 150,195,376
      pic 500,195,377
      pic 150,275,378
    }
    //Nav Drawer icons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Pantalla"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Fecha/Hora"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Color del sistema"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Memoria"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Unidades"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Configuración"
    }else if(sys0==1)
    {
      //Italian
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Schermo"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Data/Ora"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Colore di sistema"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Memoria"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Unità"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Collocamento"
    }else if(sys0==2)
    {
      //French
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Écran"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Date/Heure"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Couleur du système"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Mémoire"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Unités"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Paramètre"
    }else if(sys0==3)
    {
      //English
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Display"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Date/Hour"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"System color"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Memory"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Units"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Settings"
    }else if(sys0==4)
    {
      //German
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Bildschirm"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Datum/Stunde"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Systemfarbe"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Speicher"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Einheiten"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Einstellung"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Tela"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Data/Hora"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Cor do sistema"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Memória"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Unidades"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Configuração"
    }
    //Page text end

Touch press event m0
--------------------

.. code-block:: javascript

    cirs 150,130,30,fondo
    cirs 390,130,30,fondo
    line 150,100,390,100,fondo
    line 150,160,390,160,fondo
    fill 150,100,240,60,fondo

Touch release event m0
----------------------

.. code-block:: javascript

    cirs 150,130,30,cbutton.val
    cirs 390,130,30,cbutton.val
    line 150,100,390,100,cbutton.val
    line 150,160,390,160,cbutton.val
    fill 150,100,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 150,115,349
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,115,354
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,115,359
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,115,364
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,115,369
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,115,374
    }
    //Page text start
    if(sys0==0)
    {
      //Buttons text
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Fecha/Hora"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Data/Ora"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Date/Heure"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Date/Hour"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Datum/Stunde"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Data/Hora"
    }
    //Page text end
    page Advertencia

Touch press event m1
--------------------

.. code-block:: javascript

    cirs 500,130,30,fondo
    cirs 740,130,30,fondo
    line 500,100,740,100,fondo
    line 500,160,740,160,fondo
    fill 500,100,240,60,fondo

Touch release event m1
----------------------

.. code-block:: javascript

    cirs 500,130,30,cbutton.val
    cirs 740,130,30,cbutton.val
    line 500,100,740,100,cbutton.val
    line 500,160,740,160,cbutton.val
    fill 500,100,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 500,115,350
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,115,355
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,115,360
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,115,365
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,115,370
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,115,375
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Color del sistema"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Colore di sistema"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Couleur du système"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"System color"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Systemfarbe"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Cor do sistema"
    }
    //Page text end
    page ColorS

Touch press event m2
--------------------

.. code-block:: javascript

    cirs 150,210,30,fondo
    cirs 390,210,30,fondo
    line 150,180,390,180,fondo
    line 150,240,390,240,fondo
    fill 150,180,240,60,fondo

Touch release event m2
----------------------

.. code-block:: javascript

    cirs 150,210,30,cbutton.val
    cirs 390,210,30,cbutton.val
    line 150,180,390,180,cbutton.val
    line 150,240,390,240,cbutton.val
    fill 150,180,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 150,195,351
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,195,356
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,195,361
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,195,366
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,195,371
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,195,376
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Memoria"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Memoria"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Mémoire"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Memory"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Reinigung"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Memória"
    }
    //Page text end
    page Memoria

Touch press event m3
--------------------

.. code-block:: javascript

    cirs 500,210,30,fondo
    cirs 740,210,30,fondo
    line 500,180,740,180,fondo
    line 500,240,740,240,fondo
    fill 500,180,240,60,fondo

Touch release event m3
----------------------

.. code-block:: javascript

    cirs 500,210,30,cbutton.val
    cirs 740,210,30,cbutton.val
    line 500,180,740,180,cbutton.val
    line 500,240,740,240,cbutton.val
    fill 500,180,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 500,195,352
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,195,357
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,195,362
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,195,367
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,195,372
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,195,377
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Unidades"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Unità"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Unités"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Units"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Einheiten"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Unidades"
    }
    //Page text end

Touch press event m4
--------------------

.. code-block:: javascript

    cirs 150,290,30,fondo
    cirs 390,290,30,fondo
    line 150,260,390,260,fondo
    line 390,320,390,320,fondo
    fill 150,260,240,60,fondo

Touch release event m4
----------------------

.. code-block:: javascript

    cirs 150,290,30,cbutton.val
    cirs 390,290,30,cbutton.val
    line 150,260,390,260,cbutton.val
    line 390,320,390,320,cbutton.val
    fill 150,260,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 150,275,353
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,275,358
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,275,363
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,275,368
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,275,373
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,275,378
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Configuración"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Collocamento"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Paramètre"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Settings"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Einstellung"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Configuração"
    }
    //Page text end
    page PConfig

Touch press event bInfoPa
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

Touch release event bInfoPa
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

Touch press event bHomePa
--------------------------

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

Touch release event bHomePa
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

Touch press event bBackPa
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

Touch release event bBackPa
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
    page MenuConf
    