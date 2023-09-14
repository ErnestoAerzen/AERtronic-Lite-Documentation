Info Nextion Page
============================

Description
-----------

Overview
--------

This document provides a comprehensive explanation of the Nextion display script created for a user interface. The script is designed for use with the Nextion Editor and consists of several sections that define graphical elements, conditional logic, and text content to create an informative and visually appealing interface.

Script Structure
----------------

The script is organized into multiple sections, each serving a specific purpose within the user interface:

**Nav Drawer**
~~~~~~~~~~~~~~~~

This section defines a navigation drawer, a common UI element that typically appears on the side of the display. It consists of circular elements ("cirs") positioned strategically for navigation, lines ("line") to separate them, and rectangular areas ("fill") to enhance the visual aesthetics.

**Nav Drawer Icons**
~~~~~~~~~~~~~~~~~~~~

Conditional logic is employed in this section to customize the icons displayed in the navigation drawer based on the value of the "fondo" variable. Different themes are applied, each with its set of icons and colors, contributing to the overall user experience.

**Main Container**
~~~~~~~~~~~~~~~~~~

The "Main Container" section defines a prominent central area on the display. It includes circular elements ("cirs") at specific locations, lines ("line") to create boundaries, and rectangular areas ("fill") to provide background colors. This container serves as the primary content area for the interface.

**Page Title**
~~~~~~~~~~~~~~~~

In this section, two circular elements ("cirs") are defined at the top of the display, creating a visually distinct title area. The use of lines ("line") separates these elements, and a colored background is applied using the "fill" command.

**Language Selection**
~~~~~~~~~~~~~~~~~~~~~~

The script uses conditional logic to adapt the displayed text based on the selected language, determined by the "sys0" variable. Language-specific labels for the interface are defined, allowing users to access information in their preferred language.

**Additional Information**
~~~~~~~~~~~~~~~~~~~~~~~~~~

- The "Aerzen text" section defines a text element with the company's name and location information, contributing to the informational aspect of the interface.

- Contact information is also provided, including the company's address, phone number, fax number, email address, and website. This information serves as a reference for users who may need to contact the company.

- Software and hardware version details are displayed using the "xstr" command, providing essential information about the software and hardware components.

- A QR code image is positioned at a specific location on the display using the "pic" command. This may serve as a quick link or reference for users.

Usage
-----

This script is intended for use with the Nextion Editor, a visual interface design tool for Nextion displays. To effectively implement this script, ensure that the Nextion display is correctly configured to handle the defined variables and commands.

The primary purpose of this script is to create an interactive and informative user interface on the Nextion display. Users can navigate the interface using the navigation drawer, access information in their preferred language, and find essential contact details.

For specific implementation instructions, refer to the Nextion Editor documentation and the user manual for the Nextion display.

Contributors
------------

- [Your Name/Team Name]

Version History
---------------

- Version 1.0: [Date of Initial Release]

Disclaimer
-----------

[Include any necessary disclaimers or legal information here.]

**Note:** This documentation may undergo updates and improvements as needed.

For the most up-to-date information and documentation, refer to the official Nextion Display resources.

Preinitialize event Info
------------------------

.. code-block:: javascript

    // Changes the background color of the page
    Info.bco=fondo
    // Custom command to stop serial comm in this page. See the README.md file to learn more.
    printh 52 FE FF FF FF

Postinitialize event Info
-------------------------

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
    //Main container start
    cirs 170,120,30,color
    cirs 730,120,30,color
    line 170,90,730,90,color
    cirs 170,360,30,color
    cirs 730,360,30,color
    line 170,390,730,390,color
    line 140,120,140,360,color
    line 760,120,760,360,color
    fill 170,90,560,300,color
    fill 140,120,30,240,color
    fill 730,120,30,240,color
    //Main container end
    //Page title start
    cirs 380,40,30,color
    cirs 520,40,30,color
    line 380,10,520,10,color
    line 380,70,520,70,color
    fill 380,10,140,60,color
    //Page title end
    if(sys0==0)
    {
      //Spanish
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Información"
    }else if(sys0==1)
    {
      //Italian
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Informazione"
    }else if(sys0==2)
    {
      //French
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Informations"
    }else if(sys0==3)
    {
      //English
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Information"
    }else if(sys0==4)
    {
      //German
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Information"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 380,25,140,25,4,fontColor.val,color,1,1,3,"Informação"
    }
    //Page tiltle end
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

Touch press event bInfoI
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

Touch release event bInfoI
--------------------------

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

Touch press event bHomeI
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

Touch release event bhomeI
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

Touch press event bBackI
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

Touch release event bBackI
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
    page returnPage.val
    