ControlSystem Nextion Page
==========================

Description
-----------

This script is designed for use with a Nextion display, a touchscreen interface commonly used in embedded projects. The script defines the layout and functionality of the display, including buttons, icons, and text elements.

Color Variable
--------------

The script uses a color variable `cbutton.val` to specify the color for certain elements throughout the display. This variable allows for dynamic color changes based on user interaction or system state.

Navigation Drawer
-----------------

The script starts by defining a navigation drawer using circular buttons (created with the `cirs` command). These buttons are positioned at specific coordinates and use the color variable `color` for their appearance. Lines are drawn to connect the circular buttons, and rectangles are filled to create the background of the navigation drawer.

Menu Buttons
------------

The script defines two sets of menu buttons. Each set consists of two circular buttons created with the `cirs` command. The color for these buttons is specified using the `cbutton.val` variable. Lines are drawn to outline the buttons, and rectangles are filled to give them a distinct appearance. This approach allows for flexibility in changing button colors.

Page Title
----------

Circular buttons are used to create a visually appealing page title. Lines are drawn to connect these buttons, and a rectangle is filled to form the background of the page title. The color for these elements is specified using the `color` variable.

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

The script checks the background color (`fondo`) and sets the font color (`fontColor.val`) accordingly. Depending on the background color, specific icons are displayed using the `pic` command. Each theme corresponds to a set of icons. Additionally, icons are positioned within the menu buttons to provide visual representation.

Text
~~~~

Text elements are displayed on the screen based on the value of `sys0`, likely representing the selected system language. Different text is displayed for various language settings. The `xstr` command is used to define text elements, including their position, font color, background color, and text content.

Conclusion
-----------

This script defines the visual elements and interactivity of a Nextion display. It allows users to navigate through menus, select themes, and interact with buttons. The color variable (`cbutton.val`) provides flexibility in customizing the appearance of elements. The script also accommodates multiple languages for text display, enhancing the user experience.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project it is used in.

Preinitialize event ControlSystem
---------------------------------

.. code-block:: javascript

    ControlSystem.bco=fondo
    cbutton.val=color


    printh 52 FE FF FF FF

Postinitialize event ControlSystem
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
      pic 150,115,295
      pic 500,115,296
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Button's icons
      pic 150,115,297
      pic 500,115,298
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Button's icons
      pic 150,115,299
      pic 500,115,300
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Button's icons
      pic 150,115,301
      pic 500,115,302
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Button's icons
      pic 150,115,303
      pic 500,115,304
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Button's icons
      pic 150,115,305
      pic 500,115,306
    }
    //Nav Drawer icons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Sistema de control"
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Misceláneos"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Comunicación"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Sistema di controllo"
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Varie"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Comunicazione"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Système de contrôle"
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Divers"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Communication"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Control system"
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Miscellaneous"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Communication"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Kontrollsystem"
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Verschiedenes"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Kommunikation"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Sistema de controle"
      xstr 200,120,250,25,6,fontColor.val,color,0,1,3,"Diversos"
      xstr 550,120,250,25,6,fontColor.val,color,0,1,3,"Comunicação"
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
      pic 150,115,295
    }else if(fondo==63391)
    {
      //Theme 2
      pic 150,115,297
    }else if(fondo==65438)
    {
      //Theme 3
      pic 150,115,299
    }else if(fondo==63421)
    {
      //Theme 4
      pic 150,115,301
    }else if(fondo==6339)
    {
      //Theme 5
      pic 150,115,303
    }else if(fondo==8484)
    {
      //Theme 6
      pic 150,115,305
    }
    //Text
    if(sys0==0)
    {
      //Spanish
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Misceláneos"
    }else if(sys0==1)
    {
      //Italian
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Varie"
    }else if(sys0==2)
    {
      //French
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Divers"
    }else if(sys0==3)
    {
      //English
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Miscellaneous"
    }else if(sys0==4)
    {
      //German
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Verschiedenes"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 200,120,250,25,6,BLACK,color,0,1,3,"Diversos"
    }
    //
    page Varios

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
      pic 500,115,296
    }else if(fondo==63391)
    {
      //Theme 2
      pic 500,115,298
    }else if(fondo==65438)
    {
      //Theme 3
      pic 500,115,300
    }else if(fondo==63421)
    {
      //Theme 4
      pic 500,115,302
    }else if(fondo==6339)
    {
      //Theme 5
      pic 500,115,304
    }else if(fondo==8484)
    {
      //Theme 6
      pic 500,115,306
    }
    //Text
    if(sys0==0)
    {
      //Spanish
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Comunicación"
    }else if(sys0==1)
    {
      //Italian
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Comunicazione"
    }else if(sys0==2)
    {
      //French
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Communication"
    }else if(sys0==3)
    {
      //English
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Communication"
    }else if(sys0==4)
    {
      //German
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Kommunikation"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 550,120,250,25,6,BLACK,color,0,1,3,"Comunicação"
    }
    //
    page Comunicacion

