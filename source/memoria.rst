Memoria Nextion Page
============================

Description
-----------

Introduction
------------

This script defines the layout and elements of a graphical user interface (GUI). It includes a navigation drawer, page title, and multiple containers for displaying various information. Each section of the script is explained below.

Navigation Drawer
-------------------

This section defines the appearance of a navigation drawer, typically containing icons or navigation options. It includes:

- Four circular icons (`cirs`) with specified coordinates, radii, and colors.
- Four lines (`line`) that outline the drawer.
- Two filled rectangles (`fill`) to color specific areas within the drawer.

Page Title
----------

Defines the appearance of the page title at the top of the GUI, including:

- Two circular elements (`cirs`) for decorative purposes.
- Two lines (`line`) forming a border around the title.
- One filled rectangle (`fill`) to provide a background color for the title area.

Containers
----------

This section creates multiple containers, each containing circular elements, lines, and filled rectangles to organize and display different types of information. There are six containers in total, and each follows a similar structure:

- Four circular elements (`cirs`) with specified coordinates, radii, and colors.
- Two lines (`line`) for the top and bottom boundaries of the container.
- Filled rectangles (`fill`) to create background areas within the container.
- Additional lines and filled rectangles inside the container to further organize content.

Navigation Drawer Icons
-----------------------

This part dynamically displays icons based on the value of the `fondo` variable. The icons change to reflect different themes. It includes conditional checks and the `pic` command to display theme-specific icons.

Page Text
---------

This section displays text content based on the `sys0` variable, determining the language. It includes conditional checks and the `xstr` command to display text with varying content, colors, and positions.

Custom Styling
--------------

The script sets the background color (`bco`) of various elements based on the `color` variable. This likely affects the overall color scheme of the GUI.

Conclusion
----------

This script is designed to create a GUI with a navigation drawer, page title, and multiple containers for displaying information. The layout and appearance of these elements are defined with specific coordinates, sizes, and colors, making it suitable for interactive applications.

Please note that the script assumes variable values, such as `fondo`, `sys0`, and `color`, which may affect the appearance and behavior of the GUI elements. The script's execution and functionality may depend on the integration with a compatible platform or application.

Preinitialize event Memoria
---------------------------

.. code-block:: javascript

    // Changes the page's background color
    Memoria.bco=fondo
    // Sends the current page's id over serial
    sendme

