Limites3 Nextion Page
============================

Description
-----------

Introduction
------------

This script defines the layout and elements of a graphical user interface (GUI) using a custom domain-specific language. It creates a visually appealing interface with various shapes, lines, fills, and text elements. The script is organized into several sections, each responsible for specific components of the GUI.

Nav Drawer
----------

The **Navigation Drawer** section creates a navigation drawer with icons and borders. It consists of the following elements:

- Four circular icons (`cirs`) for navigation options.
- Four lines (`line`) to outline the drawer.
- Two filled rectangles (`fill`) to color specific areas within the drawer.

Main Container
--------------

The **Main Container** section defines the main content area of the GUI. It includes:

- Two circular elements (`cirs`) for visual appeal.
- Four lines (`line`) to create a border around the main content.
- Three filled rectangles (`fill`) for coloring specific regions within the container.

Inner Containers
----------------

There are two **Inner Container** sections, each similar in structure. They include:

- Four circular elements (`cirs`) within each inner container.
- Four lines (`line`) outlining each inner container.
- Three filled rectangles (`fill`) to colorize certain parts of the inner containers.

Buttons
-------

The script defines two types of buttons: a **Cancel Button** and an **OK Button**. Each button includes:

- Two circular elements (`cirs`) representing the button's appearance.
- Four lines (`line`) outlining the button's borders.
- One filled rectangle (`fill`) to give color to the button.

Nav Drawer Icons
----------------

This section dynamically displays icons based on the value of the `fondo` variable. The icons change to reflect different themes. It includes:

- Conditional checks based on the `fondo` variable.
- Usage of the `pic` command to display theme-specific icons.

Page Title
----------

The **Page Title** section displays a title at the top of the GUI. It comprises:

- Two circular elements (`cirs`) for decorative purposes.
- Two lines (`line`) forming a border around the title.
- One filled rectangle (`fill`) to provide a background color for the title area.

Page Text
---------

The **Page Text** section presents textual content based on the `sys0` variable, which determines the language. It includes:

- Conditional checks based on the `sys0` variable to select the appropriate language.
- Usage of the `xstr` command to display text with varying content, colors, and positions.

Number Keyboard
---------------

The **Number Keyboard** section defines a numeric keypad with digits 1 through 9, '0', and 'x'. It consists of:

- Circles (`cirs`) and lines (`line`) to create buttons for each digit.
- Text labels (`xstr`) for each digit.
- The '0' and 'x' buttons serve specific functions.

Conclusion
----------

This script is designed to create a versatile GUI with customizable themes and multilingual support. The layout and appearance of the interface elements are determined by various conditional checks and variable values, offering flexibility in design and functionality.

Please note that the execution and visualization of this GUI script may depend on the specific graphics system and variable values, and it may require integration with a compatible platform to function as intended.

Preinitialize event Limites3
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Limites3.bco=fondo
    // Focus on the t0 textbox
    tselected.val=0

