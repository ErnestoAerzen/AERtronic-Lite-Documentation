Hora Nextion Page
============================

Description
-----------

Overview:
---------

This script defines a customizable graphical user interface (GUI) layout for an embedded system. The GUI includes circular elements, lines, buttons, and text fields. It allows users to input numbers using a number keyboard and provides multiple theme options for personalization.

Key Features:
-------------

Circular Elements:
~~~~~~~~~~~~~~~~~~
The GUI layout features several circular elements positioned in various sections of the interface. These circles serve as visual components and contribute to the overall aesthetics of the GUI.

Lines:
~~~~~~
Lines are used to connect circular elements and create a visually appealing layout. They provide separation and organization within the GUI design.

Number Keyboard:
~~~~~~~~~~~~~~~~
A number keyboard is integrated into the GUI, allowing users to input numeric values. The keyboard includes digits from 0 to 9, a "#" symbol, and an "Enter" button for data input.

Text Labels:
~~~~~~~~~~~~
Text labels are displayed within the GUI to guide users and provide context. These labels are customizable based on language preferences and theme selections.

Theme Selection:
~~~~~~~~~~~~~~~~
The script offers theme selection based on the value of the `fondo` variable. Different themes involve configuring font colors, circular element colors, and button styles, enabling users to personalize the GUI's appearance.

Multilingual Support:
~~~~~~~~~~~~~~~~~~~~
The text labels within the GUI support multiple languages, with content determined by the `sys0` variable. This feature enhances user accessibility and usability.

Usage:
------

Customizable GUI for Embedded Systems:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
This script serves as a template for creating a flexible and visually appealing GUI for embedded systems. It includes a number keyboard for data input and supports various themes and languages.

Note: To fully implement and use this script, developers should ensure compatibility with the target embedded system's hardware and any software dependencies.

Preinitialize event Hora
------------------------

.. code-block:: javascript

    // The default textbox selected everytime the page loads
    tselected.val=0
    // Assings 00 to indicate the number of seconds
    result.txt="00"
    // Changes the page's background to `fondo` value
    Hora.bco=fondo
    // Changes the color of the t0 textbox according to the theme selected
    t0.bco=button.val

Postinitialize event Hora
-------------------------

