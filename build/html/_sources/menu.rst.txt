Menu Nextion Page
============================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script. The script is designed for controlling a Nextion display and creating a user interface with various elements, including circles, lines, and text.

Script Overview
---------------

The provided script is intended for use with a Nextion display and is divided into several sections, each serving a specific purpose.

1. **Nav Drawer**
   - This section creates a navigation drawer with circular buttons and lines to form a menu structure.

2. **Menu Buttons**
   - This section defines circular buttons used within the navigation drawer.

3. **Page Title**
   - This part sets up a circular button-based page title.

4. **Nav Drawer Icons**
   - Icons within the navigation drawer are defined based on the selected theme and color scheme.

5. **Language Selection**
   - The script handles language selection, with corresponding text for buttons and menus based on the chosen language.

Script Explanation
------------------

Now, let's provide a more detailed explanation of each section and its commands within the script:

1. **Nav Drawer**
   - Four circles (circular buttons) are created at specific coordinates with defined radii and colors.
   - Four lines form a rectangular shape around the buttons, creating the appearance of a drawer.
   - Two filled rectangles, one on top and one on the side, complete the visual representation of the navigation drawer.

2. **Menu Buttons**
   - Circular buttons are created for the menu items.
   - Each button consists of two circles (outer and inner) and two lines forming a rectangular border.
   - The buttons are positioned in pairs, with two buttons in each pair.

3. **Page Title**
   - Two circular buttons at the top form a decorative element that serves as the page title.
   - Lines connect these circles to create a visually appealing header.

4. **Nav Drawer Icons**
   - This section checks the background color (fondo) and sets the font color accordingly.
   - Different themes are defined based on the background color.
   - Icons for buttons and menu items are placed at specific coordinates on the screen based on the selected theme.

5. **Language Selection**
   - Language selection is handled based on the value of sys0.
   - Text for menu items and buttons is defined in multiple languages (Spanish, Italian, French, English, German, Portuguese) based on the selected language.

Conclusion
----------
This documentation provides a comprehensive explanation of the Nextion display script, including its various sections, graphical elements, and language handling. By understanding this script, developers can create interactive user interfaces with language support for Nextion displays, enhancing the user experience of their embedded systems.

Preinitialize event Menu
------------------------

.. code-block:: javascript

    // Changes the page's background color
    Menu.bco=fondo
    // Applies 'color' to the button's main color
    cbutton.val=color
    // Custom command. See more in the README.md file
    printh 52 FE FF FF FF

Postinitialize event Menu
-------------------------

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
    //Menu buttons start
    //First button
    cirs 150,130,30,color
    cirs 390,130,30,color
    line 150,100,390,100,color
    line 150,160,390,160,color
    fill 150,100,240,60,color
    //Second button
    cirs 500,130,30,color
    cirs 740,130,30,color
    line 500,100,740,100,color
    line 500,160,740,160,color
    fill 500,100,240,60,color
    //Third button
    cirs 150,210,30,color
    cirs 390,210,30,color
    line 150,180,390,180,color
    line 150,240,390,240,color
    fill 150,180,240,60,color
    //Fourth button
    cirs 500,210,30,color
    cirs 740,210,30,color
    line 500,180,740,180,color
    line 500,240,740,240,color
    fill 500,180,240,60,color
    //Fifth button
    cirs 150,290,30,color
    cirs 390,290,30,color
    line 150,260,390,260,color
    line 390,320,390,320,color
    fill 150,260,240,60,color
    //Menu buttons end
    //Page title start
    cirs 380,40,30,color
    cirs 520,40,30,color
    line 380,10,520,10,color
    line 380,70,520,70,color
    fill 380,10,140,60,color
    //Nav Drawer icons start
    if(fondo==65534)
    {
      //Font color
      fontColor.val=0
      //Theme 1
      pic 25,30,78
      pic 25,120,144
      pic 25,400,146
      //Buttons icons
      pic 150,115,181
      pic 500,115,182
      pic 150,195,183
      pic 500,195,184
      pic 150,275,185
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Buttons icons
      pic 150,115,186
      pic 500,115,187
      pic 150,195,188
      pic 500,195,189
      pic 150,275,190
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Buttons icons
      pic 150,115,191
      pic 500,115,192
      pic 150,195,193
      pic 500,195,194
      pic 150,275,195
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Buttons icons
      pic 150,115,196
      pic 500,115,197
      pic 150,195,198
      pic 500,195,199
      pic 150,275,200
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Buttons icons
      pic 150,115,201
      pic 500,115,202
      pic 150,195,203
      pic 500,195,204
      pic 150,275,205
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Buttons icons
      pic 150,115,206
      pic 500,115,207
      pic 150,195,208
      pic 500,195,209
      pic 150,275,210
    }
    //Nav Drawer icons end
    if(sys0==0)
    {
      //Spanish
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Menú"
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Estado del módulo"
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalos de servicio"
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Tiempo de operación"
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Idiomas"
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Configuración"
    }else if(sys0==1)
    {
      //Italian
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Menù"
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Stato del modulo"
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalli di servizio"
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Tempo di funzionamento"
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Le lingue"
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Collocamento"
    }else if(sys0==2)
    {
      //French
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Menu"
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"État des modules"
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalles d'entretien"
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Moment de l'opération"
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Langues"
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Paramètre"
    }else if(sys0==3)
    {
      //English
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Menu"
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Module status"
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Service intervals"
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Operation time"
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Languages"
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Settings"
    }else if(sys0==4)
    {
      //German
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Menü"
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Modulstatus"
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Wartungsintervalle"
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Betriebszeit"
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Sprachen"
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Einstellung"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Menu"
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Status do módulo"
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalos de serviço"
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Tempo de operação"
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Línguas"
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Configuração"
    }

