Fecha Nextion Page
============================

Description
-----------

Circle Buttons and Lines:
--------------------------
The script creates four circular buttons with a radius of 20 at the following positions:
- Upper Left: (80, 80)
- Upper Right: (360, 80)
- Bottom Left: (80, 260)
- Bottom Right: (360, 260)

Lines are drawn to connect these circular buttons, creating a visual separation between them.

Fill Rectangles:
----------------
Several fill rectangles are used to create the layout and background of the user interface elements. These rectangles are used to define areas for buttons and text.

Date Box:
---------
A box for entering the date is created with lines. It has a rectangular shape with corners defined by lines and filled with a specific color. The date box consists of an outline and a filled background.

OK and Cancel Buttons:
-----------------------
- OK Button: A circular OK button with a radius of 20 is positioned at (310, 250). Lines connect the button, and it is filled with a specific color. The label "OK" is displayed in the button.
- Cancel Button: A circular Cancel button with a radius of 20 is positioned at (200, 250). Lines connect the button, and it is filled with a specific color. The label "Cancel" is displayed in the button.

Themes:
-------
The script checks the `fondo` variable, representing the background theme. Based on the `fondo` value, specific icons are displayed on the interface:
- Aerzen icons are displayed at various positions.
- A calendar icon is displayed at (340, 110).

Text Elements:
--------------
The script checks the `sys0` variable, likely representing the selected system language. Depending on the `sys0` value, the script displays text elements in different languages (Spanish, Italian, French, English, German, Portuguese) with various attributes like position, font color, and background color.

Number Keyboard:
----------------
A numeric keyboard is created with buttons for digits 0 to 9 and a special "Enter" button. Each digit button is a circular shape with a radius of 20 and is positioned in a grid layout. The digits are displayed in each button.

Textbox:
--------
The `vis` commands make textboxes `t0`, `t1`, and `t2` visible, likely indicating the presence of text input fields.

In summary, this script sets up a user interface layout for entering a date with options for choosing themes, displaying icons, and providing a numeric keyboard for input. The appearance and text content of elements are customized based on the selected language and theme.

Preinitialize event Fecha
-------------------------

.. code-block:: javascript

    // The default textbox selected everytime the page loads
    tselected.val=0
    // Changes the page's background to `fondo` value
    Fecha.bco=fondo
    // Changes the color of the t0 textbox according to the theme selected
    t0.bco=button.val

Postinitialize event Fecha
--------------------------

