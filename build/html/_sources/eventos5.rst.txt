Eventos5 Nextion Page
=====================

Description
-----------

Navigation Drawer
-----------------

Four circular buttons are created in the navigation drawer, positioned at (30,30), (80,30), (30,450), and (80,450) with a radius of 20. These buttons serve as navigation options.

Lines are drawn between these buttons to visually separate them.

Filled rectangles are used to create the background of the navigation drawer.

Navigation Drawer Icons
-----------------------

The script checks the `fondo` variable, which likely represents the background theme.

Depending on the `fondo` value, the `fontColor.val` variable is set accordingly (0 for light themes, 65535 for dark themes).

Icons are displayed based on the selected theme (themes 1 to 6), using the `pic` command.

Page Title
----------

Two circular buttons with a radius of 30 are created for the page title.

Lines are drawn to connect these buttons for a decorative effect.

A filled rectangle serves as the background for the page title.

Page Text
---------

The script checks the `sys0` variable, likely representing the selected system language.

Text is displayed in different languages (Spanish, Italian, French, English, German, Portuguese) based on the `sys0` value using the `xstr` command. Text position and appearance are customized for each language.

Next Button and Back Button
---------------------------

A "Next" button is created with a circular shape, positioned at (720,440), with a radius of 20, and colored with the code 0x3B44.

Lines are drawn to complete the button's appearance, and a filled rectangle is used as the background.

The label "Next" is displayed on the button using the `xstr` command.

A "Back" button with similar attributes is created for navigation purposes.

Textbox Backgrounds
-------------------

Multiple textboxes (`e53` to `e65`) are defined with specific background and text color configurations based on the `fondo` and `fontColor.val` variables.

In summary, this script defines the layout and appearance of a user interface for a display, including navigation options, icons, text elements, and buttons for navigation and interaction. The appearance and behavior of the elements vary based on theme and language settings.

Preinitialize event Eventos5
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Eventos5.bco=fondo
    // Sends the current page's id
    sendme

Postinitialize event Eventos5
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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Eventos-5"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventi-5"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Evénements-5"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Events-5"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Veranstaltungen-5"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventos-5"
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
    e53.bco=fondo
    e53.pco=fontColor.val
    e54.bco=fondo
    e54.pco=fontColor.val
    e55.bco=fondo
    e55.pco=fontColor.val
    e56.bco=fondo
    e56.pco=fontColor.val
    e57.bco=fondo
    e57.pco=fontColor.val
    e58.bco=fondo
    e58.pco=fontColor.val
    e59.bco=fondo
    e59.pco=fontColor.val
    e60.bco=fondo
    e60.pco=fontColor.val
    e61.bco=fondo
    e61.pco=fontColor.val
    e62.bco=fondo
    e62.pco=fontColor.val
    e63.bco=fondo
    e63.pco=fontColor.val
    e64.bco=fondo
    e64.pco=fontColor.val
    e65.bco=fondo
    e65.pco=fontColor.val

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
    page Eventos6

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
    page Eventos4

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
    
    