Postinitialize event Limites3
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
    //Main container start
    cirs 160,120,20,color
    line 160,100,440,100,color
    cirs 440,120,20,color
    line 140,120,140,280,color
    cirs 160,280,20,color
    line 160,300,440,300,color
    cirs 440,280,20,color
    line 460,120,460,280,color
    fill 160,100,280,200,color
    fill 140,120,20,160,color
    fill 440,120,20,160,color
    //Main container end
    //Inner container 1 start
    cirs 170,170,10,45347
    cirs 270,170,10,45347
    cirs 170,240,10,45347
    cirs 270,240,10,45347
    line 170,160,270,160,45347
    line 280,170,280,240,45347
    line 170,250,270,250,45347
    line 160,170,160,240,45347
    fill 170,160,100,90,45347
    fill 160,170,10,70,45347
    fill 270,170,10,70,45347
    //Inner container 1 end
    //Inner container 2 start
    cirs 330,170,10,58631
    cirs 430,170,10,58631
    cirs 330,240,10,58631
    cirs 430,240,10,58631
    line 330,160,430,160,58631
    line 440,170,440,240,58631
    line 330,250,430,250,58631
    line 320,170,320,240,58631
    fill 330,160,100,90,58631
    fill 320,170,10,70,58631
    fill 430,170,10,70,58631
    //Inner container 2 end
    //Cancel buton
    cirs 270,275,15,65535
    cirs 330,275,15,65535
    line 270,260,330,260,65535
    line 270,290,330,290,65535
    fill 270,260,60,30,65535
    //OK button
    cirs 370,275,15,0x3B44
    cirs 430,275,15,0x3B44
    line 370,260,430,260,0x3B44
    line 370,290,430,290,0x3B44
    fill 370,260,60,30,0x3B44
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
      fontColor.val=0
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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Temperatura final"
      xstr 160,110,280,35,0,fontColor.val,45347,0,1,3,"Valor de alarma y de advertencia temperatura final (°C)"
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Cancelar"
      xstr 370,265,60,25,2,WHITE,0x3B44,1,1,3,"OK"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Temperatura finale"
      xstr 160,110,280,35,0,fontColor.val,45347,0,1,3,"Valore di allarme e avviso di temperatura finale (°C)"
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Annulla"
      xstr 370,265,60,25,2,WHITE,0x3B44,1,1,3,"OK"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Température finale"
      xstr 160,110,280,35,0,fontColor.val,45347,0,1,3,"Alarme de température finale et valeur d'avertissement (°C)"
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Annuler"
      xstr 370,265,60,25,2,WHITE,0x3B44,1,1,3,"OK"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,2,fontColor.val,color,1,1,3,"Final temperature"
      xstr 160,110,280,35,0,fontColor.val,45347,0,1,3,"Final temperature alarm and warning value (°C)"
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Cancel"
      xstr 370,265,60,25,2,WHITE,0x3B44,1,1,3,"OK"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,2,fontColor.val,color,1,1,3,"Endtemperatur"
      xstr 160,110,280,35,0,fontColor.val,45347,0,1,3,"Endtemperatur Alarm- und Warnwert (°C)"
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Stornieren"
      xstr 370,265,60,25,2,WHITE,0x3B44,1,1,3,"OK"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,2,fontColor.val,color,1,1,3,"Temperatura final"
      xstr 160,110,280,35,0,fontColor.val,45347,0,1,3,"Alarme de temperatura final e valor de aviso (°C)"
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Cancelar"
      xstr 370,265,60,25,2,WHITE,0x3B44,1,1,3,"OK"
    }
    //Page text end
    //Number Keyboard
    //1
    cirs 500,100,20,button.val
    cirs 540,100,20,button.val
    cirs 500,140,20,button.val
    cirs 540,140,20,button.val
    line 500,80,540,80,button.val
    line 500,160,540,160,button.val
    line 480,100,480,140,button.val
    line 560,100,560,140,button.val
    fill 500,80,40,80,button.val
    fill 480,100,80,40,button.val
    xstr 500,90,40,90,1,fontColor.val,button.val,1,0,3,"1"
    //2
    cirs 600,100,20,button.val
    cirs 640,100,20,button.val
    cirs 600,140,20,button.val
    cirs 640,140,20,button.val
    line 600,80,640,80,button.val
    line 600,160,640,160,button.val
    line 580,100,580,140,button.val
    line 660,100,660,140,button.val
    fill 600,80,40,80,button.val
    fill 580,100,80,40,button.val
    xstr 600,90,40,90,1,fontColor.val,button.val,1,0,3,"2"
    //3
    cirs 700,100,20,button.val
    cirs 740,100,20,button.val
    cirs 700,140,20,button.val
    cirs 740,140,20,button.val
    line 700,80,740,80,button.val
    line 700,160,740,160,button.val
    line 680,100,680,140,button.val
    line 760,100,760,140,button.val
    fill 700,80,40,80,button.val
    fill 680,100,80,40,button.val
    xstr 700,90,40,90,1,fontColor.val,button.val,1,0,3,"3"
    //4
    cirs 500,200,20,button.val
    cirs 540,200,20,button.val
    cirs 500,240,20,button.val
    cirs 540,240,20,button.val
    line 500,180,540,180,button.val
    line 500,260,540,260,button.val
    line 480,200,480,240,button.val
    line 560,200,560,240,button.val
    fill 500,180,40,80,button.val
    fill 480,200,80,40,button.val
    xstr 500,190,40,90,1,fontColor.val,button.val,1,0,3,"4"
    //5
    cirs 600,200,20,button.val
    cirs 640,200,20,button.val
    cirs 600,240,20,button.val
    cirs 640,240,20,button.val
    line 600,180,640,180,button.val
    line 600,260,640,260,button.val
    line 580,200,580,240,button.val
    line 660,200,660,240,button.val
    fill 600,180,40,80,button.val
    fill 580,200,80,40,button.val
    xstr 600,190,40,90,1,fontColor.val,button.val,1,0,3,"5"
    //6
    cirs 700,200,20,button.val
    cirs 740,200,20,button.val
    cirs 700,240,20,button.val
    cirs 740,240,20,button.val
    line 700,180,740,180,button.val
    line 700,260,740,260,button.val
    line 680,200,680,240,button.val
    line 760,200,760,240,button.val
    fill 700,180,40,80,button.val
    fill 680,200,80,40,button.val
    xstr 700,190,40,90,1,fontColor.val,button.val,1,0,3,"6"
    //7
    cirs 500,300,20,button.val
    cirs 540,300,20,button.val
    cirs 500,340,20,button.val
    cirs 540,340,20,button.val
    line 500,280,540,280,button.val
    line 500,360,540,360,button.val
    line 480,300,480,340,button.val
    line 560,300,560,340,button.val
    fill 500,280,40,80,button.val
    fill 480,300,80,40,button.val
    xstr 500,290,40,90,1,fontColor.val,button.val,1,0,3,"7"
    //8
    cirs 600,300,20,button.val
    cirs 640,300,20,button.val
    cirs 600,340,20,button.val
    cirs 640,340,20,button.val
    line 600,280,640,280,button.val
    line 600,360,640,360,button.val
    line 580,300,580,340,button.val
    line 660,300,660,340,button.val
    fill 600,280,40,80,button.val
    fill 580,300,80,40,button.val
    xstr 600,290,40,90,1,fontColor.val,button.val,1,0,3,"8"
    //9
    cirs 700,300,20,button.val
    cirs 740,300,20,button.val
    cirs 700,340,20,button.val
    cirs 740,340,20,button.val
    line 700,280,740,280,button.val
    line 700,360,740,360,button.val
    line 680,300,680,340,button.val
    line 760,300,760,340,button.val
    fill 700,280,40,80,button.val
    fill 680,300,80,40,button.val
    xstr 700,290,40,90,1,fontColor.val,button.val,1,0,3,"9"
    //#
    cirs 500,400,20,button.val
    cirs 540,400,20,button.val
    cirs 500,440,20,button.val
    cirs 540,440,20,button.val
    line 500,380,540,380,button.val
    line 500,460,540,460,button.val
    line 480,400,480,440,button.val
    line 560,400,560,440,button.val
    fill 500,380,40,80,button.val
    fill 480,400,80,40,button.val
    //0
    cirs 600,400,20,button.val
    cirs 640,400,20,button.val
    cirs 600,440,20,button.val
    cirs 640,440,20,button.val
    line 600,380,640,380,button.val
    line 600,460,640,460,button.val
    line 580,400,580,440,button.val
    line 660,400,660,440,button.val
    fill 600,380,40,80,button.val
    fill 580,400,80,40,button.val
    xstr 600,390,40,90,1,fontColor.val,button.val,1,0,3,"0"
    //x
    cirs 700,400,20,button.val
    cirs 740,400,20,button.val
    cirs 700,440,20,button.val
    cirs 740,440,20,button.val
    line 700,380,740,380,button.val
    line 700,460,740,460,button.val
    line 680,400,680,440,button.val
    line 760,400,760,440,button.val
    fill 700,380,40,80,button.val
    fill 680,400,80,40,button.val
    xstr 700,385,40,90,1,fontColor.val,button.val,1,0,3,"x"