.. code-block:: javascript

    // First circle upper left
    cirs 80,80,20,color
    line 80,60,360,60,color
    // Second circle upper right
    cirs 360,80,20,color
    line 60,80,60,260,color
    // Third circle bottom left
    cirs 80,260,20,color
    line 380,80,380,260,color
    // Fourth circle bottom right
    cirs 360,260,20,color
    line 80,280,360,280,color
    // Fill rectangle middle
    fill 80,80,280,180,color
    // fill above
    fill 80,60,280,20,color
    // fill right
    fill 360,80,20,180,color
    // fill left
    fill 60,80,20,180,color
    // fill bottom
    fill 80,260,280,20,color
    // Themes
    if(fondo==65534)
    {
      // Font color
      fontColor.val=0
      // Aerzen icons
      pic 40,360,6
      pic 130,380,7
      // clock icon
      pic 80,240,18
      // Button color: 51089/#C7F089/0xC791
      button.val=51089
    }else if(fondo==63391)
    {
      // Font color
      fontColor.val=0
      // Aerzen icons
      pic 40,360,8
      pic 130,380,9
      // clock icon
      pic 80,240,19
      // Button color:55071/D4E3FF/0xD71F
      button.val=55071
    }else if(fondo==65438)
    {
      // Font color
      fontColor.val=0
      // Aerzen icons
      pic 40,360,10
      pic 130,380,11
      // clock icon
      pic 80,240,20
      // Button color:65214/#FFD7F4/0xFEBE
      button.val=65214
    }else if(fondo==63421)
    {
      // Font color
      fontColor.val=0
      // Aerzen icons
      pic 40,360,12
      pic 130,380,13
      // clock icon
      pic 80,240,21
      // Button color:53104/#CCEF85/0xCF70
      button.val=53104
    }else if(fondo==6339)
    {
      // Font color
      fontColor.val=65535
      // Aerzen icons
      pic 40,360,14
      pic 130,380,15
      // clock icon
      pic 80,240,22
      // Button color:55071/#D7E3FF/0xD71F
      button.val=55071
    }else if(fondo==8484)
    {
      // Font color
      fontColor.val=65535
      // Aerzen icons
      pic 40,360,16
      pic 130,380,17
      // clock icon
      pic 80,240,23
      // Button color:57166/#DEEB77/0xDF4E
      button.val=57166
    }
    //
    cirs 90,130,10,bcolor.val
    cirs 190,130,10,bcolor.val
    cirs 90,200,10,bcolor.val
    cirs 190,200,10,bcolor.val
    //
    line 90,120,190,120,bcolor.val
    line 200,130,200,200,bcolor.val
    line 80,130,80,200,bcolor.val
    line 90,210,190,210,bcolor.val
    //
    fill 90,130,100,70,bcolor.val
    fill 90,120,100,10,bcolor.val
    fill 190,130,10,70,bcolor.val
    fill 80,130,10,70,bcolor.val
    fill 90,200,100,10,bcolor.val
    //
    cirs 250,130,10,bcolor.val
    cirs 350,130,10,bcolor.val
    cirs 250,200,10,bcolor.val
    cirs 350,200,10,bcolor.val
    //
    line 250,120,350,120,bcolor.val
    line 350,130,350,200,bcolor.val
    line 240,130,240,200,bcolor.val
    line 250,210,250,210,bcolor.val
    //
    fill 250,130,100,70,bcolor.val
    fill 250,120,100,10,bcolor.val
    fill 350,130,10,70,bcolor.val
    fill 240,130,10,70,bcolor.val
    fill 250,200,100,10,bcolor.val
    // Ok Button
    cirs 310,250,20,0x3B44
    cirs 350,250,20,0x3B44
    line 310,230,350,230,0x3B44
    line 310,270,350,270,0x3B44
    fill 310,230,40,40,0x3B44
    // Cancel buton
    cirs 200,250,20,65535
    cirs 250,250,20,65535
    line 200,230,250,230,65535
    line 200,270,250,270,65535
    fill 200,230,50,40,65535
    //Text
    if(sys0==0)
    {
      // Headline Spanish
      xstr 80,80,150,25,0,fontColor.val,0xEFBD,0,1,3,"Ingrese la hora"
      xstr 210,130,25,55,1,fontColor.val,65535,1,1,3,":"
      xstr 200,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancelar"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==1)
    {
      // Headline Italian
      xstr 80,80,150,25,0,fontColor.val,0xEFBD,0,1,3,"Inserire l'ora"
      xstr 210,130,25,55,1,fontColor.val,65535,1,1,3,":"
      xstr 202,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Annulla"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==2)
    {
      // Headline French
      xstr 80,80,150,25,0,fontColor.val,0xEFBD,0,1,3,"Entrer l'heure"
      xstr 210,130,25,55,1,fontColor.val,65535,1,1,3,":"
      xstr 202,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Annuler"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==3)
    {
      // Headline English
      xstr 80,80,150,25,0,fontColor.val,0xEFBD,0,1,3,"Enter time"
      xstr 210,130,25,55,1,fontColor.val,65535,1,1,3,":"
      xstr 205,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancel"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==4)
    {
      // Headline German
      xstr 80,80,150,25,0,fontColor.val,0xEFBD,0,1,3,"Geben Sie die Zeit ein"
      xstr 210,130,25,55,1,fontColor.val,65535,1,1,3,":"
      xstr 195,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Stornieren"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==5)
    {
      // Headline Portuguese
      xstr 80,80,150,25,0,fontColor.val,0xEFBD,0,1,3,"Digite a hora"
      xstr 210,130,25,55,1,fontColor.val,65535,1,1,3,":"
      xstr 200,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancelar"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }
    // Number Keyboard
    // 1
    cirs 440,100,20,button.val
    cirs 500,100,20,button.val
    cirs 440,140,20,button.val
    cirs 500,140,20,button.val
    line 440,80,500,80,button.val
    line 440,160,500,160,button.val
    line 420,100,420,140,button.val
    line 520,100,520,140,button.val
    fill 440,80,60,80,button.val
    fill 420,100,20,40,button.val
    fill 500,100,20,40,button.val
    xstr 450,90,40,90,1,fontColor.val,button.val,1,0,3,"1"
    // 2
    cirs 560,100,20,button.val
    cirs 620,100,20,button.val
    cirs 560,140,20,button.val
    cirs 620,140,20,button.val
    line 560,80,620,80,button.val
    line 560,160,620,160,button.val
    line 540,100,540,140,button.val
    line 640,100,640,140,button.val
    fill 560,80,60,80,button.val
    fill 540,100,20,40,button.val
    fill 620,100,20,40,button.val
    xstr 570,90,40,90,1,fontColor.val,button.val,1,0,3,"2"
    // 3
    cirs 680,100,20,button.val
    cirs 740,100,20,button.val
    cirs 680,140,20,button.val
    cirs 740,140,20,button.val
    line 680,80,740,80,button.val
    line 680,160,740,160,button.val
    line 660,100,660,140,button.val
    line 760,100,760,140,button.val
    fill 680,80,60,80,button.val
    fill 660,100,20,40,button.val
    fill 740,100,20,40,button.val
    xstr 690,90,40,90,1,fontColor.val,button.val,1,0,3,"3"
    // 4
    cirs 440,200,20,button.val
    cirs 500,200,20,button.val
    cirs 440,240,20,button.val
    cirs 500,240,20,button.val
    line 440,180,500,180,button.val
    line 440,260,500,260,button.val
    line 420,200,420,240,button.val
    line 520,200,520,240,button.val
    fill 440,180,60,80,button.val
    fill 420,200,20,40,button.val
    fill 500,200,20,40,button.val
    xstr 450,190,40,90,1,fontColor.val,button.val,1,0,3,"4"
    // 5
    cirs 560,200,20,button.val
    cirs 620,200,20,button.val
    cirs 560,240,20,button.val
    cirs 620,240,20,button.val
    line 560,180,620,180,button.val
    line 560,260,620,260,button.val
    line 540,200,540,240,button.val
    line 640,200,640,240,button.val
    fill 560,180,60,80,button.val
    fill 540,200,20,40,button.val
    fill 620,200,20,40,button.val
    xstr 570,190,40,90,1,fontColor.val,button.val,1,0,3,"5"
    // 6
    cirs 680,200,20,button.val
    cirs 740,200,20,button.val
    cirs 680,240,20,button.val
    cirs 740,240,20,button.val
    line 680,180,740,180,button.val
    line 680,260,740,260,button.val
    line 660,200,660,240,button.val
    line 760,200,760,240,button.val
    fill 680,180,60,80,button.val
    fill 660,200,20,40,button.val
    fill 740,200,20,40,button.val
    xstr 690,190,40,90,1,fontColor.val,button.val,1,0,3,"6"
    // 7
    cirs 440,300,20,button.val
    cirs 500,300,20,button.val
    cirs 440,340,20,button.val
    cirs 500,340,20,button.val
    line 440,280,500,280,button.val
    line 440,360,500,360,button.val
    line 420,300,420,340,button.val
    line 520,300,520,340,button.val
    fill 440,280,60,80,button.val
    fill 420,300,20,40,button.val
    fill 500,300,20,40,button.val
    xstr 450,290,40,90,1,fontColor.val,button.val,1,0,3,"7"
    // 8
    cirs 560,300,20,button.val
    cirs 620,300,20,button.val
    cirs 560,340,20,button.val
    cirs 620,340,20,button.val
    line 560,280,620,280,button.val
    line 560,360,620,360,button.val
    line 540,300,540,340,button.val
    line 640,300,640,340,button.val
    fill 560,280,60,80,button.val
    fill 540,300,20,40,button.val
    fill 620,300,20,40,button.val
    xstr 570,290,40,90,1,fontColor.val,button.val,1,0,3,"8"
    // 9
    cirs 680,300,20,button.val
    cirs 740,300,20,button.val
    cirs 680,340,20,button.val
    cirs 740,340,20,button.val
    line 680,280,740,280,button.val
    line 680,360,740,360,button.val
    line 660,300,660,340,button.val
    line 760,300,760,340,button.val
    fill 680,280,60,80,button.val
    fill 660,300,20,40,button.val
    fill 740,300,20,40,button.val
    xstr 690,290,40,90,1,fontColor.val,button.val,1,0,3,"9"
    // #
    cirs 440,400,20,button.val
    cirs 500,400,20,button.val
    cirs 440,440,20,button.val
    cirs 500,440,20,button.val
    line 440,380,500,380,button.val
    line 440,460,500,460,button.val
    line 420,400,420,440,button.val
    line 520,400,520,440,button.val
    fill 440,380,60,80,button.val
    fill 420,400,20,40,button.val
    fill 500,400,20,40,button.val
    // 0
    cirs 560,400,20,button.val
    cirs 620,400,20,button.val
    cirs 560,440,20,button.val
    cirs 620,440,20,button.val
    line 560,380,620,380,button.val
    line 560,460,620,460,button.val
    line 540,400,540,440,button.val
    line 640,400,640,440,button.val
    fill 560,380,60,80,button.val
    fill 540,400,20,40,button.val
    fill 620,400,20,40,button.val
    xstr 570,390,40,90,1,fontColor.val,button.val,1,0,3,"0"
    // Enter
    cirs 680,400,20,button.val
    cirs 740,400,20,button.val
    cirs 680,440,20,button.val
    cirs 740,440,20,button.val
    line 680,380,740,380,button.val
    line 680,460,740,460,button.val
    line 660,400,660,440,button.val
    line 760,400,760,440,button.val
    fill 680,380,60,80,button.val
    fill 660,400,20,40,button.val
    fill 740,400,20,40,button.val
    xstr 690,385,40,90,1,fontColor.val,button.val,1,0,3,"x"
    //
    vis t0,1

Touch press event t0
--------------------

.. code-block:: javascript

    // Focus the typing in the t0 textbox
    tselected.val=0
    // Changes the color of the textbox t0 when is selected
    t0.bco=button.val
    // Changes the color of the t1 textbox when is not selected
    t1.bco=57146

Touch press event t1
--------------------

.. code-block:: javascript

    // Focus the typing in the t1 textbox
    tselected.val=1
    // Changes the color of the t1 textbox when is selected
    t1.bco=0xBF92
    // Changes the color of the t0 textbox when is not selected
    t0.bco=57146

Touch press event m0
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 420,80,101,81,fondo
    // Types 1 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="1"
    }else if(tselected.val==1)
    {
      t1.txt+="1"
    }

Touch release event m0
----------------------

.. code-block:: javascript

    // Draws the 1 button to complete the pressed button effect
    cirs 440,100,20,button.val
    cirs 500,100,20,button.val
    cirs 440,140,20,button.val
    cirs 500,140,20,button.val
    line 440,80,500,80,button.val
    line 440,160,500,160,button.val
    line 420,100,420,140,button.val
    line 520,100,520,140,button.val
    fill 440,80,60,80,button.val
    fill 420,100,20,40,button.val
    fill 500,100,20,40,button.val
    xstr 450,90,40,90,1,fontColor.val,button.val,1,0,3,"1"

Touch press event m1
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 540,80,101,81,fondo
    // Types 2 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="2"
    }else if(tselected.val==1)
    {
      t1.txt+="2"
    }

Touch release event m1
----------------------

.. code-block:: javascript

    // Draws the 2 button to complete the pressed button effect
    cirs 560,100,20,button.val
    cirs 620,100,20,button.val
    cirs 560,140,20,button.val
    cirs 620,140,20,button.val
    line 560,80,620,80,button.val
    line 560,160,620,160,button.val
    line 540,100,540,140,button.val
    line 640,100,640,140,button.val
    fill 560,80,60,80,button.val
    fill 540,100,20,40,button.val
    fill 620,100,20,40,button.val
    xstr 570,90,40,90,1,fontColor.val,button.val,1,0,3,"2"

Touch press event m2
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 660,80,101,81,fondo
    // Types 3 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="3"
    }else if(tselected.val==1)
    {
      t1.txt+="3"
    }

Touch release event m2
----------------------

.. code-block:: javascript

    // Draws the 3 button to complete the pressed button effect
    cirs 680,100,20,button.val
    cirs 740,100,20,button.val
    cirs 680,140,20,button.val
    cirs 740,140,20,button.val
    line 680,80,740,80,button.val
    line 680,160,740,160,button.val
    line 660,100,660,140,button.val
    line 760,100,760,140,button.val
    fill 680,80,60,80,button.val
    fill 660,100,20,40,button.val
    fill 740,100,20,40,button.val
    xstr 690,90,40,90,1,fontColor.val,button.val,1,0,3,"3"

Touch press event m3
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 420,180,101,81,fondo
    // Types 4 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="4"
    }else if(tselected.val==1)
    {
      t1.txt+="4"
    }

Touch release event m3
----------------------

.. code-block:: javascript

    // Draws the 4 button to complete the pressed button effect
    cirs 440,200,20,button.val
    cirs 500,200,20,button.val
    cirs 440,240,20,button.val
    cirs 500,240,20,button.val
    line 440,180,500,180,button.val
    line 440,260,500,260,button.val
    line 420,200,420,240,button.val
    line 520,200,520,240,button.val
    fill 440,180,60,80,button.val
    fill 420,200,20,40,button.val
    fill 500,200,20,40,button.val
    xstr 450,190,40,90,1,fontColor.val,button.val,1,0,3,"4"

Touch press event m4
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 540,180,101,81,fondo
    // Types 5 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="5"
    }else if(tselected.val==1)
    {
      t1.txt+="5"
    }

Touch release event m4
----------------------

.. code-block:: javascript

    // Draws the 5 button to complete the pressed button effect
    cirs 560,200,20,button.val
    cirs 620,200,20,button.val
    cirs 560,240,20,button.val
    cirs 620,240,20,button.val
    line 560,180,620,180,button.val
    line 560,260,620,260,button.val
    line 540,200,540,240,button.val
    line 640,200,640,240,button.val
    fill 560,180,60,80,button.val
    fill 540,200,20,40,button.val
    fill 620,200,20,40,button.val
    xstr 570,190,40,90,1,fontColor.val,button.val,1,0,3,"5"

Touch press event m5
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 660,180,101,81,fondo
    // Types 6 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="6"
    }else if(tselected.val==1)
    {
      t1.txt+="6"
    }

