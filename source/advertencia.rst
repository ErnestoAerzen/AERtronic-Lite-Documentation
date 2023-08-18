Advertencia Nextion page
=========================

Description
-------------------------------

The script provided below showcases the implementation of a Nextion display interface. The script is written in a special language tailored for Nextion displays and defines the appearance and behavior of various GUI elements. It uses a combination of commands to draw shapes, display icons, set colors, and present text on the screen.

This script is divided into several sections, each responsible for a specific aspect of the user interface:

Nav Drawer
----------

This section creates a navigation drawer with circular buttons and lines. The drawer provides a visually appealing menu system that users can interact with.

Page Title
----------

Here, a title bar is constructed at the top of the screen, enhancing the overall visual design of the interface.

Buttons
-------

This section defines circular buttons in two different color schemes, along with lines to separate them.

Nav Drawer Icons
----------------

Icons for the navigation drawer are presented here, with each set of icons corresponding to a specific theme chosen by the user. The theme is determined by a global variable.

Text
----

The script displays various text messages on the screen, which change based on the user's selected language. Additionally, the font color can be customized.

Global Variables
----------------

To understand the script better, it's essential to know about the following global variables:

- `color`: Determines the color of various elements on the screen.
- `fondo`: Represents the chosen theme for the icons.
- `sys0`: Defines the language of the displayed text.
- `fontColor.val`: Sets the color of the text font.

With these variables in mind, the script adapts its visual elements and messages based on the user's language preference and theme selection. It's important to note that this script is a part of a larger project and interacts with other components to provide a dynamic and user-friendly interface on the Nextion display.

Preinitialize event Advertencia
-------------------------------

.. code-block:: javascript

    // Changes the page's background color
    Advertencia.bco=fondo

Posinitialize event Advertencia
-------------------------------

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
    //Buttons start
    cirs 260,260,30,color
    cirs 400,260,30,color
    line 260,230,400,230,color
    line 260,290,400,290,color
    fill 260,230,140,60,color
    //
    cirs 480,260,30,0xB123
    cirs 620,260,30,0xB123
    line 480,230,620,230,0xB123
    line 480,290,620,290,0xB123
    fill 480,230,140,60,0xB123
    //Buttons end
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
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Modificar la hora y fecha reiniciará el sistema"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Fecha/Hora"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Reiniciar"
    }else if(sys0==1)
    {
      //Italian
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"La modifica dell'ora e della data riavvierà il sistema"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Data/Ora"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annulla"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Ricomincia"
    }else if(sys0==2)
    {
      //French
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Changer l'heure et la date redémarrera le système"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Date/Heure"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annuler"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Redémarrage"
    }else if(sys0==3)
    {
      //English
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Changing the time and date will reboot the system"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Date/Hour"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancel"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Reboot"
    }else if(sys0==4)
    {
      //German
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Durch das Ändern von Uhrzeit und Datum wird das System neu gestartet"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Datum/Stunde"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Stornieren"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Neu starten"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Alterar a hora e a data reiniciará o sistema"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Data/Hora"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Reiniciar"
    }

Touch press event m0
--------------------

.. code-block:: javascript

    cirs 260,260,30,fondo
    cirs 400,260,30,fondo
    line 260,230,400,230,fondo
    line 260,290,400,290,fondo
    fill 260,230,140,60,fondo

Touch release event m0
----------------------

.. code-block:: javascript

    cirs 260,260,30,color
    cirs 400,260,30,color
    line 260,230,400,230,color
    line 260,290,400,290,color
    fill 260,230,140,60,color
    if(sys0==0)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
    }else if(sys0==1)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annulla"
    }else if(sys0==2)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annuler"
    }else if(sys0==3)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancel"
    }else if(sys0==4)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Stornieren"
    }else if(sys0==5)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
    }
    page Pantalla

Touch press event m1
--------------------

.. code-block:: javascript

    cirs 480,260,30,fondo
    cirs 620,260,30,fondo
    line 480,230,620,230,fondo
    line 480,290,620,290,fondo
    fill 480,230,140,60,fondo
    //
    sendme

Touch release event m1
----------------------

.. code-block:: javascript

    cirs 480,260,30,0xB123
    cirs 620,260,30,0xB123
    line 480,230,620,230,0xB123
    line 480,290,620,290,0xB123
    fill 480,230,140,60,0xB123
    if(sys0==0)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminar"
    }else if(sys0==1)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminare"
    }else if(sys0==2)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Éliminer"
    }else if(sys0==3)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Delete"
    }else if(sys0==4)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Beseitigen"
    }else if(sys0==5)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminar"
    }
    delay=2000
    rest

Touch press event bInfoAd
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

Touch release event bInfoAd
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

Touch press event bHomeAd
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

Touch release event bHomeAd
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

Touch press event bBackAd
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

Touch release event bBackAd
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
    page Pantalla 