Mensajes Nextion Page
============================

Description
-----------

Introduction
============
This document provides a detailed explanation of a Nextion display script. The script is designed to be used with a Nextion display, a popular choice for creating graphical user interfaces in embedded systems.

Script Overview
===============
The provided script is written in Nextion Instruction Set (NXIS) language, which is used to control Nextion displays. It contains a series of commands that define the behavior and appearance of the user interface elements on the display.

Script Sections
---------------
The script can be divided into several sections, each with a specific purpose:

1. **Initialization**: The script starts with initialization commands to set the display's baud rate, page, and component attributes.

2. **Page Configuration**: This section configures the properties of the display's pages, including the background image and touch events.

3. **Component Definitions**: Here, the script defines various components like text fields, buttons, and images. Each component has a unique name and associated properties.

4. **Event Handling**: This section defines what happens when a user interacts with components, such as button press events triggering actions.

5. **Timers**: Timers are used to create time-based events, and this section sets up the timers and their associated actions.

6. **User-defined Functions**: Custom functions are defined to handle specific tasks or calculations.

Script Explanation
------------------
Now, let's provide a more detailed explanation of key sections and commands within the script:

Initialization
----------------
   - `baud=9600`: Sets the communication baud rate to 9600 bps.
   - `page 0`: Switches to page 0 of the display.

Page Configuration
---------------------

   - `pic0=0`: Sets picture component 0 to display a specific image.
   - `tsw 0,1,page2`: Configures touch event on component 0 to navigate to page2 when pressed.
   
Component Definitions
-----------------------

   - `t0.txt="Hello, World!"`: Sets the text of text component 0 to "Hello, World!".
   - `b0.pic=1`: Assigns picture 1 to button component 0.
   - `p0.pic=2`: Assigns picture 2 to picture component 0.

Event Handling
----------------

   - `page2.b0.en=0`: Disables button 0 on page2.
   - `page2.b1.en=1`: Enables button 1 on page2.
   - `click b0`: Defines an action when button 0 is clicked.
   
Timers
--------

   - `tm0.en=1`: Enables timer 0.
   - `tm0.tim=1000`: Sets timer 0's interval to 1000 milliseconds.
   - `tm0.val=100`: Sets an initial value for timer 0.

Conclusion
----------
This documentation provides an in-depth explanation of the Nextion display script, highlighting its sections, key commands, and their purposes. By understanding this script, developers can create customized user interfaces for Nextion displays, enhancing the interactivity of their embedded systems.

Preinitialize event Mensajes
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    Mensajes.bco=fondo
    // Sets the main color
    cbutton.val=0x3B44
    // Sends the current page's id
    sendme

Postinitialize event Mensajes
-----------------------------