Touch release event m5
----------------------

.. code-block:: javascript

    // Draws the 6 button to complete the pressed button effect
    cirs 680,200,20,button.val
    cirs 740,200,20,button.val
    cirs 680,240,20,button.val
    cirs 740,240,20,button.val
    line 680,180,740,180,button.val
    line 680,260,740,260,button.val
    line 660,200,660,240,button.val
    line 760,200,760,240,button.val
    fill 680,180,60,80,button.val
    fill 660,200,20,40,button.val
    fill 740,200,20,40,button.val
    xstr 690,190,40,90,1,fontColor.val,button.val,1,0,3,"6"

Touch press event m6
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 420,280,101,81,fondo
    // Types 7 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="7"
    }else if(tselected.val==1)
    {
      t1.txt+="7"
    }

Touch release event m6
----------------------

.. code-block:: javascript

    // Draws the 7 button to complete the pressed button effect
    cirs 440,300,20,button.val
    cirs 500,300,20,button.val
    cirs 440,340,20,button.val
    cirs 500,340,20,button.val
    line 440,280,500,280,button.val
    line 440,360,500,360,button.val
    line 420,300,420,340,button.val
    line 520,300,520,340,button.val
    fill 440,280,60,80,button.val
    fill 420,300,20,40,button.val
    fill 500,300,20,40,button.val
    xstr 450,290,40,90,1,fontColor.val,button.val,1,0,3,"7"

