menuServicio Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script that controls the appearance and functionality of a user interface with color-changing buttons, navigation drawers, menu buttons, page titles, and text localization. The script is written in the Nextion scripting language and aims to create an interactive and visually appealing user interface.

Script Overview
---------------

The script consists of several sections, each serving a specific purpose:

1. **Color-Changing Button**
   - The color of a button, represented by the `cbutton.val` variable, can be changed dynamically based on user interaction.
   - The button's appearance is defined using the `cbutton.val` variable.

2. **Navigation Drawer**
   - The navigation drawer section creates a user interface element with four circular icons, connecting lines, and filled rectangles. This section defines the layout of the navigation drawer.
   - Elements are positioned and styled using the `cirs`, `line`, and `fill` commands.

3. **Menu Buttons**
   - This section defines the appearance of six menu buttons, each consisting of two circular icons and connecting lines.
   - The color of these buttons is determined by the `cbutton.val` variable, allowing dynamic color changes.

4. **Page Title**
   - A page title section creates two circular icons and connecting lines to form a title bar for the active page.
   - Elements are positioned and styled using the `cirs` and `line` commands.

5. **Nav Drawer Icons**
   - This section determines the appearance of navigation icons within the navigation drawer based on the value of the `fondo` variable, representing the selected theme.
   - Each theme has a unique set of icon IDs and colors, and the selected theme is determined by the `fondo` value.

6. **Page Text**
   - Text elements are displayed on the page based on the value of the `sys0` variable, representing the selected language.
   - Text content and positioning are controlled using the `xstr` command, with different text for each language.

7. **Conclusion**
   - This section summarizes the script's functionality and explains how it creates an interactive user interface with dynamic color-changing buttons, navigation elements, and text localization.

Conclusion
----------

This documentation provides a comprehensive explanation of a Nextion display script that creates an interactive user interface with color-changing buttons, navigation drawers, menu buttons, page titles, and text localization. Developers can use this script as a foundation for building Nextion display projects with dynamic and visually appealing user interfaces, enhancing the overall user experience and interface design.

The provided script showcases how to create a responsive and customizable interface that adapts to user interactions, theme changes, and language preferences. By integrating these elements, developers can create versatile Nextion display applications with a polished look and user-friendly features.

Preinitialize event menuServicio
--------------------------------

.. code-block:: javascript

    // Changes the page's background color
    menuServicio.bco=fondo
    // Sets the buttons main color to `color` value
    cbutton.val=color
    // Custom command see README.md file for more details.
    printh 52 FE FF FF FF