Touch release event m0
----------------------

.. code-block:: javascript

    cirs 270,275,15,65535
    cirs 330,275,15,65535
    line 270,260,330,260,65535
    line 270,290,330,290,65535
    fill 270,260,60,30,65535
    if(sys0==0)
    {
      xstr 270,265,60,25,5,0x3B44,65535,1,1,3,"Cancelar"
    }else if(sys0==1)
    {
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Annulla"
    }else if(sys0==2)
    {
      //French
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Annuler"
    }else if(sys0==3)
    {
      //English
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Cancel"
    }else if(sys0==4)
    {
      //German
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Stornieren"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 270,265,60,25,2,0x3B44,65535,1,1,3,"Cancelar"
    }
    page Limites3

Touch press event m1
--------------------

.. code-block:: javascript

    cirs 370,275,15,color
    cirs 430,275,15,color
    line 370,260,430,260,color
    line 370,290,430,290,color
    fill 370,260,60,30,color
    //txt into int
    covx t0.txt,alarm.val,0,0
    covx t1.txt,warning.val,0,0

Touch release event m1
----------------------

.. code-block:: javascript

    cirs 370,275,15,0x3B44
    cirs 430,275,15,0x3B44
    line 370,260,430,260,0x3B44
    line 370,290,430,290,0x3B44
    fill 370,260,60,30,0x3B44
    if(sys0==0)
    {
      xstr 370,265,60,25,5,WHITE,0x3B44,1,1,3,"OK"
    }
    //Checks the values
    if(alarm.val>=warning.val)
    {
      maxP1=alarm.val
      warnP1=warning.val
      page Limites4
    }else
    {
      if(sys0==0)
      {
        xstr 150,400,250,35,6,RED,color,0,1,3,"El valor de alarma debe ser mayor al valor de advertencia"
      }else if(sys0==1)
      {
        xstr 150,400,250,35,6,RED,color,0,1,3,"Il valore dell'allarme deve essere maggiore del valore dell'avviso"
      }else if(sys0==2)
      {
        xstr 150,400,250,35,6,RED,color,0,1,3,"La valeur d'alarme doit être supérieure à la valeur d'avertissement"
      }else if(sys0==3)
      {
        xstr 150,400,250,35,6,RED,color,0,1,3,"The alarm value must be greater than the warning value"
      }else if(sys0==4)
      {
        xstr 150,400,250,35,6,RED,color,0,1,3,"Der Alarmwert muss größer als der Warnwert sein"
      }else if(sys0==5)
      {
        xstr 150,400,250,35,6,RED,color,0,1,3,"O valor do alarme deve ser maior que o valor do aviso"
      }
      delay=1500
      page Limites3
    }