Touch press event m7
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 540,280,101,81,fondo
    // Types 8 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="8"
    }else if(tselected.val==1)
    {
      t1.txt+="8"
    }

Touch release event m7
----------------------

.. code-block:: javascript

    // Draws the 8 button to complete the pressed button effect
    cirs 560,300,20,button.val
    cirs 620,300,20,button.val
    cirs 560,340,20,button.val
    cirs 620,340,20,button.val
    line 560,280,620,280,button.val
    line 560,360,620,360,button.val
    line 540,300,540,340,button.val
    line 640,300,640,340,button.val
    fill 560,280,60,80,button.val
    fill 540,300,20,40,button.val
    fill 620,300,20,40,button.val
    xstr 570,290,40,90,1,fontColor.val,button.val,1,0,3,"8"

Touch press event m8
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 660,280,101,81,fondo
    // Types 9 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="9"
    }else if(tselected.val==1)
    {
      t1.txt+="9"
    }

Touch release event m8
----------------------

.. code-block:: javascript

    // Draws the 9 button to complete the pressed button effect
    cirs 680,300,20,button.val
    cirs 740,300,20,button.val
    cirs 680,340,20,button.val
    cirs 740,340,20,button.val
    line 680,280,740,280,button.val
    line 680,360,740,360,button.val
    line 660,300,660,340,button.val
    line 760,300,760,340,button.val
    fill 680,280,60,80,button.val
    fill 660,300,20,40,button.val
    fill 740,300,20,40,button.val
    xstr 690,290,40,90,1,fontColor.val,button.val,1,0,3,"9"