.. code-block:: javascript

    //Disables touch components
    tsw bHomeMe,0
    tsw bBackMe,0
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
    //Acknowledge messages
    cirs 650,40,30,0x3B44
    cirs 760,40,30,0x3B44
    line 650,10,760,10,0x3B44
    line 650,70,760,70,0x3B44
    fill 650,10,110,60,0x3B44
    //Page title start
    cirs 380,40,30,color
    cirs 520,40,30,color
    line 380,10,520,10,color
    line 380,70,520,70,color
    fill 380,10,140,60,color
    if(sys0==0)
    {
      //Spanish
      xstr 380,25,140,25,4,BLACK,color,1,1,3,"Mensajes"
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Regresar"
    }else if(sys0==1)
    {
      //Italian
      xstr 380,25,140,25,4,BLACK,color,1,1,3,"Messaggi"
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Torna"
    }else if(sys0==2)
    {
      //French
      xstr 380,25,140,25,4,BLACK,color,1,1,3,"Messages"
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Retourner"
    }else if(sys0==3)
    {
      //English
      xstr 380,25,140,25,4,BLACK,color,1,1,3,"Messages"
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Back"
    }else if(sys0==4)
    {
      //German
      xstr 380,25,140,25,4,BLACK,color,1,1,3,"Mitteilungen"
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Geh zurück"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 380,25,140,25,4,BLACK,color,1,1,3,"Mensagens"
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Volte"
    }
    //Page title end
    //Nav Drawer icons start
    //Change the color of the info image according to the current state
    if(sys1==1)
    {
      if(fondo==65534)
      {
        //Font color
        fontColor.val=0
        //Theme 1
        pic 25,30,170
      }else if(fondo==63391)
      {
        //Font color
        fontColor.val=0
        //Theme 2
        pic 25,30,172
      }else if(fondo==65438)
      {
        //Font color
        fontColor.val=0
        //Theme 3
        pic 25,30,174
      }else if(fondo==63421)
      {
        //Font color
        fontColor.val=0
        //Theme 4
        pic 25,30,176
      }else if(fondo==6339)
      {
        //Font color
        fontColor.val=65535
        //Theme 5
        pic 25,30,178
      }else if(fondo==8484)
      {
        //Font color
        fontColor.val=65535
        //Theme 6
        pic 25,30,180
      }
    }else if(sys1==2)
    {
      if(fondo==65534)
      {
        //Font color
        fontColor.val=0
        //Theme 1
        pic 25,30,169
      }else if(fondo==63391)
      {
        //Font color
        fontColor.val=0
        //Theme 2
        pic 25,30,171
      }else if(fondo==65438)
      {
        //Font color
        fontColor.val=0
        //Theme 3
        pic 25,30,173
      }else if(fondo==63421)
      {
        //Font color
        fontColor.val=0
        //Theme 4
        pic 25,30,175
      }else if(fondo==6339)
      {
        //Font color
        fontColor.val=65535
        //Theme 5
        pic 25,30,177
      }else if(fondo==8484)
      {
        //Font color
        fontColor.val=65535
        //Theme 6
        pic 25,30,179
      }
    }else
    {
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
    }
    //Nav Drawer icons end
    if(fondo==65534)
    {
      //Font color
      fontColor.val=0
      //Theme 1
      pic 25,120,144
      pic 25,400,146
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,120,148
      pic 25,400,150
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,120,152
      pic 25,400,154
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,120,156
      pic 25,400,158
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,120,160
      pic 25,400,162
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,120,164
      pic 25,400,166
    }
    //Rectangles to display warnings and errors
    //Displays only if there are enough multiple errors or warnings
    if(box1>0)
    {
      //
      cirs 220,100,20,color
      cirs 680,100,20,color
      line 220,80,680,80,color
      line 220,120,680,120,color
      fill 220,80,460,40,color
    }
    if(box2>0)
    {
      //
      cirs 220,150,20,color
      cirs 680,150,20,color
      line 220,130,680,130,color
      line 220,170,680,170,color
      fill 220,130,460,40,color
    }
    if(box3>0)
    {
      //
      cirs 220,200,20,color
      cirs 680,200,20,color
      line 220,180,680,180,color
      line 220,220,680,220,color
      fill 220,180,460,40,color
    }
    if(box4>0)
    {
      //
      cirs 220,250,20,color
      cirs 680,250,20,color
      line 220,230,680,230,color
      line 220,270,680,270,color
      fill 220,230,460,40,color
    }
    if(box5>0)
    {
      //
      cirs 220,300,20,color
      cirs 680,300,20,color
      line 220,280,680,280,color
      line 220,320,680,320,color
      fill 220,280,460,40,color
    }
    if(box6>0)
    {
      //
      cirs 220,350,20,color
      cirs 680,350,20,color
      line 220,330,680,330,color
      line 220,370,680,370,color
      fill 220,330,460,40,color
    }
    if(box7>0)
    {
      //
      cirs 220,400,20,color
      cirs 680,400,20,color
      line 220,380,680,380,color
      line 220,420,680,420,color
      fill 220,380,460,40,color
    }
    if(box8>0)
    {
      //
      cirs 220,450,20,color
      cirs 680,450,20,color
      line 220,430,680,430,color
      line 220,470,680,470,color
      fill 220,430,460,40,color
    }
    //Messages
    //First text container
    if(box1==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box1==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box1==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box1==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box1==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box1==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box1==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box1==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Second box container
    if(box2==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box2==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box2==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box2==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box2==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box2==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box2==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box2==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,140,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Third box container
    if(box3==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box3==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box3==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box3==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box3==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box3==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box3==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box3==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,190,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Fourth text container
    if(box4==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box4==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box4==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box4==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box4==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box4==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box4==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box4==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,240,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Fifth text container
    if(box5==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box5==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box5==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box5==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box5==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box5==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box5==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,90,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box5==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,290,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Sixth text container
    if(box6==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box6==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box6==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box6==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box6==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box6==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box6==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box6==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,340,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Seventh text container
    if(box7==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box7==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box7==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box7==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box7==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box7==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box7==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box7==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,390,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //Eight text container
    if(box8==1)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarma presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Allarme di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Final pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Enddruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de pressão final"
      }
    }else if(box8==2)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Advertencia presión final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avviso di pressione finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avertissement de pression finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Final pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Enddruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Aviso de pressão final"
      }
    }else if(box8==3)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarma temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Allarme temperatura finale"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de température finale"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Final temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Endtemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura final"
      }
    }else if(box8==4)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura final"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avviso di fine temperatura"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avertissement de température de fin"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"End temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Temperaturwarnung beenden"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura final"
      }
    }else if(box8==5)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarma temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Allarme temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Oil temperature alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Öltemperaturalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de temperatura do óleo"
      }
    }else if(box8==6)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Advertencia temperatura del aceite"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avviso temperatura olio"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avertissement de température d'huile"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Oil temperature warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Öltemperaturwarnung"
      }else if(sys0==5)
      {
        //Portuguse
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Aviso de temperatura do óleo"
      }
    }else if(box8==7)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarma presión de aspiración"
      }else if(sys0==31)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Allarme pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Suction pressure alarm"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Saugdruckalarm"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Alarme de pressão de sucção"
      }
    }else if(box8==8)
    {
      if(sys0==0)
      {
        //Spanish
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Advertencia presión de aspiración"
      }else if(sys0==1)
      {
        //Italian
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avviso di pressione di aspirazione"
      }else if(sys0==2)
      {
        //French
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Avertissement de pression d'aspiration"
      }else if(sys0==3)
      {
        //English
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Suction pressure warning"
      }else if(sys0==4)
      {
        //German
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Saugdruckwarnung"
      }else if(sys0==5)
      {
        //Portuguese
        xstr 400,440,300,25,6,BLACK,color,0,1,3,"Aviso de pressão de sucção"
      }
    }
    //
    timeT1.bco=fondo
    timeT2.bco=fondo
    timeT3.bco=fondo
    timeT4.bco=fondo
    timeT5.bco=fondo
    timeT6.bco=fondo
    timeT7.bco=fondo
    timeT8.bco=fondo
    dateT1.bco=fondo
    dateT2.bco=fondo
    dateT3.bco=fondo
    dateT4.bco=fondo
    dateT5.bco=fondo
    dateT6.bco=fondo
    dateT7.bco=fondo
    dateT8.bco=fondo

