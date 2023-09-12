ColorS Nextion Page
===================

Description
-----------

This script is designed for use with a Nextion display, a versatile touch-enabled graphical user interface commonly used in embedded projects. The script defines the layout and functionality of the display, including buttons, navigation elements, icons, and text, to create an interactive user interface.

Navigation Drawer
-----------------

- The script starts by defining a navigation drawer, which typically contains circular buttons for menu navigation. It uses the `cirs` command to draw circular buttons at specific coordinates with defined colors.
- Lines are drawn to connect these circular buttons, creating a visual separation.
- Rectangles are filled to create the background of the navigation drawer, giving it a distinct appearance.

Navigation Drawer Icons
~~~~~~~~~~~~~~~~~~~~~~~

- Based on the background color (`fondo`) selected, the script determines the theme and sets the font color accordingly.
- Each theme corresponds to a set of icons (represented by the `pic` command) placed at specific coordinates within the navigation drawer. These icons are displayed based on the selected theme.

Page Title
----------

- The script defines circular buttons for the page title, similar to those in the navigation drawer.
- Lines are drawn to connect these buttons, creating a visually cohesive title area.
- A rectangle is filled to serve as the background of the page title.

Buttons
~~~~~~~

- The script defines several buttons, each consisting of circular shapes.
- These buttons are drawn using the `cirs` command with different coordinates and colors.
- Lines are drawn to connect and delineate the buttons.
- Fill commands are used to color specific portions of the buttons, creating the appearance of distinct button areas.

Page Text
~~~~~~~~~

- Depending on the system language setting (`sys0`), the script displays text relevant to the selected language.
- Multiple language options are provided, and the appropriate text is displayed based on the language setting.

Conclusion
-----------

This script is an essential component of the Nextion display project, defining the visual elements and interactivity of the user interface. It allows users to navigate through menus, select themes, and interact with buttons while accommodating multiple languages. This script can be customized and expanded upon to suit the specific requirements of your project.

Preinitialize event ColorS
--------------------------

.. code-block:: javascript

    // Changes the page's background color
    ColorS.bco=fondo

Postinitialize event ColorS
---------------------------

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
    cirs 310,40,30,color
    cirs 540,40,30,color
    line 310,10,540,10,color
    line 310,70,540,70,color
    fill 310,10,240,60,color
    //Page title end
    //Buttons start
    //First button
    cirs 150,130,30,0xF7BD
    cirs 300,130,30,0xF7BD
    cirs 150,190,30,0xF7BD
    cirs 300,190,30,0xF7BD
    line 150,100,300,100,0xF7BD
    line 150,220,300,220,0xF7BD
    fill 150,100,150,120,0xF7BD
    line 120,130,120,190,0xF7BD
    fill 120,130,30,60,0xF7BD
    line 330,130,330,190,0xF7BD
    fill 300,130,30,60,0xF7BD
    //Second button
    cirs 380,130,30,0xD71F
    cirs 530,130,30,0xD71F
    cirs 380,190,30,0xD71F
    cirs 530,190,30,0xD71F
    line 380,100,530,100,0xD71F
    line 380,220,530,220,0xD71F
    fill 380,100,150,120,0xD71F
    line 350,130,350,190,0xD71F
    fill 350,130,30,60,0xD71F
    line 560,130,560,190,0xD71F
    fill 530,130,30,60,0xD71F
    //Third button
    cirs 610,130,30,0xFEDA
    cirs 760,130,30,0xFEDA
    cirs 610,190,30,0xFEDA
    cirs 760,190,30,0xFEDA
    line 610,100,760,100,0xFEDA
    line 610,220,760,220,0xFEDA
    fill 610,100,150,120,0xFEDA
    line 580,130,580,190,0xFEDA
    fill 580,130,30,60,0xFEDA
    line 790,130,790,190,0xFEDA
    fill 760,130,30,60,0xFEDA
    //Fourth button
    cirs 150,300,30,0xCF73
    cirs 300,300,30,0xCF73
    cirs 150,360,30,0xCF73
    cirs 300,360,30,0xCF73
    line 150,270,300,270,0xCF73
    line 150,390,300,390,0xCF73
    fill 150,270,150,120,0xCF73
    line 120,300,120,360,0xCF73
    fill 120,300,30,60,0xCF73
    line 330,300,330,360,0xCF73
    fill 300,300,30,60,0xCF73
    //Fifth button
    cirs 380,300,30,0x0231
    cirs 530,300,30,0x0231
    cirs 380,360,30,0x0231
    cirs 530,360,30,0x0231
    line 380,270,530,270,0x0231
    line 380,390,530,390,0x0231
    fill 380,270,150,120,0x0231
    line 350,300,350,360,0x0231
    fill 350,300,30,60,0x0231
    line 560,300,560,360,0x0231
    fill 530,300,30,60,0x0231
    //Sixth button
    cirs 610,300,30,0x4A44
    cirs 760,300,30,0x4A44
    cirs 610,360,30,0x4A44
    cirs 760,360,30,0x4A44
    line 610,270,760,270,0x4A44
    line 610,390,760,390,0x4A44
    fill 610,270,150,120,0x4A44
    line 580,300,580,360,0x4A44
    fill 580,300,30,60,0x4A44
    line 790,300,790,360,0x4A44
    fill 760,300,30,60,0x4A44
    //Buttons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Seleccionar color"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Seleziona il colore"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Choisissez la couleur"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Choose color"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Wähle Farbe"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Selecione a cor"
    }
    //Page text end

Touch press event m0
--------------------

.. code-block:: javascript

    //Changes the theme color
    fondo=65534
    //Changes the main color
    color=63421
    page ColorS

Touch press event m1
--------------------

.. code-block:: javascript

    //Changes the theme color
    fondo=63391
    //Changes the main color
    color=55071
    page ColorS

Touch press event m2
--------------------

.. code-block:: javascript

    //Changes the theme color
    fondo=65438
    //Changes the main color
    color=65242
    page ColorS

Touch press event m3
--------------------

.. code-block:: javascript

    //Changes the theme color
    fondo=63421
    //Changes the main color
    color=53107
    page ColorS

Touch press event m4
--------------------

.. code-block:: javascript

    //Changes the theme color
    fondo=6339
    //Changes the main color
    color=561
    page ColorS

Touch press event m5
--------------------

.. code-block:: javascript

    //Changes the theme color
    fondo=8484
    //Changes the main color
    color=19012
    page ColorS

Touch press event bInfoCol
--------------------------

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

Touch release event bInfoCol
----------------------------

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

Touch press event bHomeCol
--------------------------

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

Touch release event bHomeCol
----------------------------

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

Touch press event bBackCol
--------------------------

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

Touch release event bBackCol
----------------------------

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