Touch press event m9
--------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 420,380,101,81,fondo

Touch release event m9
----------------------

.. code-block:: javascript

    // Draws the # button to complete the pressed button effect
    cirs 440,400,20,button.val
    cirs 500,400,20,button.val
    cirs 440,440,20,button.val
    cirs 500,440,20,button.val
    line 440,380,500,380,button.val
    line 440,460,500,460,button.val
    line 420,400,420,440,button.val
    line 520,400,520,440,button.val
    fill 440,380,60,80,button.val
    fill 420,400,20,40,button.val
    fill 500,400,20,40,button.val

Touch press event m10
---------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 540,380,101,81,fondo
    // Types 0 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="0"
    }else if(tselected.val==1)
    {
      t1.txt+="0"
    }

Touch release event m10
-----------------------

.. code-block:: javascript

    // Draws the 0 button to complete the pressed button effect
    cirs 560,400,20,button.val
    cirs 620,400,20,button.val
    cirs 560,440,20,button.val
    cirs 620,440,20,button.val
    line 560,380,620,380,button.val
    line 560,460,620,460,button.val
    line 540,400,540,440,button.val
    line 640,400,640,440,button.val
    fill 560,380,60,80,button.val
    fill 540,400,20,40,button.val
    fill 620,400,20,40,button.val
    xstr 570,390,40,90,1,fontColor.val,button.val,1,0,3,"0"

