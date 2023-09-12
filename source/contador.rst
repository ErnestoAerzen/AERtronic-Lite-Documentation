Contador Nextion Page
=====================

Description
-----------

This script is designed for use with a Nextion display, a touchscreen interface commonly used in embedded projects. The script defines the layout and functionality of the display, including buttons, icons, and text elements.

Navigation Drawer
-----------------

The script starts by defining a navigation drawer using circular buttons (created with the `cirs` command) to facilitate menu navigation. Lines are drawn to connect the circular buttons, and rectangles are filled to create the background of the navigation drawer.

Page Title
----------

Circular buttons are used to create a visually appealing page title. Lines are drawn to connect these buttons, and a rectangle is filled to form the background of the page title.

Buttons
-------

Two sets of buttons are defined on the display. The first set consists of circular buttons with a solid color, while the second set uses a different color (`0xB123`) for its circular buttons. Lines are drawn to define the boundaries of these buttons, and rectangles are filled to create their appearance.

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

The script checks the background color (`fondo`) and sets the font color accordingly. Depending on the background color, specific icons are displayed using the `pic` command. Each theme corresponds to a set of icons.

Text
~~~~

Text elements are displayed on the screen based on the value of `sys0`, likely representing the selected system language. Different text is displayed for various language settings, including messages related to resetting operation hours counters.

Conclusion
-----------

This script defines the visual elements and interactivity of a Nextion display. It allows users to navigate through menus, select themes, and interact with buttons for resetting operation hours counters. The script also accommodates multiple languages for text display, enhancing the user experience.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project it is used in.

Preinitialize event Contador
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Contador.bco=fondo

Postinitialize event Contador
-----------------------------

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
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Reiniciar el contador de horas de operación"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Reiniciar contador"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Reiniciar"
    }else if(sys0==1)
    {
      //Italian
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Azzerare il contatore delle ore di funzionamento"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Azzerare il contatore"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annulla"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Ricomincia"
    }else if(sys0==2)
    {
      //French
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Remise à zéro du compteur d'heures de fonctionnement"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Réinitialiser le compteur"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annuler"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Redémarrage"
    }else if(sys0==3)
    {
      //English
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Reset the operation hours counter"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Reset counter"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancel"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Reboot"
    }else if(sys0==4)
    {
      //German
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Betriebsstundenzähler zurücksetzen"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Zähler zurücksetzen"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Stornieren"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Neu starten"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Redefinir o contador de horas de operação"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Reiniciar contador"
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
    page menuServicio

Touch press event m1
--------------------

.. code-block:: javascript

    cirs 480,260,30,fondo
    cirs 620,260,30,fondo
    line 480,230,620,230,fondo
    line 480,290,620,290,fondo
    fill 480,230,140,60,fondo
    //
    prints "ResetContador",0

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
    //Reset counter command
    printh 43 F3 FF FF FF

Touch press event bInfoC
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

Touch release event bInfoC
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

Touch press event bHomeC
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

Touch release event bHomeC
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

Touch press event bBackC
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

Touch release event bBackC
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
    page menuServicio
