Eventos1 Nextion Page
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

Next Button
-----------

A "Next" button is defined using two circular buttons, connecting lines, and a filled rectangle. The button is positioned at the bottom right corner of the screen. It is colored using the `0x3B44` color code. The button includes the text "Next" for user interaction.

Textbox Backgrounds
-------------------

Textbox backgrounds are set for multiple textboxes (`e1`, `e2`, ..., `e13`) on the display. The background color (`bco`) and text color (`pco`) are configured based on the `fondo` and `fontColor.val` variables, providing a consistent visual theme for text input areas.

Conclusion
-----------

This script defines the visual elements, icons, and interactivity of a Nextion display interface. It allows users to navigate through menus, view event-related text, and interact with a "Next" button. The use of variables for color and language settings enhances the customization and user experience of the display.

Please note that the specific functionality and behavior of this script may vary based on the broader context of the project in which it is used.

Preinitialize event Eventos1
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Eventos1.bco=fondo
    // Sends the current page's id
    sendme

Postinitialize event Eventos1
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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Eventos-1"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventi-1"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Evénements-1"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Events-1"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Veranstaltungen-1"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventos-1"
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
    //Textbox background
    e1.bco=fondo
    e1.pco=fontColor.val
    e2.bco=fondo
    e2.pco=fontColor.val
    e3.bco=fondo
    e3.pco=fontColor.val
    e4.bco=fondo
    e4.pco=fontColor.val
    e5.bco=fondo
    e5.pco=fontColor.val
    e6.bco=fondo
    e6.pco=fontColor.val
    e7.bco=fondo
    e7.pco=fontColor.val
    e8.bco=fondo
    e8.pco=fontColor.val
    e9.bco=fondo
    e9.pco=fontColor.val
    e10.bco=fondo
    e10.pco=fontColor.val
    e11.bco=fondo
    e11.pco=fontColor.val
    e12.bco=fondo
    e12.pco=fontColor.val
    e13.bco=fondo
    e13.pco=fontColor.val

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
    page Eventos2

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