Touch press event m0
--------------------

.. code-block:: javascript

    // Pressed button effect
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
      pic 150,115,181
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,115,186
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,115,191
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,115,196
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,115,201
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,115,206
    }
    //Nav Drawer icons end
    if(sys0==0)
    {
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Estado del módulo"
    }else if(sys0==1)
    {
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Stato del modulo"
    }else if(sys0==2)
    {
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"État des modules"
    }else if(sys0==3)
    {
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Module status"
    }else if(sys0==4)
    {
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Modulstatus"
    }else if(sys0==5)
    {
      //Buttons text
      xstr 190,120,250,25,0,fontColor.val,color,0,1,3,"Status do módulo"
    }
    page EstadoModulo

Touch press event m1
--------------------

.. code-block:: javascript

    // Pressed button effect
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
      pic 500,115,182
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,115,187
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,115,192
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,115,197
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,115,202
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,115,207
    }
    //Nav Drawer icons end
    if(sys0==0)
    {
      //Buttons text
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalos de servicio"
    }else if(sys0==1)
    {
      //Buttons text
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalli di servizio"
    }else if(sys0==2)
    {
      //Buttons text
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalles d'entretien"
    }else if(sys0==3)
    {
      //Buttons text
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Service intervals"
    }else if(sys0==4)
    {
      //Buttons text
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Wartungsintervalle"
    }else if(sys0==5)
    {
      //Buttons text
      xstr 540,120,250,25,0,fontColor.val,color,0,1,3,"Intervalos de serviço"
    }
    page Intervalos

Touch press event m2
--------------------

.. code-block:: javascript

    // Pressed button effect
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
      pic 150,195,183
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,195,188
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,195,193
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,195,198
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,195,203
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,195,208
    }
    //Nav Drawer icons end
    if(sys0==0)
    {
      //Buttons text
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Tiempo de operación"
    }else if(sys0==1)
    {
      //Buttons text
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Tempo di funzionamento"
    }else if(sys0==2)
    {
      //Buttons text
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Moment de l'opération"
    }else if(sys0==3)
    {
      //Buttons text
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Operation time"
    }else if(sys0==4)
    {
      //Buttons text
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Betriebszeit"
    }else if(sys0==5)
    {
      //Buttons text
      xstr 190,200,250,25,0,fontColor.val,color,0,1,3,"Tempo de operação"
    }
    page Tiempos

Touch press event m3
--------------------

.. code-block:: javascript

    // Pressed button effect
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
      pic 500,195,184
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,195,189
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,195,194
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,195,199
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,195,204
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,195,209
    }
    //Nav Drawer icons end
    if(sys0==0)
    {
      //Buttons text
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Idiomas"
    }else if(sys0==1)
    {
      //Buttons text
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Le lingue"
    }else if(sys0==2)
    {
      //Buttons text
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Langues"
    }else if(sys0==3)
    {
      //Buttons text
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Languages"
    }else if(sys0==4)
    {
      //Buttons text
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Sprachen"
    }else if(sys0==5)
    {
      //Buttons text
      xstr 540,200,250,25,0,fontColor.val,color,0,1,3,"Línguas"
    }
    page Idiomas

Touch press event m4
--------------------

.. code-block:: javascript

    // Pressed button effect
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
      pic 150,275,185
    }else if(fondo==63391)
    {
      pic 150,275,190
    }else if(fondo==65438)
    {
      pic 150,275,195
    }else if(fondo==63421)
    {
      pic 150,275,200
    }else if(fondo==6339)
    {
      pic 150,275,205
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,275,210
    }
    //Nav Drawer icons end
    if(sys0==0)
    {
      //Buttons text
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Configuración"
    }else if(sys0==1)
    {
      //Buttons text
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Collocamento"
    }else if(sys0==2)
    {
      //Buttons text
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Paramètre"
    }else if(sys0==3)
    {
      //Buttons text
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Settings"
    }else if(sys0==4)
    {
      //Buttons text
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Einstellung"
    }else if(sys0==5)
    {
      //Buttons text
      xstr 190,280,250,25,0,fontColor.val,color,0,1,3,"Configuração"
    }
    //
    page InSesion

Touch press event bInfoM
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

Touch release event bInfoM
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

Touch press event bHomeM
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

Touch release event bHomeM
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

Touch press event bBackM
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

Touch release event bBackM
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
    page Home