Postinitialize event Memoria
----------------------------

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
    //Page title start
    cirs 300,40,30,color
    cirs 550,40,30,color
    line 300,10,550,10,color
    line 300,70,550,70,color
    fill 300,10,250,60,color
    //Page title end
    //Containers start
    //First container
    cirs 150,110,30,color
    cirs 300,110,30,color
    cirs 150,170,30,color
    cirs 300,170,30,color
    line 150,80,300,80,color
    line 150,200,300,200,color
    fill 150,80,150,120,color
    line 120,110,120,170,color
    fill 120,110,30,60,color
    line 330,110,330,170,color
    fill 300,110,30,60,color
    //Second container
    cirs 380,110,30,color
    cirs 530,110,30,color
    cirs 380,170,30,color
    cirs 530,170,30,color
    line 380,80,530,80,color
    line 380,200,530,200,color
    fill 380,80,150,120,color
    line 350,110,350,170,color
    fill 350,110,30,60,color
    line 560,110,560,170,color
    fill 530,110,30,60,color
    //Third container
    cirs 610,110,30,color
    cirs 760,110,30,color
    cirs 610,170,30,color
    cirs 760,170,30,color
    line 610,80,760,80,color
    line 610,200,760,200,color
    fill 610,80,150,120,color
    line 580,110,580,170,color
    fill 580,110,30,60,color
    line 790,110,790,170,color
    fill 760,110,30,60,color
    //Fourth container
    cirs 150,240,30,color
    cirs 300,240,30,color
    cirs 150,300,30,color
    cirs 300,300,30,color
    line 150,210,300,210,color
    line 150,330,300,330,color
    fill 150,210,150,120,color
    line 120,240,120,300,color
    fill 120,240,30,60,color
    line 330,240,330,300,color
    fill 300,240,30,60,color
    //Fifth container
    cirs 380,240,30,color
    cirs 530,240,30,color
    cirs 380,300,30,color
    cirs 530,300,30,color
    line 380,210,530,210,color
    line 380,330,530,330,color
    fill 380,210,150,120,color
    line 350,240,350,300,color
    fill 350,240,30,60,color
    line 560,240,560,300,color
    fill 530,240,30,60,color
    //Sixth container
    cirs 610,240,30,color
    cirs 760,240,30,color
    cirs 610,300,30,color
    cirs 760,300,30,color
    line 610,210,760,210,color
    line 610,330,760,330,color
    fill 610,210,150,120,color
    line 580,240,580,300,color
    fill 580,240,30,60,color
    line 790,240,790,300,color
    fill 760,240,30,60,color
    //Seventh container
    cirs 150,370,30,color
    cirs 300,370,30,color
    cirs 150,430,30,color
    cirs 300,430,30,color
    line 150,340,300,340,color
    line 150,460,300,460,color
    fill 150,340,150,120,color
    line 120,370,120,430,color
    fill 120,370,30,60,color
    line 330,370,330,430,color
    fill 300,370,30,60,color
    //Containers end
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
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Memoria"
      xstr 150,90,150,25,0,fontColor.val,color,0,1,3,"Memoria RAM (bytes)"
      xstr 380,90,150,25,0,fontColor.val,color,0,1,3,"Memoria Total (bytes)"
      xstr 610,90,150,35,0,fontColor.val,color,0,1,3,"Memoria disponible sketch (bytes)"
      xstr 150,220,150,35,0,fontColor.val,color,0,1,3,"Entradas disponibles(preferences)"
      xstr 380,220,150,35,0,fontColor.val,color,0,1,3,"Entradas disponibles(register1)"
      xstr 610,220,150,35,0,fontColor.val,color,0,1,3,"Entradas disponibles(events)"
      xstr 150,350,150,35,0,fontColor.val,color,0,1,3,"Serial buffer(bytes)"
    }else if(sys0==1)
    {
      //Italian
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Memoria"
      xstr 150,90,150,25,0,fontColor.val,color,0,1,3,"Memoria RAM (bytes)"
      xstr 380,90,150,25,0,fontColor.val,color,0,1,3,"Memoria totale (byte)"
      xstr 610,90,150,35,0,fontColor.val,color,0,1,3,"Memoria per schizzi disponibile (byte)"
      xstr 150,220,150,35,0,fontColor.val,color,0,1,3,"Biglietti disponibili (preferenze)"
      xstr 380,220,150,35,0,fontColor.val,color,0,1,3,"Biglietti disponibili(registrati1)"
      xstr 610,220,150,35,0,fontColor.val,color,0,1,3,"Biglietti disponibili(eventi)"
      xstr 150,350,150,35,0,fontColor.val,color,0,1,3,"Serial buffer(bytes)"
    }else if(sys0==2)
    {
      //French
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Mémoire"
      xstr 150,90,150,25,0,fontColor.val,color,0,1,3,"Mémoire RAM (bytes)"
      xstr 380,90,150,25,0,fontColor.val,color,0,1,3,"Mémoire totale (bytes)"
      xstr 610,90,150,35,0,fontColor.val,color,0,1,3,"Mémoire de croquis disponible (bytes)"
      xstr 150,220,150,35,0,fontColor.val,color,0,1,3,"Billets disponibles (préférences)"
      xstr 380,220,150,35,0,fontColor.val,color,0,1,3,"Billets disponibles(register1)"
      xstr 610,220,150,35,0,fontColor.val,color,0,1,3,"Billets disponibles (événements)"
      xstr 150,350,150,35,0,fontColor.val,color,0,1,3,"Serial buffer(bytes)"
    }else if(sys0==3)
    {
      //English
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Memory"
      xstr 150,90,150,25,0,fontColor.val,color,0,1,3,"RAM memory (bytes)"
      xstr 380,90,150,25,0,fontColor.val,color,0,1,3,"Total Memory (bytes)"
      xstr 610,90,150,35,0,fontColor.val,color,0,1,3,"Available sketch memory (bytes)"
      xstr 150,220,150,35,0,fontColor.val,color,0,1,3,"Space available(preferences)"
      xstr 380,220,150,35,0,fontColor.val,color,0,1,3,"Space available(register1)"
      xstr 610,220,150,35,0,fontColor.val,color,0,1,3,"Space available(events)"
      xstr 150,350,150,35,0,fontColor.val,color,0,1,3,"Serial buffer(bytes)"
    }else if(sys0==4)
    {
      //German
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Speicher"
      xstr 150,90,150,25,0,fontColor.val,color,0,1,3,"RAM-Speicher (Byte)"
      xstr 380,90,150,25,0,fontColor.val,color,0,1,3,"Gesamtspeicher (Byte)"
      xstr 610,90,150,35,0,fontColor.val,color,0,1,3,"Verfügbarer Skizzenspeicher (Byte)"
      xstr 150,220,150,35,0,fontColor.val,color,0,1,3,"Tickets verfügbar (Präferenzen)"
      xstr 380,220,150,35,0,fontColor.val,color,0,1,3,"Verfügbare Tickets(registrieren1)"
      xstr 610,220,150,35,0,fontColor.val,color,0,1,3,"Tickets erhältlich (Veranstaltungen)"
      xstr 150,350,150,35,0,fontColor.val,color,0,1,3,"Serial buffer(bytes)"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 355,25,140,25,4,fontColor.val,color,1,1,3,"Memória"
      xstr 150,90,150,25,0,fontColor.val,color,0,1,3,"Memória RAM (bytes)"
      xstr 380,90,150,25,0,fontColor.val,color,0,1,3,"Memória total (bytes)"
      xstr 610,90,150,35,0,fontColor.val,color,0,1,3,"Memória de esboço disponível (bytes)"
      xstr 150,220,150,35,0,fontColor.val,color,0,1,3,"Ingressos disponíveis (preferências)"
      xstr 380,220,150,35,0,fontColor.val,color,0,1,3,"Ingressos disponíveis (cadastro1)"
      xstr 610,220,150,35,0,fontColor.val,color,0,1,3,"Ingressos disponíveis (eventos)"
      xstr 150,350,150,35,0,fontColor.val,color,0,1,3,"Serial buffer(bytes)"
    }
    //Page text end
    tmem1.bco=color
    tmem2.bco=color
    tmem3.bco=color
    tmem4.bco=color
    tmem5.bco=color
    tmem6.bco=color
    n0.bco=color

Touch press event bInfoMe
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

Touch release event bInfoMe
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
    page Pantalla
