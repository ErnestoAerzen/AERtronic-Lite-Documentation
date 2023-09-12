Comunicacion Nextion Page
===================

Description
-----------

This script is designed to be used with a Nextion display, a touchscreen interface commonly used in embedded projects. It defines the layout and functionality of the display, including buttons, icons, and text elements.

Navigation Drawer
-----------------

The script begins by defining a navigation drawer, which typically contains circular buttons for menu navigation. It uses the `cirs` command to create circular buttons at specific coordinates, and the `line` command to connect them with lines. The `fill` command is then used to fill rectangles, creating the background of the navigation drawer.

Modbus Button
-------------

A button, likely related to Modbus functionality, is defined based on the value of `sys3`. Depending on whether `sys3` is 0 or 1, the button's appearance and color are adjusted accordingly.

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

The script checks the background color (`fondo`) and sets the font color accordingly. Depending on the background color, specific icons are displayed using the `pic` command. These icons correspond to different themes.

Page Title
----------

Circular buttons for the page title are defined, along with connecting lines. A rectangle is filled to create the background of the page title.

Page Text
~~~~~~~~~

The script displays text based on the value of `sys0`, which likely represents the selected system language. Depending on the language setting, different text is displayed in various languages. The text includes information about Modbus RTU and its status.

Conclusion
-----------

This script defines the visual elements and interactivity of a Nextion display. It allows users to navigate through menus, select themes, and interact with buttons related to Modbus functionality. The script also accommodates multiple languages for text display, enhancing the user experience.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project it is used in.

Preinitialize event Comunicacion
--------------------------------

.. code-block:: javascript

    // Changes the page's background color
    Comunicacion.bco=fondo
    // Sends the current page's id
    sendme

Postinitialize event Comunicacion
---------------------------------

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
    //Modbus button start
    if(sys3==0)
    {
      cirs 520,150,20,45347
      cirs 620,150,20,45347
      line 520,130,620,130,45347
      line 520,170,620,170,45347
      fill 520,130,100,40,45347
    }else if(sys3==1)
    {
      cirs 520,150,20,0x3B44
      cirs 620,150,20,0x3B44
      line 520,130,620,130,0x3B44
      line 520,170,620,170,0x3B44
      fill 520,130,100,40,0x3B44
    }
    //Modbus button end
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
    //Page title start
    cirs 300,40,30,color
    cirs 550,40,30,color
    line 300,10,550,10,color
    line 300,70,550,70,color
    fill 300,10,250,60,color
    //Page title end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Comunicación"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Habilitar Modbus RTU"
      xstr 140,240,350,25,7,fontColor.val,fondo,0,1,3,"Enviando data :"
      if(sys3==0)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"Off"
      }else if(sys3==1)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"On"
      }
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Comunicazione"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Abilita Modbus RTU"
      xstr 140,240,350,25,7,fontColor.val,fondo,0,1,3,"Invio dati :"
      if(sys3==0)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"Off"
      }else if(sys3==1)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"On"
      }
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Communication"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Activer Modbus RTU"
      xstr 140,240,350,25,7,fontColor.val,fondo,0,1,3,"Envoi de données :"
      if(sys3==0)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"Off"
      }else if(sys3==1)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"On"
      }
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Communication"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Enable Modbus RTU"
      xstr 140,240,350,25,7,fontColor.val,fondo,0,1,3,"Sending data :"
      if(sys3==0)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"Off"
      }else if(sys3==1)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"On"
      }
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Kommunikation"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Aktivieren Sie Modbus RTU"
      xstr 140,240,350,25,7,fontColor.val,fondo,0,1,3,"Senden von Daten :"
      if(sys3==0)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"Off"
      }else if(sys3==1)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"On"
      }
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Comunicação"
      xstr 140,140,350,25,7,fontColor.val,fondo,0,1,3,"Ativar Modbus RTU"
      xstr 140,240,350,25,7,fontColor.val,fondo,0,1,3,"Enviando dados :"
      if(sys3==0)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"Off"
      }else if(sys3==1)
      {
        xstr 520,140,100,25,6,65535,45347,1,1,3,"On"
      }
    }
    //Page text end

Touch release event m0
----------------------

.. code-block:: javascript

    if(sys3==0)
    {
      //Modbus button start
      cirs 520,150,20,0x3B44
      cirs 620,150,20,0x3B44
      line 520,130,620,130,0x3B44
      line 520,170,620,170,0x3B44
      fill 520,130,100,40,0x3B44
      //Modbus button end
      xstr 520,140,100,25,0,65535,45347,1,1,3,"On"
      //Activates Modbus RTU
      sys3=1
      //Sends command over Serial
      //Enables modbus rtu
      printh 4D F4 FF FF FF
    }else if(sys3==1)
    {
      //Modbus button start
      cirs 520,150,20,45347
      cirs 620,150,20,45347
      line 520,130,620,130,45347
      line 520,170,620,170,45347
      fill 520,130,100,40,45347
      //Modbus button end
      xstr 520,140,100,25,0,65535,45347,1,1,3,"Off"
      //Deactivates Modbus RTU
      sys3=0
      //Sends command over serial
      //Disables modbus rtu
      printh 4D F5 FF FF FF
    }

Touch press event bInfoCo
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

Touch release event bInfoCo
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

Touch press event bHomeCo
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

Touch release event bHomeCo
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

Touch press event bBackCo
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

Touch release event bBackCo
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
    page ControlSystem