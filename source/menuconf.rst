MenuConf Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script. The script is designed for controlling a Nextion display and creating a user interface with various elements, including circles, lines, buttons, icons, and text.

Script Overview
---------------

The provided script is intended for use with a Nextion display and is divided into several sections, each serving a specific purpose.

1. **Custom Button Color**
   - This line of code sets the color (cbutton.val) for various elements within the script.

2. **Nav Drawer**
   - This section creates a navigation drawer with circular buttons and lines to form a menu structure.

3. **Menu Buttons**
   - This section defines circular buttons used within the navigation drawer.
   - Each button consists of an outer circle, an inner circle, and lines forming a rectangular border.
   - Buttons are positioned in pairs.

4. **Page Title**
   - Two circular buttons at the top form a decorative element that serves as the page title.
   - Lines connect these circles to create a visually appealing header.

5. **Nav Drawer Icons**
   - This section checks the background color (fondo) and sets the font color accordingly.
   - Different themes are defined based on the background color.
   - Icons for buttons and menu items are placed at specific coordinates on the screen based on the selected theme.

6. **Language Selection**
   - Language selection is handled based on the value of sys0.
   - Text for menu items and buttons is defined in multiple languages (Spanish, Italian, French, English, German, Portuguese) based on the selected language.

Script Explanation
------------------

Now, let's provide a more detailed explanation of each section and its commands within the script:

1. **Custom Button Color**
   - This line of code sets the color for various elements within the script using the value of `cbutton.val`.

2. **Nav Drawer**
   - Four circular buttons (cirs) are created at specific coordinates with defined radii and colors.
   - Four lines (line) form a rectangular shape around the buttons, creating the appearance of a drawer.
   - Two filled rectangles (fill), one on top and one on the side, complete the visual representation of the navigation drawer.

3. **Menu Buttons**
   - Circular buttons (cirs) are created for the menu items.
   - Each button consists of two circles (outer and inner) and two lines forming a rectangular border.
   - Buttons are positioned in pairs, with two buttons in each pair.

4. **Page Title**
   - Two circular buttons (cirs) at the top form a decorative element that serves as the page title.
   - Lines (line) connect these circles to create a visually appealing header.
   - A filled rectangle (fill) adds a background color to the page title.

5. **Nav Drawer Icons**
   - This section checks the background color (fondo) and sets the font color accordingly (fontColor.val).
   - Different themes are defined based on the background color.
   - Icons (pic) for buttons and menu items are placed at specific coordinates on the screen based on the selected theme.

6. **Language Selection**
   - Language selection is handled based on the value of sys0.
   - Text (xstr) for menu items and buttons is defined in multiple languages (Spanish, Italian, French, English, German, Portuguese) based on the selected language.

Conclusion
----------

This documentation provides a comprehensive explanation of the Nextion display script, including its various sections, graphical elements, custom button colors, icon themes, and language support. Developers can use this script as a reference to create interactive user interfaces for Nextion displays, enhancing the user experience of their embedded systems.

Preinitialize event MenuConf
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    MenuConf.bco=fondo
    // Sets the main color of the buttons to `color`
    cbutton.val=color

