ConfirmarM Nextion Page
===================

Description
-----------

This script is designed for use with a Nextion display, a touchscreen interface commonly used in embedded projects. The script defines the layout and functionality of the display, including buttons, icons, and text elements.

Navigation Drawer
-----------------

The script starts by defining a navigation drawer using circular buttons (created with the `cirs` command) to facilitate menu navigation. Lines are drawn to connect the circular buttons, and rectangles are filled to create the background of the navigation drawer.

Page Title
----------

Circular buttons are used to create a visually appealing page title. Lines are drawn to connect these buttons, and a rectangle is filled to form the background of the page title.

First Button
------------

A button is defined using circular shapes (`cirs`), and lines are drawn to delineate its boundaries. The button's appearance and color are determined by the value of `sys3`. If `sys3` equals 0, the button is labeled "Off"; if it equals 1, the label is "On."

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

The script checks the background color (`fondo`) and sets the font color accordingly. Depending on the background color, specific icons are displayed using the `pic` command. Each theme corresponds to a set of icons.

Page Text
~~~~~~~~~

Text is displayed based on the value of `sys0`, likely representing the selected system language. Different text is displayed for various language settings, including messages related to confirming maintenance.

Conclusion
-----------

This script defines the visual elements and interactivity of a Nextion display. It allows users to navigate through menus, select themes, and interact with buttons that confirm or deny maintenance actions. The script also accommodates multiple languages for text display, enhancing the user experience.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project it is used in.

Preinitialize event ConfirmarM
------------------------------

.. code-block:: javascript

    // Changes the page's background color
    ConfirmarM.bco=fondo
    // Sends the current page's id over serial
    sendme

Postinitialize event ConfirmarM
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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Confirmar"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Confirmar mantenimiento"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirmar"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Confermare"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Confermare la manutenzione"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confermare"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Confirmer"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Confirmer l'entretien"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirmer"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Confirm"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Confirm maintenance"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirm"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Bestätigen"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Wartung bestätigen"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Bestätigen"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Confirme"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Confirmar manutenção"
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirme"
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
    printh 43 EF FF FF FF

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
      xstr 520,140,100,25,6,65535,45347,1,1,3,"Confirmar"
    }else if(sys0==1)
    {
      //Italian
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confermare"
    }else if(sys0==2)
    {
      //French
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirmer"
    }else if(sys0==3)
    {
      //English
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirm"
    }else if(sys0==4)
    {
      //German
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Bestätigen"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Confirme"
    }

Touch press event bInfoCM
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

Touch release event bInfoCM
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

Touch press event bHomeCM
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

Touch release event bHomeCM
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

Touch press event bBackCM
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

Touch release event bBackCM
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

