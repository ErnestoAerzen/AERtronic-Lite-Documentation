EstadoModulo System Nextion Page
================================

Description
-----------

This script is designed for use with a Nextion display, a touchscreen interface commonly used in embedded projects. The script defines the layout and functionality of the display, including buttons, icons, and text elements.

Navigation Drawer
-----------------

The script begins by defining a navigation drawer with circular buttons (created using the `cirs` command). These buttons are positioned at specific coordinates and use the `color` variable for their appearance. Lines are drawn to connect the circular buttons, creating a visual separation. Additionally, rectangles are filled to form the background of the navigation drawer.

Page Title
----------

Following the navigation drawer, circular buttons are used to create a visually appealing page title. Lines are drawn to connect these buttons, and a rectangle is filled to create the background of the title area. The `color` variable is used for the appearance of these elements.

Page Containers
---------------

The script defines multiple page containers, each consisting of two circular buttons with connecting lines and filled rectangles. These containers are organized in a row. The `color` variable is used to specify the appearance of these elements. The multiple containers create a structured layout for the display.

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

The script checks the background color (`fondo`) and sets the font color (`fontColor.val`) accordingly. Depending on the background color, specific icons are displayed using the `pic` command. Each theme corresponds to a set of icons. Additionally, icons are positioned within the navigation drawer to provide visual representation.

Text Elements
-------------

Text elements are displayed on the screen based on the value of `sys0`, which likely represents the selected system language. Different text is displayed for various language settings. The `xstr` command is used to define text elements, including their position, font color, background color, and text content. The text elements include module names and status indicators.

Conclusion
-----------

This script defines the visual elements and interactivity of a Nextion display. It allows users to navigate through menus, view module names and statuses, and interact with buttons. The use of the `color` variable provides flexibility in customizing the appearance of elements. The script also accommodates multiple languages for text display, enhancing the user experience.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project it is used in.

Preinitialize event EstadoModulo
--------------------------------

.. code-block:: javascript

    // Changes the page's background color
    EstadoModulo.bco=fondo
    // Sends the current page number over serial
    sendme

Postinitialize event EstadoModulo
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
    //Page title start
    cirs 330,40,30,color
    cirs 520,40,30,color
    line 330,10,520,10,color
    line 330,70,520,70,color
    fill 330,10,190,60,color
    //Page title end
    //Page containers start
    //First container
    cirs 200,130,30,color
    cirs 700,130,30,color
    line 200,100,700,100,color
    line 200,160,700,160,color
    fill 200,100,500,60,color
    //Second container
    cirs 200,200,30,color
    cirs 700,200,30,color
    line 200,170,700,170,color
    line 200,230,700,230,color
    fill 200,170,500,60,color
    //Third container
    cirs 200,270,30,color
    cirs 700,270,30,color
    line 200,240,700,240,color
    line 200,300,700,300,color
    fill 200,240,500,60,color
    //Fourth container
    cirs 200,340,30,color
    cirs 700,340,30,color
    line 200,310,700,310,color
    line 200,370,700,370,color
    fill 200,310,500,60,color
    //Fifth container
    cirs 200,410,30,color
    cirs 700,410,30,color
    line 200,380,700,380,color
    line 200,440,700,440,color
    fill 200,380,500,60,color
    //Page container end
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
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Estado del módulo"
      xstr 360,117,150,25,0,fontColor.val,color,0,1,3,"Arranque"
      xstr 360,187,150,25,0,fontColor.val,color,0,1,3,"Paro"
      xstr 360,257,150,25,0,fontColor.val,color,0,1,3,"OK"
      xstr 360,327,150,25,0,fontColor.val,color,0,1,3,"Advertencia"
      xstr 360,397,150,25,0,fontColor.val,color,0,1,3,"Alarma"
    }else if(sys0==1)
    {
      //Italian
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Stato del modulo"
      xstr 360,117,150,25,0,fontColor.val,color,0,1,3,"Inizio"
      xstr 360,187,150,25,0,fontColor.val,color,0,1,3,"fermare"
      xstr 360,257,150,25,0,fontColor.val,color,0,1,3,"OK"
      xstr 360,327,150,25,0,fontColor.val,color,0,1,3,"Avvertimento"
      xstr 360,397,150,25,0,fontColor.val,color,0,1,3,"Allarme"
    }else if(sys0==2)
    {
      //French
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"État des modules"
      xstr 360,117,150,25,0,fontColor.val,color,0,1,3,"Début"
      xstr 360,187,150,25,0,fontColor.val,color,0,1,3,"Chômage"
      xstr 360,257,150,25,0,fontColor.val,color,0,1,3,"OK"
      xstr 360,327,150,25,0,fontColor.val,color,0,1,3,"Avertissement"
      xstr 360,397,150,25,0,fontColor.val,color,0,1,3,"Alarme"
    }else if(sys0==3)
    {
      //English
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Module status"
      xstr 360,117,150,25,0,fontColor.val,color,0,1,3,"Start"
      xstr 360,187,150,25,0,fontColor.val,color,0,1,3,"Stop"
      xstr 360,257,150,25,0,fontColor.val,color,0,1,3,"OK"
      xstr 360,327,150,25,0,fontColor.val,color,0,1,3,"Warning"
      xstr 360,397,150,25,0,fontColor.val,color,0,1,3,"Alarm"
    }else if(sys0==4)
    {
      //German
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Modulstatus"
      xstr 360,117,150,25,0,fontColor.val,color,0,1,3,"Anfang"
      xstr 360,187,150,25,0,fontColor.val,color,0,1,3,"Arbeitslosigkeit"
      xstr 360,257,150,25,0,fontColor.val,color,0,1,3,"OK"
      xstr 360,327,150,25,0,fontColor.val,color,0,1,3,"Vorbehalt"
      xstr 360,397,150,25,0,fontColor.val,color,0,1,3,"Alarm"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Status do módulo"
      xstr 360,117,150,25,0,fontColor.val,color,0,1,3,"Começar"
      xstr 360,187,150,25,0,fontColor.val,color,0,1,3,"Pare"
      xstr 360,257,150,25,0,fontColor.val,color,0,1,3,"OK"
      xstr 360,327,150,25,0,fontColor.val,color,0,1,3,"Advertência"
      xstr 360,397,150,25,0,fontColor.val,color,0,1,3,"Alarme"
    }
    //Page tiltle end
    //Name of module
    xstr 250,115,100,25,4,fontColor.val,65535,0,1,3,"A01-DI1"
    xstr 250,185,100,25,4,fontColor.val,65535,0,1,3,"A01-DI2"
    xstr 250,255,100,25,4,fontColor.val,65535,0,1,3,"A01-DO1"
    xstr 250,325,100,25,4,fontColor.val,65535,0,1,3,"A01-DO2"
    xstr 250,395,100,25,4,fontColor.val,65535,0,1,3,"A01-DO3"

Touch press event bInfoEM
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

Touch release event bInfoEM
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

Touch press event bHomeEM
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

Touch release event bHomeEM
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

Touch press event bBackEM
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

Touch release event bBackEM
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
    page Menu
    