Postinitialize event MenuConf
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
      pic 150,115,265
      pic 500,115,266
      pic 150,195,267
      pic 500,195,268
      pic 150,275,269
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Button's icons
      pic 150,115,270
      pic 500,115,271
      pic 150,195,272
      pic 500,195,273
      pic 150,275,274
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Button's icons
      pic 150,115,275
      pic 500,115,276
      pic 150,195,277
      pic 500,195,278
      pic 150,275,279
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Button's icons
      pic 150,115,280
      pic 500,115,281
      pic 150,195,282
      pic 500,195,283
      pic 150,275,284
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Button's icons
      pic 150,115,285
      pic 500,115,286
      pic 150,195,287
      pic 500,195,288
      pic 150,275,289
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Button's icons
      pic 150,115,290
      pic 500,115,291
      pic 150,195,292
      pic 500,195,293
      pic 150,275,294
    }
    //Nav Drawer icons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Configuración"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Sistema de control"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Parámetros de la maquina"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Servicio"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Valores Límite"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Pantalla"
    }else if(sys0==1)
    {
      //Italian
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Collocamento"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Sistema di controllo"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Parametri macchina"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Servizio"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Valori limite"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Schermo"
    }else if(sys0==2)
    {
      //French
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Paramètre"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Système de contrôle"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Paramètres machines"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Un service"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Valeurs limites"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Écran"
    }else if(sys0==3)
    {
      //English
      xstr 355,25,140,25,4,BLACK,color,1,1,3,"Settings"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Control system"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Machine parameters"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Service"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Limit values"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Display"
    }else if(sys0==4)
    {
      //German
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Einstellung"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Kontrollsystem"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Maschinenparameter"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Service"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Grenzwerte"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Bildschirm"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Configuração"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Sistema de controle"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Parâmetros da máquina"
      xstr 200,200,250,25,6,fontColor.val,color,0,1,3,"Serviço"
      xstr 550,200,250,25,6,fontColor.val,color,0,1,3,"Valores limite"
      xstr 200,280,250,25,6,fontColor.val,color,0,1,3,"Tela"
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
    //Theme starts
    if(fondo==65534)
    {
      //Theme 1
      pic 150,115,265
    }else if(fondo==63391)
    {
      //Theme 2
      pic 150,115,270
    }else if(fondo==65438)
    {
      //Theme 3
      pic 150,115,275
    }else if(fondo==63421)
    {
      //Theme 4
      pic 150,115,280
    }else if(fondo==6339)
    {
      //Theme 5
      pic 150,115,285
    }else if(fondo==8484)
    {
      //Theme 6
      pic 150,115,290
    }
    if(sys0==0)
    {
      //Spanish
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Sistema de control"
    }else if(sys0==1)
    {
      //Italian
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Sistema di controllo"
    }else if(sys0==2)
    {
      //French
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Système de contrôle"
    }else if(sys0==3)
    {
      //English
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Control system"
    }else if(sys0==4)
    {
      //German
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Kontrollsystem"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Sistema de controle"
    }
    //
    page ControlSystem

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
    //Theme starts
    if(fondo==65534)
    {
      //Theme 1
      pic 500,115,266
    }else if(fondo==63391)
    {
      //Theme 2
      pic 500,115,271
    }else if(fondo==65438)
    {
      //Theme 3
      pic 500,115,276
    }else if(fondo==63421)
    {
      //Theme 4
      pic 500,115,281
    }else if(fondo==6339)
    {
      //Theme 5
      pic 500,115,286
    }else if(fondo==8484)
    {
      //Theme 6
      pic 500,115,291
    }
    if(sys0==0)
    {
      //Spanish
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Parámetros de la maquina"
    }else if(sys0==1)
    {
      //Italian
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Parametri macchina"
    }else if(sys0==2)
    {
      //French
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Paramètres machines"
    }else if(sys0==3)
    {
      //English
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Machine parameters"
    }else if(sys0==4)
    {
      //German
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Maschinenparameter"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Parâmetros da máquina"
    }
    //
    page MachineParam

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
    //Theme starts
    if(fondo==65534)
    {
      //Theme 1
      pic 150,195,267
    }else if(fondo==63391)
    {
      //Theme 2
      pic 150,195,272
    }else if(fondo==65438)
    {
      //Theme 3
      pic 150,195,277
    }else if(fondo==63421)
    {
      //Theme 4
      pic 150,195,282
    }else if(fondo==6339)
    {
      //Theme 5
      pic 150,195,287
    }else if(fondo==8484)
    {
      //Theme 6
      pic 150,195,292
    }
    if(sys0==0)
    {
      //Spanish
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Servicio"
    }else if(sys0==1)
    {
      //Italian
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Servizio"
    }else if(sys0==2)
    {
      //French
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Un service"
    }else if(sys0==3)
    {
      //English
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Service"
    }else if(sys0==4)
    {
      //German
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Service"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 200,200,250,25,6,BLACK,color,0,1,3,"Serviço"
    }
    //
    page menuServicio

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
    //Theme starts
    if(fondo==65534)
    {
      //Theme 1
      pic 500,195,268
    }else if(fondo==63391)
    {
      //Theme 2
      pic 500,195,273
    }else if(fondo==65438)
    {
      //Theme 3
      pic 500,195,278
    }else if(fondo==63421)
    {
      //Theme 4
      pic 500,195,283
    }else if(fondo==6339)
    {
      //Theme 5
      pic 500,195,288
    }else if(fondo==8484)
    {
      //Theme 6
      pic 500,195,293
    }
    if(sys0==0)
    {
      //Spanish
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Valores Límite"
    }else if(sys0==1)
    {
      //Italian
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Valori limite"
    }else if(sys0==2)
    {
      //French
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Valeurs limites"
    }else if(sys0==3)
    {
      //English
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Limit values"
    }else if(sys0==4)
    {
      //German
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Grenzwerte"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 550,200,250,25,6,BLACK,color,0,1,3,"Valores limite"
    }
    page Limites

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
    //Theme starts
    if(fondo==65534)
    {
      //Theme 1
      pic 150,275,269
    }else if(fondo==63391)
    {
      //Theme 2
      pic 150,275,274
    }else if(fondo==65438)
    {
      //Theme 3
      pic 150,275,279
    }else if(fondo==63421)
    {
      //Theme 4
      pic 150,275,284
    }else if(fondo==6339)
    {
      //Theme 5
      pic 150,275,289
    }else if(fondo==8484)
    {
      //Theme 6
      pic 150,275,294
    }
    if(sys0==0)
    {
      //Spanish
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Pantalla"
    }else if(sys0==1)
    {
      //Italian
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Schermo"
    }else if(sys0==2)
    {
      //French
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Écran"
    }else if(sys0==3)
    {
      //English
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Display"
    }else if(sys0==4)
    {
      //German
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Bildschirm"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 200,280,250,25,6,BLACK,color,0,1,3,"Tela"
    }
    page Pantalla

Touch press event bInfoMC
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

Touch release event bInfoMC
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

Touch press event bHomeMC
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

Touch release event bHomeMC
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

Touch press event bBackMC
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

Touch release event bBackMC
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
    page InSesion

    