.. code-block:: javascript

    //First circle upper left
    cirs 80,80,20,color
    line 80,60,360,60,color
    //Second circle upper right
    cirs 360,80,20,color
    line 60,80,60,260,color
    //Third circle bottom left
    cirs 80,260,20,color
    line 380,80,380,260,color
    //Fourth circle bottom right
    cirs 360,260,20,color
    line 80,280,360,280,color
    //Fill rectangle middle
    fill 80,80,280,180,color
    //fill above
    fill 80,60,280,20,color
    //fill right
    fill 360,80,20,180,color
    //fill left
    fill 60,80,20,180,color
    //fill bottom
    fill 80,260,280,20,color
    //middle line
    line 60,140,380,140,0x4268
    //Date box
    line 80,155,110,155,0x43A6
    line 160,155,360,155,0x43A6
    line 360,155,360,225,0x43A6
    line 80,155,80,225,0x43A6
    line 80,225,360,225,0x43A6
    //Ok Button
    cirs 310,250,20,0x3B44
    cirs 350,250,20,0x3B44
    line 310,230,350,230,0x3B44
    line 310,270,350,270,0x3B44
    fill 310,230,40,40,0x3B44
    //Cancel buton
    cirs 200,250,20,65535
    cirs 250,250,20,65535
    line 200,230,250,230,65535
    line 200,270,250,270,65535
    fill 200,230,50,40,65535
    //Themes
    if(fondo==65534)
    {
      //Aerzen icons
      pic 40,360,6
      pic 130,380,7
      //Calendar icon
      pic 340,110,24
    }else if(fondo==63391)
    {
      //Aerzen icons
      pic 40,360,8
      pic 130,380,9
      //Calendar icon
      pic 340,110,25
    }else if(fondo==65438)
    {
      //Aerzen icons
      pic 40,360,10
      pic 130,380,11
      //Calendar icon
      pic 340,110,26
    }else if(fondo==63421)
    {
      //Aerzen icons
      pic 40,360,12
      pic 130,380,13
      //Calendar icon
      pic 340,110,27
    }else if(fondo==6339)
    {
      //Aerzen icons
      pic 40,360,14
      pic 130,380,15
      //Calendar icon
      pic 340,110,28
    }else if(fondo==8484)
    {
      //Aerzen icons
      pic 40,360,16
      pic 130,380,17
      //Calendar icon
      pic 340,110,29
    }
    if(sys0==0)
    {
      //Day/month/year Spanish
      xstr 120,205,45,20,2,BLACK,0xE75B,0,1,3,"Día"
      xstr 200,205,45,20,2,BLACK,0xE75B,0,1,3,"Mes"
      xstr 300,205,45,20,2,BLACK,0xE75B,0,1,3,"Año"
      //Headline
      xstr 80,100,250,35,3,BLACK,0xE75B,0,1,3,"Ingresar fecha"
      //
      xstr 200,240,80,25,2,BLACK,0xEFBD,0,1,3,"Cancelar"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
      xstr 120,145,100,25,2,0x43A6,0xE75B,0,1,3,"Fecha"
    }else if(sys0==1)
    {
      //Day/month/year Italian
      xstr 120,205,45,20,2,BLACK,0xE75B,0,1,3,"Giorno"
      xstr 200,205,45,20,2,BLACK,0xE75B,0,1,3,"Mese"
      xstr 300,205,45,20,2,BLACK,0xE75B,0,1,3,"Anno"
      //Headline
      xstr 80,100,250,35,3,BLACK,0xE75B,0,1,3,"Inserire la data"
      //
      xstr 200,240,80,25,2,BLACK,0xEFBD,0,1,3,"Annulla"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
      xstr 120,145,100,25,2,0x43A6,0xE75B,0,1,3,"Data"
    }else if(sys0==2)
    {
      //Day/month/year French
      xstr 120,205,45,20,2,BLACK,0xE75B,0,1,3,"Jour"
      xstr 200,205,45,20,2,BLACK,0xE75B,0,1,3,"Mois"
      xstr 300,205,45,20,2,BLACK,0xE75B,0,1,3,"An"
      //Headline
      xstr 80,100,250,35,3,BLACK,0xE75B,0,1,3,"Entrer la date"
      //
      xstr 200,240,80,25,2,BLACK,0xEFBD,0,1,3,"Annuler"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
      xstr 120,145,100,25,2,0x43A6,0xE75B,0,1,3,"Date"
    }else if(sys0==3)
    {
      //Day/month/year English
      xstr 120,205,45,20,2,BLACK,0xE75B,0,1,3,"Day"
      xstr 200,205,45,20,2,BLACK,0xE75B,0,1,3,"Month"
      xstr 300,205,45,20,2,BLACK,0xE75B,0,1,3,"Year"
      //Headline
      xstr 80,100,250,35,3,BLACK,0xE75B,0,1,3,"Enter date"
      //
      xstr 205,240,80,25,2,BLACK,0xEFBD,0,1,3,"Cancel"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
      xstr 120,145,100,25,2,0x43A6,0xE75B,0,1,3,"Date"
    }else if(sys0==4)
    {
      //Day/month/year German
      xstr 120,205,45,20,2,BLACK,0xE75B,0,1,3,"Tag"
      xstr 200,205,45,20,2,BLACK,0xE75B,0,1,3,"Monat"
      xstr 300,205,45,20,2,BLACK,0xE75B,0,1,3,"Jahr"
      //Headline
      xstr 80,100,250,35,3,BLACK,0xE75B,0,1,3,"Datum eingeben"
      //
      xstr 200,240,80,25,2,BLACK,0xEFBD,0,1,3,"Stornieren"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
      xstr 120,145,100,25,2,0x43A6,0xE75B,0,1,3,"Datum"
    }else if(sys0==5)
    {
      //Day/month/year Portuguese
      xstr 120,205,45,20,2,BLACK,0xE75B,0,1,3,"Dia"
      xstr 200,205,45,20,2,BLACK,0xE75B,0,1,3,"Mês"
      xstr 300,205,45,20,2,BLACK,0xE75B,0,1,3,"Ano"
      //Headline
      xstr 80,100,250,35,3,BLACK,0xE75B,0,1,3,"Insira a data"
      //
      xstr 200,240,80,25,2,BLACK,0xEFBD,0,1,3,"Cancelar"
      xstr 320,240,40,25,2,65535,0x3B44,0,1,13,"OK"
      xstr 120,145,100,25,2,0x43A6,0xE75B,0,1,3,"Data"
    }
    //Number Keyboard
    //1
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
    //2
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
    //3
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
    //4
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
    //5
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
    //6
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
    //7
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
    //8
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
    //9
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
    //#
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
    //0
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
    //Enter
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
    //Textbox
    vis t0,1
    vis t1,1
    vis t2,1

Touch press event t0
--------------------

.. code-block:: javascript

    // Indicates that the t0 textbox is selected
    tselected.val=0
    // Changes the color of the t0 textbox to indicate that is selected
    t0.bco=0xBF92
    // Changes the color of the remaining textboxes to focus only in the textbox selected
    t1.bco=57146
    t2.bco=57146

Touch press event t1
--------------------