Postinitialize event menuServicio
----------------------------------

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
    line 150,320,390,320,cbutton.val
    fill 150,260,240,60,cbutton.val
    //Sixth button
    cirs 500,290,30,cbutton.val
    cirs 740,290,30,cbutton.val
    line 500,260,740,260,cbutton.val
    line 500,320,740,320,cbutton.val
    fill 500,260,240,60,cbutton.val
    //Seventh button
    cirs 150,370,30,cbutton.val
    cirs 390,370,30,cbutton.val
    line 150,340,390,340,cbutton.val
    line 150,400,390,400,cbutton.val
    fill 150,340,240,60,cbutton.val
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
      pic 150,115,307
      pic 500,115,308
      pic 150,195,309
      pic 500,195,310
      pic 150,275,311
      pic 500,275,312
      pic 150,355,313
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Button's icons
      pic 150,115,314
      pic 500,115,315
      pic 150,195,316
      pic 500,195,317
      pic 150,275,318
      pic 500,275,319
      pic 150,355,320
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Button's icons
      pic 150,115,321
      pic 500,115,322
      pic 150,195,323
      pic 500,195,324
      pic 150,275,325
      pic 500,275,326
      pic 150,355,327
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Button's icons
      pic 150,115,328
      pic 500,115,329
      pic 150,195,330
      pic 500,195,331
      pic 150,275,332
      pic 500,275,333
      pic 150,355,334
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Button's icons
      pic 150,115,335
      pic 500,115,336
      pic 150,195,337
      pic 500,195,338
      pic 150,275,339
      pic 500,275,340
      pic 150,355,341
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Button's icons
      pic 150,115,342
      pic 500,115,343
      pic 150,195,344
      pic 500,195,345
      pic 150,275,346
      pic 500,275,347
      pic 150,355,348
    }
    //Nav Drawer icons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 335,25,170,25,4,fontColor.val,color,1,1,3,"Menú de servicio"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Intervalos de mantenimiento"
      xstr 550,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Información de la versión"
      xstr 200,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Registro de eventos"
      xstr 550,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Datos de la máquina"
      xstr 200,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Confirmar mantenimientos"
      xstr 550,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Contador de horas"
      xstr 200,360,250,25,6,fontColor.val,cbutton.val,0,1,3,"Configuración de fabrica"
    }else if(sys0==1)
    {
      //Italian
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Menù di servizio"
      //Buttons text
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Intervalli di manutenzione"
      xstr 550,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Informazioni sulla versione"
      xstr 200,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Registro eventi"
      xstr 550,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Dati macchina"
      xstr 200,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Confermare la manutenzione"
      xstr 550,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Contaore"
      xstr 200,360,250,25,6,fontColor.val,cbutton.val,0,1,3,"Impostazioni di fabbrica"
    }else if(sys0==2)
    {
      //French
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Menu des services"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Intervalles d'entretien"
      xstr 550,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Information sur la version"
      xstr 200,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Journal des événements"
      xstr 550,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Données machine"
      xstr 200,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Confirmer l'entretien"
      xstr 550,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Compteur horaire"
      xstr 200,360,250,25,6,fontColor.val,cbutton.val,0,1,3,"Réglages d'usine"
    }else if(sys0==3)
    {
      //English
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Service menu"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Maintenance intervals"
      xstr 550,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Version Information"
      xstr 200,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Event log"
      xstr 550,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Machine data"
      xstr 200,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Confirm maintenance"
      xstr 550,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Hour meter"
      xstr 200,360,250,25,6,fontColor.val,cbutton.val,0,1,3,"Factory settings"
    }else if(sys0==4)
    {
      //German
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Service-Menü"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Wartungsintervalle"
      xstr 550,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Versionsinformation"
      xstr 200,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Ereignisprotokoll"
      xstr 550,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Maschinendaten"
      xstr 200,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Wartung bestätigen"
      xstr 550,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Stundenzähler"
      xstr 200,360,250,25,6,fontColor.val,cbutton.val,0,1,3,"Werkseinstellungen"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Menu de serviço"
      //Buttons text
      xstr 200,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Intervalos de mantenimiento"
      xstr 550,120,250,25,6,fontColor.val,cbutton.val,0,1,3,"Información de la versión"
      xstr 200,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Registro de eventos"
      xstr 550,200,250,25,6,fontColor.val,cbutton.val,0,1,3,"Datos de la maquina"
      xstr 200,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Confirmar mantenimientos"
      xstr 550,280,250,25,6,fontColor.val,cbutton.val,0,1,3,"Contador de horas"
      xstr 200,360,250,25,6,fontColor.val,cbutton.val,0,1,3,"Configuración de fabrica"
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
      pic 150,115,307
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,115,314
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,115,321
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,115,328
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,115,335
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,115,342
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 200,120,250,25,6,BLACK,cbutton.val,0,1,3,"Intervalos de mantenimiento"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,120,250,25,6,BLACK,cbutton.val,0,1,3,"Intervalli di manutenzione"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,120,250,25,6,BLACK,cbutton.val,0,1,3,"Intervalles d'entretien"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,120,250,25,6,BLACK,cbutton.val,0,1,3,"Maintenance intervals"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,120,250,25,6,BLACK,cbutton.val,0,1,3,"Wartungsintervalle"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,120,250,25,6,BLACK,cbutton.val,0,1,3,"Intervalos de mantenimiento"
    }
    //Page text end
    page ResetMant

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
      pic 500,115,308
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,115,315
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,115,322
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,115,329
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,115,336
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,115,343
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 550,120,250,25,6,BLACK,cbutton.val,0,1,3,"Información de la versión"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 550,120,250,25,6,BLACK,cbutton.val,0,1,3,"Informazioni sulla versione"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 550,120,250,25,6,BLACK,cbutton.val,0,1,3,"Information sur la version"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 550,120,250,25,6,BLACK,cbutton.val,0,1,3,"Version Information"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 550,120,250,25,6,BLACK,cbutton.val,0,1,3,"Versionsinformation"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 550,120,250,25,6,BLACK,cbutton.val,0,1,3,"Información de la versión"
    }
    //Page text end

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
      pic 150,195,309
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,195,316
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,195,323
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,195,330
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,195,337
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,195,344
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 200,200,250,25,6,BLACK,cbutton.val,0,1,3,"Registro de eventos"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,200,250,25,6,BLACK,cbutton.val,0,1,3,"Registro eventi"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,200,250,25,6,BLACK,cbutton.val,0,1,3,"Journal des événements"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,200,250,25,6,BLACK,cbutton.val,0,1,3,"Event log"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,200,250,25,6,BLACK,cbutton.val,0,1,3,"Ereignisprotokoll"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,200,250,25,6,BLACK,cbutton.val,0,1,3,"Registro de eventos"
    }
    //Page text end
    page Eventos1

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
      pic 500,195,310
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,195,317
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,195,324
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,195,331
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,195,338
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,195,345
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 550,200,250,25,6,BLACK,cbutton.val,0,1,3,"Datos de la máquina"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 550,200,250,25,6,BLACK,cbutton.val,0,1,3,"Dati macchina"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 550,200,250,25,6,BLACK,cbutton.val,0,1,3,"Données machine"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 550,200,250,25,6,BLACK,cbutton.val,0,1,3,"Machine data"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 550,200,250,25,6,BLACK,cbutton.val,0,1,3,"Maschinendaten"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 550,200,250,25,6,BLACK,cbutton.val,0,1,3,"Datos de la maquina"
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
      pic 150,275,311
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,275,318
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,275,325
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,275,332
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,275,339
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,275,346
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 200,280,250,25,6,BLACK,cbutton.val,0,1,3,"Confirmar mantenimientos"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,280,250,25,6,BLACK,cbutton.val,0,1,3,"Confermare la manutenzione"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,280,250,25,6,BLACK,cbutton.val,0,1,3,"Confirmer l'entretien"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,280,250,25,6,BLACK,cbutton.val,0,1,3,"Confirm maintenance"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,280,250,25,6,BLACK,cbutton.val,0,1,3,"Wartung bestätigen"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,280,250,25,6,BLACK,cbutton.val,0,1,3,"Confirmar mantenimientos"
    }
    //Page text end
    page ConfirmarM