Touch press event m2
--------------------

.. code-block:: javascript

    cirs 500,100,20,fondo
    cirs 540,100,20,fondo
    cirs 500,140,20,fondo
    cirs 540,140,20,fondo
    line 500,80,540,80,fondo
    line 500,160,540,160,fondo
    line 480,100,480,140,fondo
    line 560,100,560,140,fondo
    fill 500,80,40,80,fondo
    fill 480,100,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="1"
    }else if(tselected.val==1)
    {
      t1.txt+="1"
    }

Touch release event m2
----------------------

.. code-block:: javascript

    //1
    cirs 500,100,20,button.val
    cirs 540,100,20,button.val
    cirs 500,140,20,button.val
    cirs 540,140,20,button.val
    line 500,80,540,80,button.val
    line 500,160,540,160,button.val
    line 480,100,480,140,button.val
    line 560,100,560,140,button.val
    fill 500,80,40,80,button.val
    fill 480,100,80,40,button.val
    xstr 500,90,40,90,1,fontColor.val,button.val,1,0,3,"1"

Touch press event m3
--------------------

.. code-block:: javascript

    cirs 600,100,20,fondo
    cirs 640,100,20,fondo
    cirs 600,140,20,fondo
    cirs 640,140,20,fondo
    line 600,80,640,80,fondo
    line 600,160,640,160,fondo
    line 580,100,580,140,fondo
    line 660,100,660,140,fondo
    fill 600,80,40,80,fondo
    fill 580,100,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="2"
    }else if(tselected.val==1)
    {
      t1.txt+="2"
    }

