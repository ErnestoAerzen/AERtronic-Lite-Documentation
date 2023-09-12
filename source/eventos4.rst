Eventos4 Nextion Page
============================

Description
-----------

This script is designed for a Nextion display, a touchscreen interface commonly used in embedded projects. The script defines the layout and functionality of the display, including buttons, icons, text elements, and textbox backgrounds.

Navigation Drawer
-----------------

The script begins by defining a navigation drawer with circular buttons (created using the `cirs` command) at specific coordinates. Lines are drawn to connect these circular buttons, forming a visual separation between them. Additionally, rectangles are filled to create the background of the navigation drawer. The `color` variable is used for the appearance of these elements.

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

The script checks the background color (`fondo`) and sets the font color (`fontColor.val`) accordingly. Depending on the background color, specific icons are displayed within the navigation drawer using the `pic` command. Each theme corresponds to a set of icons, enhancing the visual representation of the interface.

Page Title
----------

Following the navigation drawer, a visually appealing page title is defined with two circular buttons and connecting lines. A filled rectangle serves as the background of the title area. The `color` variable determines the appearance of these elements.

Page Text
---------

Text elements are displayed on the screen based on the value of `sys0`, representing the selected system language. Different text is displayed for various language settings. The `xstr` command is used to define text elements, specifying their position, font color, background color, and text content. In this script, a single text element is used to display event-related text based on the system language.

Next Button and Back Button
---------------------------

A "Next" button and a "Back" button are defined using circular buttons, connecting lines, and filled rectangles. The "Next" button is positioned at the bottom right corner of the screen and is colored using the `0x3B44` color code. The "Back" button is positioned next to it and is colored in red. Both buttons include text for user interaction.

Textbox Backgrounds
-------------------

Textbox backgrounds are set for multiple textboxes (`e40`, `e41`, ..., `e52`) on the display. The background color (`bco`) and text color (`pco`) are configured based on the `fondo` and `fontColor.val` variables, providing a consistent visual theme for text input areas.

Conclusion
-----------

This script defines the visual elements, icons, and interactivity of a Nextion display interface. It allows users to navigate through menus, view event-related text, and interact with "Next" and "Back" buttons. The use of variables for color, language settings, and textbox backgrounds enhances the customization and user experience of the display.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project in which it is used.

Preinitialize event Eventos4
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Eventos4.bco=fondo
    // Sends the current page's id
    sendme

Postinitialize event Eventos4
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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Eventos-4"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventi-4"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Evénements-4"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Events-4"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Veranstaltungen-4"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventos-4"
    }
    //Page text end
    //Next button
    cirs 720,440,20,0x3B44
    cirs 760,440,20,0x3B44
    line 720,420,760,420,0x3B44
    line 720,460,760,460,0x3B44
    fill 720,420,40,40,0x3B44
    xstr 720,430,40,20,6,WHITE,0x3B44,1,1,3,"Next"
    //NextButton
    //Back button
    cirs 620,440,20,RED
    cirs 660,440,20,RED
    line 620,420,660,420,RED
    line 620,460,660,460,RED
    fill 620,420,40,20,RED
    xstr 620,430,40,20,6,0,RED,1,1,3,"Back"
    //Textbox background
    e40.bco=fondo
    e40.pco=fontColor.val
    e41.bco=fondo
    e41.pco=fontColor.val
    e42.bco=fondo
    e42.pco=fontColor.val
    e43.bco=fondo
    e43.pco=fontColor.val
    e44.bco=fondo
    e44.pco=fontColor.val
    e45.bco=fondo
    e45.pco=fontColor.val
    e46.bco=fondo
    e46.pco=fontColor.val
    e47.bco=fondo
    e47.pco=fontColor.val
    e48.bco=fondo
    e48.pco=fontColor.val
    e49.bco=fondo
    e49.pco=fontColor.val
    e50.bco=fondo
    e50.pco=fontColor.val
    e51.bco=fondo
    e51.pco=fontColor.val
    e52.bco=fondo
    e52.pco=fontColor.val

Touch press event m0
--------------------

.. code-block:: javascript

    //Next button
    cirs 720,440,20,fondo
    cirs 760,440,20,fondo
    line 720,420,760,420,fondo
    line 720,460,760,460,fondo
    fill 720,420,40,40,fondo
    xstr 720,430,40,20,6,WHITE,fondo,1,1,3,"Next"
    //NextButton

Touch release event m0
----------------------

.. code-block:: javascript

    //Next button
    cirs 720,440,20,0x3B44
    cirs 760,440,20,0x3B44
    line 720,420,760,420,0x3B44
    line 720,460,760,460,0x3B44
    fill 720,420,40,40,0x3B44
    xstr 720,430,40,20,6,WHITE,0x3B44,1,1,3,"Next"
    //NextButton
    page Eventos5

Touch press event m1
--------------------

.. code-block:: javascript

    //Back button
    cirs 620,440,20,fondo
    cirs 660,440,20,fondo
    line 620,420,660,420,fondo
    line 620,460,660,460,fondo
    fill 620,420,40,20,fondo
    xstr 620,430,40,20,6,0,fondo,1,1,3,"Back"
    //Back button

Touch release event m1
----------------------

.. code-block:: javascript

    //Back button
    cirs 620,440,20,RED
    cirs 660,440,20,RED
    line 620,420,660,420,RED
    line 620,460,660,460,RED
    fill 620,420,40,20,RED
    xstr 620,430,40,20,6,0,RED,1,1,3,"Back"
    //Back button
    page Eventos3

Touch press event bInfoEv
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

Touch release event bInfoEv
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

Touch press event bHomeEv
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

Touch release event bHomeEv
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

Touch press event bBackEv
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

Touch release event bBackEv
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
    