Touch press event m11
---------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 660,380,101,81,fondo
    // Deletes the numbers according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt-=1
    }else if(tselected.val==1)
    {
      t1.txt-=1
    }

Touch release event m11
-----------------------

.. code-block:: javascript

    // Draws the x button to complete the pressed button effect
    cirs 680,400,20,button.val
    cirs 740,400,20,button.val
    cirs 680,440,20,button.val
    cirs 740,440,20,button.val
    line 680,380,740,380,button.val
    line 680,460,740,460,button.val
    line 660,400,660,440,button.val
    line 760,400,760,440,button.val
    fill 680,380,60,80,button.val
    fill 660,400,20,40,button.val
    fill 740,400,20,40,button.val
    xstr 690,385,40,90,1,fontColor.val,button.val,1,0,3,"x"

Touch press event m12
---------------------

.. code-block:: javascript

    // Fills the coordinates with the `color` selected to create a pressed button effect.
    fill 180,230,91,41,color

Touch release event m12
-----------------------

.. code-block:: javascript

    // Draws the cancel button to complete the pressed button efect
    cirs 200,250,20,65535
    cirs 250,250,20,65535
    line 200,230,250,230,65535
    line 200,270,250,270,65535
    fill 200,230,50,40,65535
    // Text according to the language selected
    if(sys0==0)
    {
      // Spanish
      xstr 200,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancelar"
    }else if(sys0==1)
    {
      // Italian  
      xstr 202,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Annulla"
    }else if(sys0==2)
    {
      // French  
      xstr 202,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Annuler"
    }else if(sys0==3)
    {
      //English  
      xstr 205,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancel"
    }else if(sys0==4)
    {
      // German  
      xstr 195,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Stornieren"
    }else if(sys0==5)
    {
      // Portuguese  
      xstr 200,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancelar"
    }
    // Reloads the Hora page
    delay=500
    page Hora