Touch release event m3
----------------------

.. code-block:: javascript

    //2
    cirs 600,100,20,button.val
    cirs 640,100,20,button.val
    cirs 600,140,20,button.val
    cirs 640,140,20,button.val
    line 600,80,640,80,button.val
    line 600,160,640,160,button.val
    line 580,100,580,140,button.val
    line 660,100,660,140,button.val
    fill 600,80,40,80,button.val
    fill 580,100,80,40,button.val
    xstr 600,90,40,90,1,fontColor.val,button.val,1,0,3,"2"

Touch press event m4
--------------------

.. code-block:: javascript

    cirs 700,100,20,fondo
    cirs 740,100,20,fondo
    cirs 700,140,20,fondo
    cirs 740,140,20,fondo
    line 700,80,740,80,fondo
    line 700,160,740,160,fondo
    line 680,100,680,140,fondo
    line 760,100,760,140,fondo
    fill 700,80,40,80,fondo
    fill 680,100,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="3"
    }else if(tselected.val==1)
    {
      t1.txt+="3"
    }

Touch release event m4
----------------------

.. code-block:: javascript

    //3
    cirs 700,100,20,button.val
    cirs 740,100,20,button.val
    cirs 700,140,20,button.val
    cirs 740,140,20,button.val
    line 700,80,740,80,button.val
    line 700,160,740,160,button.val
    line 680,100,680,140,button.val
    line 760,100,760,140,button.val
    fill 700,80,40,80,button.val
    fill 680,100,80,40,button.val
    xstr 700,90,40,90,1,fontColor.val,button.val,1,0,3,"3"

Touch press event m5
--------------------

.. code-block:: javascript

    cirs 500,200,20,fondo
    cirs 540,200,20,fondo
    cirs 500,240,20,fondo
    cirs 540,240,20,fondo
    line 500,180,540,180,fondo
    line 500,260,540,260,fondo
    line 480,200,480,240,fondo
    line 560,200,560,240,fondo
    fill 500,180,40,80,fondo
    fill 480,200,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="4"
    }else if(tselected.val==1)
    {
      t1.txt+="4"
    }

Touch release event m5
----------------------

.. code-block:: javascript

    //4
    cirs 500,200,20,button.val
    cirs 540,200,20,button.val
    cirs 500,240,20,button.val
    cirs 540,240,20,button.val
    line 500,180,540,180,button.val
    line 500,260,540,260,button.val
    line 480,200,480,240,button.val
    line 560,200,560,240,button.val
    fill 500,180,40,80,button.val
    fill 480,200,80,40,button.val
    xstr 500,190,40,90,1,fontColor.val,button.val,1,0,3,"4"

Touch press event m6
--------------------

.. code-block:: javascript

    cirs 600,200,20,fondo
    cirs 640,200,20,fondo
    cirs 600,240,20,fondo
    cirs 640,240,20,fondo
    line 600,180,640,180,fondo
    line 600,260,640,260,fondo
    line 580,200,580,240,fondo
    line 660,200,660,240,fondo
    fill 600,180,40,80,fondo
    fill 580,200,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="5"
    }else if(tselected.val==1)
    {
      t1.txt+="5"
    }

Touch release event m6
----------------------

