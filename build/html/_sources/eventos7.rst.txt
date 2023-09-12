Eventos7 Nextion Page
============================

Description
-----------

Navigation Drawer:
------------------
The script defines the elements of a navigation drawer:
- Four circular buttons with a radius of 20 are created and positioned at coordinates (30, 30), (80, 30), (30, 450), and (80, 450).
- Lines are drawn to connect these circular buttons, creating a visual separation between them.
- Filled rectangles are used to create the background of the navigation drawer.

Navigation Drawer Icons:
-------------------------
The script checks the value of the `fondo` variable, representing the background theme. Based on the `fondo` value, the script sets the `fontColor.val` variable, which is related to font color.
Then, icons are displayed according to the selected theme (themes 1 to 6) using the `pic` command.

Page Title:
------------
The script defines elements for the page title:
- Two circular buttons with a radius of 30 are created at positions (300, 40) and (550, 40).
- Lines are drawn to connect these circular buttons, and a filled rectangle is used as the background of the page title.

Page Text:
-----------
The script checks the `sys0` variable, likely representing the selected system language. Based on the `sys0` value, text is displayed in different languages (Spanish, Italian, French, English, German, Portuguese) using the `xstr` command. The text is customized in terms of position, font color, and other attributes for each language.

Back Button:
-------------
A "Back" button is created for navigation purposes, with a red color scheme. It has a circular shape with a radius of 20 and is positioned at (620, 440). Lines and a filled rectangle complete the button's appearance, and the label "Back" is displayed using the `xstr` command.

Textbox Backgrounds:
---------------------
The script defines multiple textboxes (`e79` to `e91`) with specific background and text color configurations based on the `fondo` and `fontColor.val` variables.

In summary, this script sets up a user interface layout with navigation options, icons, text elements, and a navigation button. The appearance of elements is customized based on the selected theme and language settings.

Preinitialize event Eventos7
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Eventos7.bco=fondo
    // Sends the current page's id
    sendme

Postinitialize event Eventos7
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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Eventos-7"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventi-7"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Evénements-7"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Events-7"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Veranstaltungen-7"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Eventos-7"
    }
    //Page text end
    //Back button
    cirs 620,440,20,RED
    cirs 660,440,20,RED
    line 620,420,660,420,RED
    line 620,460,660,460,RED
    fill 620,420,40,20,RED
    xstr 620,430,40,20,6,0,RED,1,1,3,"Back"
    //Textbox background
    e79.bco=fondo
    e79.pco=fontColor.val
    e80.bco=fondo
    e80.pco=fontColor.val
    e81.bco=fondo
    e81.pco=fontColor.val
    e82.bco=fondo
    e82.pco=fontColor.val
    e83.bco=fondo
    e83.pco=fontColor.val
    e84.bco=fondo
    e84.pco=fontColor.val
    e85.bco=fondo
    e85.pco=fontColor.val
    e86.bco=fondo
    e86.pco=fontColor.val
    e87.bco=fondo
    e87.pco=fontColor.val
    e88.bco=fondo
    e88.pco=fontColor.val
    e89.bco=fondo
    e89.pco=fontColor.val
    e90.bco=fondo
    e90.pco=fontColor.val
    e91.bco=fondo
    e91.pco=fontColor.val

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
    page Eventos6

Touch press event bInfoEv
-------------------------

.. code-block:: javascript

    // Changes the images according the theme selected
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