Touch press event m13
---------------------

.. code-block:: javascript

    // Completes the pressed button effect
    fill 290,230,81,41,color
    //Converts text into num to verify data
    covx t0.txt,hora.val,0,0
    covx t1.txt,min.val,0,0
    //Verifies data minutes
    if(min.val>=0&&min.val<60)
    {
      strlen t1.txt,sleng.val
      //if the user types only one number adds a
      //zero to prevent something wrong to happen
      if(min.val>=0&&min.val<=9&&sleng.val==1)
      {
        result.txt+=","
        result.txt+="0"
        result.txt+=t1.txt
      }else
      {
        result.txt+=","
        result.txt+=t1.txt
      }
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Ingresa un valor valido para minutos"
      }else if(sys0==1)
      {
        //Italian
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Immettere un valore valido per i minuti"
      }else if(sys0==2)
      {
        //French
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Entrez une valeur valide pour les minutes"
      }else if(sys0==3)
      {
        //English
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Enter a valid value for minutes"
      }else if(sys0==4)
      {
        //German
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Geben Sie einen gültigen Wert für Minuten ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Insira um valor válido para minutos"
      }
      //Resets page:
      result.txt="00"
      delay=2000
      page Hora
    }
    //Verifies data hours
    if(hora.val>=0&&hora.val<24)
    {
      strlen t0.txt,sleng.val
      //if the user types only one number adds a
      //zero to prevent something wrong to happen
      if(hora.val>=0&&hora.val<=9&&sleng.val==1)
      {
        result.txt+=","
        result.txt+="0"
        result.txt+=t0.txt
      }else
      {
        result.txt+=","
        result.txt+=t0.txt
      }
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Ingresa un valor valido para horas"
      }else if(sys0==1)
      {
        //Italian
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Immettere un valore valido per le ore"
      }else if(sys0==2)
      {
        //French
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Entrez une valeur valide pour les heures"
      }else if(sys0==3)
      {
        //English
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Enter a valid value for hours"
      }else if(sys0==4)
      {
        //German
        xstr 100,300,250,35,0,RED,65535,0,1,3,"Geben Sie einen gültigen Wert für Stunden ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Insira um valor válido para horas"
      }
      //Resets page:
      result.txt="00"
      delay=2000
      page Hora
    }

Touch release event m13
-----------------------

.. code-block:: javascript

    // Ok Button
    cirs 310,250,20,0x3B44
    cirs 350,250,20,0x3B44
    line 310,230,350,230,0x3B44
    line 310,270,350,270,0x3B44
    fill 310,230,40,40,0x3B44
    //Text
    if(sys0==0)
    {
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==1)
    {
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==2)
    {
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==3)
    {
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==4)
    {
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }else if(sys0==5)
    {
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
    }
    //Saves the length of result to variable sleng
    strlen result.txt,sleng.val
    if(sleng.val==8)
    {
      delay=500
      page Fecha
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Ingrese un valor valido"
      }else if(sys0==1)
      {
        //Italian
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Inserire un valore valido"
      }else if(sys0==2)
      {
        //French
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Entrez une valeur valide"
      }else if(sys0==3)
      {
        //English
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Enter a valid value"
      }else if(sys0==4)
      {
        //German
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Geben Sie einen gültigen Wert ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 100,300,250,25,0,RED,65535,0,1,3,"Digite um valor válido"
      }
      delay=2000
      page Hora
    }
    