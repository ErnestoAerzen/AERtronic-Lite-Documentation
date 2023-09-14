MachineParam Nextion Page
============================

Description
-----------

Introduction
------------

This script defines the layout and elements of a graphical user interface (GUI). It consists of a navigation drawer, navigation drawer icons, a page title, page text, Aerzen text, contact information, and a QR picture. Each section of the script is explained below.

Navigation Drawer
----------------

This section defines the appearance of a navigation drawer, which typically contains icons or navigation options. It includes:

- Four circular icons (`cirs`) with specified coordinates, radii, and colors.
- Four lines (`line`) that outline the drawer.
- Two filled rectangles (`fill`) to color specific areas within the drawer.

Navigation Drawer Icons
-----------------------

This part dynamically displays icons based on the value of the `fondo` variable. The icons change to reflect different themes. It includes conditional checks and the `pic` command to display theme-specific icons.

Page Title
----------

Defines the appearance of the page title at the top of the GUI, including:

- Two circular elements (`cirs`) for decorative purposes.
- Two lines (`line`) forming a border around the title.
- One filled rectangle (`fill`) to provide a background color for the title area.

Page Text
---------

This section displays text content based on the `sys0` variable, determining the language. It includes conditional checks and the `xstr` command to display text with varying content, colors, and positions.

Aerzen Text
-----------

Displays specific text content for Aerzen Mexico SA de CV. It includes the company name and address, phone number, fax, email, and website information.

Contact Info
------------

Provides contact information, including the company's address, phone number, fax, email, and website.

QR Picture
----------

Displays a QR code image using the `pic` command.

Conclusion
----------

This script is designed to create a GUI with various elements, such as buttons, icons, text, and contact information. The layout and appearance of these elements are defined with specific coordinates, sizes, colors, and conditions, making it suitable for interactive applications.

Please note that the script assumes variable values, such as `fondo` and `sys0`, which may affect the appearance and behavior of the GUI elements. The script's execution and functionality may depend on the integration with a compatible platform or application.

Preinitialize event MachineParam
--------------------------------

.. code-block:: javascript

    // Changes the background color
    MachineParam.bco=fondo

Postinitialize event MachineParam
---------------------------------

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
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Parámetros de la maquina"
    }else if(sys0==1)
    {
      //Italian
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Parametri macchina"
    }else if(sys0==2)
    {
      //French
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Paramètres machines"
    }else if(sys0==3)
    {
      //English
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Machine parameters"
    }else if(sys0==4)
    {
      //German
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Maschinenparameter"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 325,25,200,25,4,fontColor.val,color,1,1,3,"Parâmetros da máquina"
    }
    //Aerzen text
    xstr 170,100,250,35,4,fontColor.val,65535,0,1,3,"Aerzen México SA de CV"
    //Contact info
    xstr 170,140,300,20,2,fontColor.val,65535,0,1,3,"Cerrada de Uniroyal 18-A, La Michoacana"
    xstr 170,160,255,20,2,fontColor.val,65535,0,1,3,"52166 Metepec, Mex."
    xstr 170,180,255,20,2,fontColor.val,65535,0,1,3,"Teléfono: +52 722 235  9400"
    xstr 170,200,255,20,2,fontColor.val,65535,0,1,3,"Fax: +52 722 235 9401"
    xstr 170,220,255,20,2,fontColor.val,65535,0,1,3,"Correo electrónico: info@aerzen.com"
    xstr 170,240,255,20,2,fontColor.val,65535,0,1,3,"Web: www.aerzen.com/es-mx"
    xstr 170,280,250,20,4,BLUE,65535,0,1,3,"AERtronic Basic"
    xstr 170,310,250,20,2,fontColor.val,65535,0,1,3,"Versión del software: V2.2"
    xstr 170,330,250,20,2,fontColor.val,65535,0,1,3,"Versión del hardware: V1.0"
    //QR Picture
    pic 500,120,168
    //Page text end

Touch press event bInfoMP
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

Touch release event bInfoMP
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

Touch press event bHomeMP
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

Touch release event bHomeMP
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

Touch press event bBackMP
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

Touch release event bBackMP
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
    page MenuConf