Touch press event m0
--------------------

.. code-block:: javascript

    //Acknowledge messages
    cirs 650,40,30,fondo
    cirs 760,40,30,fondo
    line 650,10,760,10,fondo
    line 650,70,760,70,fondo
    fill 650,10,110,60,fondo

Touch release event m0
----------------------

.. code-block:: javascript

    //Acknowledge messages
    cirs 650,40,30,0x3B44
    cirs 760,40,30,0x3B44
    line 650,10,760,10,0x3B44
    line 650,70,760,70,0x3B44
    fill 650,10,110,60,0x3B44
    if(sys0==0)
    {
      //Spanish
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Regresar"
    }else if(sys0==1)
    {
      //Italian
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Torna"
    }else if(sys0==2)
    {
      //French
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Retourner"
    }else if(sys0==3)
    {
      //English
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Back"
    }else if(sys0==4)
    {
      //German
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Geh zurück"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 645,25,120,25,4,65535,0x3B44,1,1,3,"Volte"
    }
    //Send reset messages command
    printh 43 EE FF FF FF
    //Resets the system status
    sys1=0
    //Resets text box
    box1=0
    box2=0
    box3=0
    box4=0
    box5=0
    box6=0
    box7=0
    box8=0
    //
    page Popup

Touch press event bHomeMe
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

Touch release event bHomeMe
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

Touch press event bBackMe
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

Touch release event bBackMe
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
    page Home

Timer event tm1
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box1 depending if there is a warning or error:
    if(box1>0)
    {
      if(box1==1||box1==3||box1==5||box1==7)
      {
        tm1.en=1
        tm1.tim=500
        //blinking red to show an error
        cirs 220,100,20,t1red.val
        t1red.val=t1red.val+20187
        if(t1red.val>65534)
        {
          t1red.val=45347
        }
      }else if(box1==2||box1==4||box1==6||box1==8)
      {
        tm1.en=1
        tm1.tim=500
        //blinking yellow color to show a warning
        cirs 220,100,20,t1yellow.val
        t1yellow.val=t1yellow.val+6903
        if(t1yellow.val>65534)
        {
          t1yellow.val=58631
        }
      }
    }

Timer event tm2
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box2 depending if there is a warning or error:
    if(box2>0)
    {
      if(box2==1||box2==3||box2==5||box2==7)
      {
        tm2.en=1
        tm2.tim=500
        //blinking red to show an error
        cirs 220,150,20,t2red.val
        t2red.val=t2red.val+20187
        if(t2red.val>65534)
        {
          t2red.val=45347
        }
      }else if(box2==2||box2==4||box2==6||box2==8)
      {
        tm2.en=1
        tm2.tim=500
        //blinking yellow color to show a warning
        cirs 220,150,20,t2yellow.val
        t2yellow.val=t2yellow.val+6903
        if(t2yellow.val>65534)
        {
          t2yellow.val=58631
        }
      }
    }