.. code-block:: javascript

    // Indicates that the t1 textbox is selected
    tselected.val=1
    // Changes the color of the t1 textbox to indicate that is selected. Changes the color of the remaining textboxes to focus only in the textbox selected
    t0.bco=57146
    t1.bco=0xBF92
    t2.bco=57146

Touch press event t2
--------------------

.. code-block:: javascript

    // Indicates that the t2 textbox is selected
    tselected.val=2
    // Changes the color of the t2 textbox to indicate that is selected. Changes the color of the remaining textboxes to focus only in the textbox selected
    t0.bco=57146
    t1.bco=57146
    t2.bco=0xBF92

Touch press event m0
--------------------

.. code-block:: javascript

        // Fills the button area with the `fondo` value to create a pressed button effect
    fill 420,80,101,81,fondo
    // Types 1 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="1"
    }else if(tselected.val==1)
    {
      t1.txt+="1"
    }else if(tselected.val==2)
    {
      t2.txt+="1"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 540,80,101,81,fondo
    // Types 2 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="2"
    }else if(tselected.val==1)
    {
      t1.txt+="2"
    }else if(tselected.val==2)
    {
      t2.txt+="2"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 660,80,101,81,fondo
    // Types 3 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="3"
    }else if(tselected.val==1)
    {
      t1.txt+="3"
    }else if(tselected.val==2)
    {
      t2.txt+="3"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 420,180,101,81,fondo
    // Types 4 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="4"
    }else if(tselected.val==1)
    {
      t1.txt+="4"
    }else if(tselected.val==2)
    {
      t2.txt+="4"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 540,180,101,81,fondo
    // Types 5 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="5"
    }else if(tselected.val==1)
    {
      t1.txt+="5"
    }else if(tselected.val==2)
    {
      t2.txt+="5"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 660,180,101,81,fondo
    // Types 6 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="6"
    }else if(tselected.val==1)
    {
      t1.txt+="6"
    }else if(tselected.val==2)
    {
      t2.txt+="6"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 420,280,101,81,fondo
    // Types 7 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="7"
    }else if(tselected.val==1)
    {
      t1.txt+="7"
    }else if(tselected.val==2)
    {
      t2.txt+="7"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 540,280,101,81,fondo
    // Types 8 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="8"
    }else if(tselected.val==1)
    {
      t1.txt+="8"
    }else if(tselected.val==2)
    {
      t2.txt+="8"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 660,280,101,81,fondo
    // Types 9 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="9"
    }else if(tselected.val==1)
    {
      t1.txt+="9"
    }else if(tselected.val==2)
    {
      t2.txt+="9"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 540,380,101,81,fondo
    // Types 0 according to what textbox is selected
    if(tselected.val==0)
    {
      t0.txt+="0"
    }else if(tselected.val==1)
    {
      t1.txt+="0"
    }else if(tselected.val==2)
    {
      t2.txt+="0"
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

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 660,380,101,81,fondo
    // Deletes one number according from the textbox selected
    if(tselected.val==0)
    {
      t0.txt-=1
    }else if(tselected.val==1)
    {
      t1.txt-=1
    }else if(tselected.val==2)
    {
      t2.txt-=1
    }

Touch press event m12
---------------------

.. code-block:: javascript

    // Fills the button area with the `fondo` value to create a pressed button effect
    fill 180,230,91,41,color

Touch release event m12
-----------------------

.. code-block:: javascript

    //Cancel buton
    cirs 200,250,20,65535
    cirs 250,250,20,65535
    line 200,230,250,230,65535
    line 200,270,250,270,65535
    fill 200,230,50,40,65535
    //Text
    if(sys0==0)
    {
      xstr 200,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancelar"
    }else if(sys0==1)
    {
      xstr 202,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Annulla"
    }else if(sys0==2)
    {
      xstr 202,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Annuler"
    }else if(sys0==3)
    {
      xstr 205,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancel"
    }else if(sys0==4)
    {
      xstr 195,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Stornieren"
    }else if(sys0==5)
    {
      xstr 200,240,80,25,2,fontColor.val,0xEFBD,0,1,3,"Cancelar"
    }
    //Reloads page
    delay=500
    page Fecha

Touch press event m13
---------------------

.. code-block:: javascript

    fill 290,230,81,41,color
    //Converts text into num to verify data
    covx t0.txt,day.val,0,0
    covx t1.txt,mon.val,0,0
    covx t2.txt,year.val,0,0
    //Verifies data days
    if(day.val>=0&&day.val<32)
    {
      strlen t0.txt,sleng.val
      //if the user types only one number adds a
      //zero to prevent something wrong to happen
      if(day.val>=0&&day.val<=9&&sleng.val==1)
      {
        date.txt+=","
        date.txt+="0"
        date.txt+=t0.txt
      }else
      {
        date.txt+=","
        date.txt+=t0.txt
      }
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 100,300,250,25,0,RED,color,0,1,3,"Ingrese un valor valido para días"
      }else if(sys0==1)
      {
        //Italian
        xstr 100,300,250,25,0,RED,color,0,1,3,"Immettere un valore valido per i giorni"
      }else if(sys0==2)
      {
        //French
        xstr 100,300,250,25,0,RED,color,0,1,3,"Entrez une valeur valide pour les jours"
      }else if(sys0==3)
      {
        //English
        xstr 100,300,250,25,0,RED,color,0,1,3,"Enter a valid value for days"
      }else if(sys0==4)
      {
        //German
        xstr 100,300,250,25,0,RED,color,0,1,3,"Geben Sie einen gültigen Wert für Tage ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 100,300,250,25,0,RED,color,0,1,3,"Insira um valor válido para dias"
      }
      //Resets page:
      date.txt=""
      delay=2000
      page Fecha
    }
    //Verifies data months
    if(mon.val>0&&mon.val<=12)
    {
      strlen t1.txt,sleng.val
      //if the user types only one number adds a
      //zero to prevent something wrong to happen
      if(mon.val>0&&mon.val<=9&&sleng.val==1)
      {
        date.txt+=","
        date.txt+="0"
        date.txt+=t1.txt
      }else
      {
        date.txt+=","
        date.txt+=t1.txt
      }
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 100,300,250,25,0,RED,color,0,1,3,"Ingrese un valor valido para meses"
      }else if(sys0==1)
      {
        //Italian
        xstr 100,300,250,25,0,RED,color,0,1,3,"Immettere un valore valido per mesi"
      }else if(sys0==2)
      {
        //French
        xstr 100,300,250,25,0,RED,color,0,1,3,"Entrez une valeur valide pour les mois"
      }else if(sys0==3)
      {
        //English
        xstr 100,300,250,25,0,RED,color,0,1,3,"Enter a valid value for months"
      }else if(sys0==4)
      {
        //German
        xstr 100,300,250,25,0,RED,color,0,1,3,"Geben Sie einen gültigen Wert für Monate ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 100,300,250,25,0,RED,color,0,1,3,"Insira um valor válido para meses"
      }
      //Resets page:
      date.txt=""
      delay=2000
      page Fecha
    }
    //Verifies data years
    if(year.val>=2023)
    {
      date.txt+=","
      date.txt+=t2.txt
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 100,300,250,25,0,RED,color,0,1,3,"Ingrese un valor valido para años"
      }else if(sys0==1)
      {
        //Italian
        xstr 100,300,250,25,0,RED,color,0,1,3,"Immettere un valore valido per gli anni"
      }else if(sys0==2)
      {
        //French
        xstr 100,300,250,25,0,RED,color,0,1,3,"Entrez une valeur valide pour les années"
      }else if(sys0==3)
      {
        //English
        xstr 100,300,250,25,0,RED,color,0,1,3,"Enter a valid value for years"
      }else if(sys0==4)
      {
        //German
        xstr 100,300,250,25,0,RED,color,0,1,3,"Geben Sie einen gültigen Wert für Jahre ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 100,300,250,25,0,RED,color,0,1,3,"Insira um valor válido para anos"
      }
      //Resets page:
      date.txt=""
      delay=2000
      page Fecha
    }