.. code-block:: javascript

    //5
    cirs 600,200,20,button.val
    cirs 640,200,20,button.val
    cirs 600,240,20,button.val
    cirs 640,240,20,button.val
    line 600,180,640,180,button.val
    line 600,260,640,260,button.val
    line 580,200,580,240,button.val
    line 660,200,660,240,button.val
    fill 600,180,40,80,button.val
    fill 580,200,80,40,button.val
    xstr 600,190,40,90,1,fontColor.val,button.val,1,0,3,"5"

Touch press event m7
--------------------

.. code-block:: javascript

    cirs 700,200,20,fondo
    cirs 740,200,20,fondo
    cirs 700,240,20,fondo
    cirs 740,240,20,fondo
    line 700,180,740,180,fondo
    line 700,260,740,260,fondo
    line 680,200,680,240,fondo
    line 760,200,760,240,fondo
    fill 700,180,40,80,fondo
    fill 680,200,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="6"
    }else if(tselected.val==1)
    {
      t1.txt+="6"
    }

Touch release event m7
----------------------

.. code-block:: javascript

    //6
    cirs 700,200,20,button.val
    cirs 740,200,20,button.val
    cirs 700,240,20,button.val
    cirs 740,240,20,button.val
    line 700,180,740,180,button.val
    line 700,260,740,260,button.val
    line 680,200,680,240,button.val
    line 760,200,760,240,button.val
    fill 700,180,40,80,button.val
    fill 680,200,80,40,button.val
    xstr 700,190,40,90,1,fontColor.val,button.val,1,0,3,"6"

Touch press event m8
--------------------

.. code-block:: javascript

    cirs 500,300,20,fondo
    cirs 540,300,20,fondo
    cirs 500,340,20,fondo
    cirs 540,340,20,fondo
    line 500,280,540,280,fondo
    line 500,360,540,360,fondo
    line 480,300,480,340,fondo
    line 560,300,560,340,fondo
    fill 500,280,40,80,fondo
    fill 480,300,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="7"
    }else if(tselected.val==1)
    {
      t1.txt+="7"
    }

Touch release event m8
----------------------

.. code-block:: javascript

    //7
    cirs 500,300,20,button.val
    cirs 540,300,20,button.val
    cirs 500,340,20,button.val
    cirs 540,340,20,button.val
    line 500,280,540,280,button.val
    line 500,360,540,360,button.val
    line 480,300,480,340,button.val
    line 560,300,560,340,button.val
    fill 500,280,40,80,button.val
    fill 480,300,80,40,button.val
    xstr 500,290,40,90,1,fontColor.val,button.val,1,0,3,"7"

Touch press event m9
--------------------

.. code-block:: javascript

    cirs 600,300,20,fondo
    cirs 640,300,20,fondo
    cirs 600,340,20,fondo
    cirs 640,340,20,fondo
    line 600,280,640,280,fondo
    line 600,360,640,360,fondo
    line 580,300,580,340,fondo
    line 660,300,660,340,fondo
    fill 600,280,40,80,fondo
    fill 580,300,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="8"
    }else if(tselected.val==1)
    {
      t1.txt+="8"
    }

Touch release event m9
----------------------

.. code-block:: javascript

    //8
    cirs 600,300,20,button.val
    cirs 640,300,20,button.val
    cirs 600,340,20,button.val
    cirs 640,340,20,button.val
    line 600,280,640,280,button.val
    line 600,360,640,360,button.val
    line 580,300,580,340,button.val
    line 660,300,660,340,button.val
    fill 600,280,40,80,button.val
    fill 580,300,80,40,button.val
    xstr 600,290,40,90,1,fontColor.val,button.val,1,0,3,"8"

Touch press event m10
---------------------

.. code-block:: javascript

    cirs 700,300,20,fondo
    cirs 740,300,20,fondo
    cirs 700,340,20,fondo
    cirs 740,340,20,fondo
    line 700,280,740,280,fondo
    line 700,360,740,360,fondo
    line 680,300,680,340,fondo
    line 760,300,760,340,fondo
    fill 700,280,40,80,fondo
    fill 680,300,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="9"
    }else if(tselected.val==1)
    {
      t1.txt+="9"
    }