Timer event tm3
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box3 depending if there is a warning or error:
    if(box3>0)
    {
      if(box3==1||box3==3||box3==5||box3==7)
      {
        tm3.en=1
        tm3.tim=500
        //blinking red to show an error
        cirs 220,200,20,t3red.val
        t3red.val=t3red.val+20187
        if(t3red.val>65534)
        {
          t3red.val=45347
        }
      }else if(box3==2||box3==4||box3==6||box3==8)
      {
        tm3.en=1
        tm3.tim=500
        //blinking yellow color to show a warning
        cirs 220,200,20,t3yellow.val
        t3yellow.val=t3yellow.val+6903
        if(t3yellow.val>65534)
        {
          t3yellow.val=58631
        }
      }
    }

Timer event tm4
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box4 depending if there is a warning or error:
    if(box4>0)
    {
      if(box4==1||box4==3||box4==5||box4==7)
      {
        tm4.en=1
        tm4.tim=500
        //blinking red to show an error
        cirs 220,250,20,t4red.val
        t4red.val=t4red.val+20187
        if(t4red.val>65534)
        {
          t4red.val=45347
        }
      }else if(box4==2||box4==4||box4==6||box4==8)
      {
        tm4.en=1
        tm4.tim=500
        //blinking yellow color to show a warning
        cirs 220,250,20,t4yellow.val
        t4yellow.val=t4yellow.val+6903
        if(t4yellow.val>65534)
        {
          t4yellow.val=58631
        }
      }
    }

Timer event tm5
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box5 depending if there is a warning or error:
    if(box5>0)
    {
      if(box5==1||box5==3||box5==5||box5==7)
      {
        tm5.en=1
        tm5.tim=500
        //blinking red to show an error
        cirs 220,300,20,t5red.val
        t5red.val=t5red.val+20187
        if(t5red.val>65534)
        {
          t5red.val=45347
        }
      }else if(box5==2||box5==4||box5==6||box5==8)
      {
        tm5.en=1
        tm5.tim=500
        //blinking yellow color to show a warning
        cirs 220,300,20,t5yellow.val
        t5yellow.val=t5yellow.val+6903
        if(t5yellow.val>65534)
        {
          t5yellow.val=58631
        }
      }
    }

Timer event tm6
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box6 depending if there is a warning or error:
    if(box6>0)
    {
      if(box6==1||box6==3||box6==5||box6==7)
      {
        tm6.en=1
        tm6.tim=500
        //blinking red to show an error
        cirs 220,350,20,t6red.val
        t6red.val=t6red.val+20187
        if(t6red.val>65534)
        {
          t6red.val=45347
        }
      }else if(box6==2||box6==4||box6==6||box6==8)
      {
        tm6.en=1
        tm6.tim=500
        //blinking yellow color to show a warning
        cirs 220,350,20,t6yellow.val
        t6yellow.val=t6yellow.val+6903
        if(t6yellow.val>65534)
        {
          t6yellow.val=58631
        }
      }
    }

Timer event tm7
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box7 depending if there is a warning or error:
    if(box7>0)
    {
      if(box7==1||box7==3||box7==5||box7==7)
      {
        tm7.en=1
        tm7.tim=500
        //blinking red to show an error
        cirs 220,400,20,t7red.val
        t7red.val=t7red.val+20187
        if(t7red.val>65534)
        {
          t7red.val=45347
        }
      }else if(box7==2||box7==4||box7==6||box7==8)
      {
        tm7.en=1
        tm7.tim=500
        //blinking yellow color to show a warning
        cirs 220,400,20,t7yellow.val
        t7yellow.val=t7yellow.val+6903
        if(t7yellow.val>65534)
        {
          t7yellow.val=58631
        }
      }
    }

Timer event tm8
---------------

.. code-block:: javascript

    //Rutine to display a blinking color in box1 depending if there is a warning or error:
    if(box8>0)
    {
      if(box8==1||box8==3||box8==5||box8==7)
      {
        tm8.en=1
        tm8.tim=500
        //blinking red to show an error
        cirs 220,450,20,t8red.val
        t8red.val=t8red.val+20187
        if(t8red.val>65534)
        {
          t8red.val=45347
        }
      }else if(box8==2||box8==4||box8==6||box8==8)
      {
        tm8.en=1
        tm8.tim=500
        //blinking yellow color to show a warning
        cirs 220,450,20,t8yellow.val
        t8yellow.val=t8yellow.val+6903
        if(t8yellow.val>65534)
        {
          t8yellow.val=58631
        }
      }
    }