Touch release event m13
-----------------------

.. code-block:: javascript

    //Ok Button
    cirs 310,250,20,0x3B44
    cirs 350,250,20,0x3B44
    line 310,230,350,230,0x3B44
    line 310,270,350,270,0x3B44
    fill 310,230,40,40,0x3B44
    Hora.result.txt+=date.txt
    //Saves the length of result to variable sleng
    strlen Hora.result.txt,sleng.val
    if(sleng.val==19)
    {
      get Hora.result.txt
      delay=500
      page Inicio
    }else
    {
      //Prints a message if the user types an invalid number
      if(sys0==0)
      {
        //Spanish
        xstr 200,300,250,25,0,RED,color,0,1,3,"Ingrese un valor valido"
      }else if(sys0==1)
      {
        //Italian
        xstr 200,300,250,25,0,RED,color,0,1,3,"Inserire un valore valido"
      }else if(sys0==2)
      {
        //French
        xstr 200,300,250,25,0,RED,color,0,1,3,"Entrez une valeur valide"
      }else if(sys0==3)
      {
        //English
        xstr 200,300,250,25,0,RED,color,0,1,3,"Enter a valid value"
      }else if(sys0==4)
      {
        //German
        xstr 200,300,250,25,0,RED,color,0,1,3,"Geben Sie einen gültigen Wert ein"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 200,300,250,25,0,RED,color,0,1,3,"Digite um valor válido"
      }
      delay=2000
      page Fecha
    }
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
    
    