Touch press event m5
--------------------

.. code-block:: javascript

    cirs 500,290,30,fondo
    cirs 740,290,30,fondo
    line 500,260,740,260,fondo
    line 500,320,740,320,fondo
    fill 500,260,240,60,fondo

Touch release event m5
----------------------

.. code-block:: javascript

    cirs 500,290,30,cbutton.val
    cirs 740,290,30,cbutton.val
    line 500,260,740,260,cbutton.val
    line 500,320,740,320,cbutton.val
    fill 500,260,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 500,275,312
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 500,275,319
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 500,275,326
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 500,275,333
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 500,275,340
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 500,275,347
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 550,280,250,25,6,BLACK,cbutton.val,0,1,3,"Contador de horas"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 550,280,250,25,6,BLACK,cbutton.val,0,1,3,"Contaore"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 550,280,250,25,6,BLACK,cbutton.val,0,1,3,"Compteur horaire"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 550,280,250,25,6,BLACK,cbutton.val,0,1,3,"Hour meter"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 550,280,250,25,6,BLACK,cbutton.val,0,1,3,"Stundenzähler"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 550,280,250,25,6,BLACK,cbutton.val,0,1,3,"Contador de horas"
    }
    //Page text end
    page Contador

Touch press event m6
--------------------

.. code-block:: javascript

    cirs 150,370,30,fondo
    cirs 390,370,30,fondo
    line 150,340,390,340,fondo
    line 150,400,390,400,fondo
    fill 150,340,240,60,fondo

Touch release event m6
----------------------

.. code-block:: javascript

    cirs 150,370,30,cbutton.val
    cirs 390,370,30,cbutton.val
    line 150,340,390,340,cbutton.val
    line 150,400,390,400,cbutton.val
    fill 150,340,240,60,cbutton.val
    if(fondo==65534)
    {
      //Buttons icons
      pic 150,355,313
    }else if(fondo==63391)
    {
      //Buttons icons
      pic 150,355,320
    }else if(fondo==65438)
    {
      //Buttons icons
      pic 150,355,327
    }else if(fondo==63421)
    {
      //Buttons icons
      pic 150,355,334
    }else if(fondo==6339)
    {
      //Buttons icons
      pic 150,355,341
    }else if(fondo==8484)
    {
      //Buttons icons
      pic 150,355,348
    }
    //Page text start
    if(sys0==0)
    {
      //Spanish
      //Buttons text
      xstr 200,360,250,25,6,BLACK,cbutton.val,0,1,3,"Configuración de fabrica"
    }else if(sys0==1)
    {
      //Italian
      //Buttons text
      xstr 200,360,250,25,6,BLACK,cbutton.val,0,1,3,"Impostazioni di fabbrica"
    }else if(sys0==2)
    {
      //French
      //Buttons text
      xstr 200,360,250,25,6,BLACK,cbutton.val,0,1,3,"Réglages d'usine"
    }else if(sys0==3)
    {
      //English
      //Buttons text
      xstr 200,360,250,25,6,BLACK,cbutton.val,0,1,3,"Factory settings"
    }else if(sys0==4)
    {
      //German
      //Buttons text
      xstr 200,360,250,25,6,BLACK,cbutton.val,0,1,3,"Werkseinstellungen"
    }else if(sys0==5)
    {
      //Portuguese
      //Buttons text
      xstr 200,360,250,25,6,BLACK,cbutton.val,0,1,3,"Configuración de fabrica"
    }
    //Page text end
    page ResetEv

Touch press event bInfoMS
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
    Info.returnPage.val=dp

Touch release event bInfoMS
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

Touch press event bHomeMS
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

Touch release event bHomeMS
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

Touch press event bBackMS
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

Touch release event bBackMS
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