Touch release event m10
-----------------------

.. code-block:: javascript

    //9
    cirs 700,300,20,button.val
    cirs 740,300,20,button.val
    cirs 700,340,20,button.val
    cirs 740,340,20,button.val
    line 700,280,740,280,button.val
    line 700,360,740,360,button.val
    line 680,300,680,340,button.val
    line 760,300,760,340,button.val
    fill 700,280,40,80,button.val
    fill 680,300,80,40,button.val
    xstr 700,290,40,90,1,fontColor.val,button.val,1,0,3,"9"

Touch press event m11
---------------------

.. code-block:: javascript

    cirs 500,400,20,fondo
    cirs 540,400,20,fondo
    cirs 500,440,20,fondo
    cirs 540,440,20,fondo
    line 500,380,540,380,fondo
    line 500,460,540,460,fondo
    line 480,400,480,440,fondo
    line 560,400,560,440,fondo
    fill 500,380,40,80,fondo
    fill 480,400,80,40,fondo

Touch release event m11
-----------------------

.. code-block:: javascript

    //#
    cirs 500,400,20,button.val
    cirs 540,400,20,button.val
    cirs 500,440,20,button.val
    cirs 540,440,20,button.val
    line 500,380,540,380,button.val
    line 500,460,540,460,button.val
    line 480,400,480,440,button.val
    line 560,400,560,440,button.val
    fill 500,380,40,80,button.val
    fill 480,400,80,40,button.val

Touch press event m12
---------------------

.. code-block:: javascript

    cirs 600,400,20,fondo
    cirs 640,400,20,fondo
    cirs 600,440,20,fondo
    cirs 640,440,20,fondo
    line 600,380,640,380,fondo
    line 600,460,640,460,fondo
    line 580,400,580,440,fondo
    line 660,400,660,440,fondo
    fill 600,380,40,80,fondo
    fill 580,400,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt+="0"
    }else if(tselected.val==1)
    {
      t1.txt+="0"
    }

Touch release event m12
-----------------------

.. code-block:: javascript

    //0
    cirs 600,400,20,button.val
    cirs 640,400,20,button.val
    cirs 600,440,20,button.val
    cirs 640,440,20,button.val
    line 600,380,640,380,button.val
    line 600,460,640,460,button.val
    line 580,400,580,440,button.val
    line 660,400,660,440,button.val
    fill 600,380,40,80,button.val
    fill 580,400,80,40,button.val
    xstr 600,390,40,90,1,fontColor.val,button.val,1,0,3,"0"

Touch press event m13
---------------------

.. code-block:: javascript

    cirs 700,400,20,fondo
    cirs 740,400,20,fondo
    cirs 700,440,20,fondo
    cirs 740,440,20,fondo
    line 700,380,740,380,fondo
    line 700,460,740,460,fondo
    line 680,400,680,440,fondo
    line 760,400,760,440,fondo
    fill 700,380,40,80,fondo
    fill 680,400,80,40,fondo
    //
    if(tselected.val==0)
    {
      t0.txt-=1
    }else if(tselected.val==1)
    {
      t1.txt-=1
    }

Touch release event m13
-----------------------

.. code-block:: javascript

    //x
    cirs 700,400,20,button.val
    cirs 740,400,20,button.val
    cirs 700,440,20,button.val
    cirs 740,440,20,button.val
    line 700,380,740,380,button.val
    line 700,460,740,460,button.val
    line 680,400,680,440,button.val
    line 760,400,760,440,button.val
    fill 700,380,40,80,button.val
    fill 680,400,80,40,button.val
    xstr 700,385,40,90,1,fontColor.val,button.val,1,0,3,"x"

Touch press event bInfoL
------------------------

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

Touch release event bInfoL
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

Touch press event bHomeL
------------------------

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

Touch release event bHomeL
--------------------------

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

Touch press event bBackL
------------------------

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

Touch release event bBackL
--------------------------

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
    page MenuConf

