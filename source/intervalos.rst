Intervalos Nextion Page
============================

Description
-----------

Overview
--------

This document provides a detailed explanation of the Nextion display script, which is divided into several sections. The script is designed to enhance the user interface and functionality of a Nextion display. It includes components for creating a navigation drawer, customizing icons based on themes, displaying page titles, defining containers, and setting up textboxes.

Script Structure
----------------

The script comprises the following sections:

**Navigation Drawer (Nav Drawer)**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This section creates a navigation drawer with circular buttons, lines, and filled rectangles to define its appearance. The buttons and shapes are positioned at specific coordinates and use the "color" parameter for their appearance.

**Navigation Drawer Icons**
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Conditional logic is used to customize the icons within the navigation drawer based on the value of the "fondo" variable, which likely represents different themes. Each theme is associated with specific font colors and a unique set of icons. Icons are displayed using the "pic" command at defined coordinates (25, 30), (25, 120), and (25, 400), each with its respective index value.

Font colors for textboxes (tman1 to tman9) are also set based on the selected theme by modifying the "tmanX.pco" attribute.

**Page Title**
~~~~~~~~~~~~~~

This section defines a page title area with circular buttons and lines. The title area is visually separated from the navigation drawer. Buttons and shapes are positioned at specific coordinates and use the "color" parameter for their appearance.

**Containers**
~~~~~~~~~~~~~~

This section defines multiple containers, each comprising circular buttons, lines, and filled rectangles. These containers are organized into a grid layout. Each container is enclosed within lines, and filled rectangles visually distinguish the different sections. Buttons and shapes are positioned at specific coordinates and use the "color" parameter for their appearance.

**Page Text**
~~~~~~~~~~~~~

Text is displayed on the page using the "xstr" command. The displayed text varies based on the value of the "sys0" variable, which presumably represents different language options. For each language option, the script defines specific text content for the page titles and container sections.

**Textboxes**
~~~~~~~~~~~~~

This section customizes the appearance of textboxes (tman1 to tman9) within the navigation drawer. The "tmanX.bco" attribute is set to control the background color of these textboxes, likely to match the theme selected in the navigation drawer.

Usage
-----

This script is intended for use with the Nextion Editor, a visual interface design tool for Nextion displays. It enhances the user experience by creating a visually appealing and functional interface with customizable themes and multilingual support.

To implement this script effectively, ensure that the Nextion display is configured to handle the defined elements, such as timers, icons, textboxes, and containers. Additionally, ensure that the necessary font colors, icon images, and text content are available and properly configured within the Nextion Editor.

Users can interact with the display, select themes from the navigation drawer, and view content in their chosen language. The script provides a dynamic and engaging user interface for Nextion displays.

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

Preinitialize event Intervalos
------------------------------

.. code-block:: javascript

    // Changes the background color of the page
    Intervalos.bco=fondo
    // Sends the current page number over serial
    sendme

Postinitialize event Intervalos
-------------------------------

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
      tman1.pco=fontColor.val
      tman2.pco=fontColor.val
      tman3.pco=fontColor.val
      tman4.pco=fontColor.val
      tman5.pco=fontColor.val
      tman6.pco=fontColor.val
      tman7.pco=fontColor.val
      tman8.pco=fontColor.val
      tman9.pco=fontColor.val
      //Theme 1
      pic 25,30,78
      pic 25,120,144
      pic 25,400,146
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      tman1.pco=fontColor.val
      tman2.pco=fontColor.val
      tman3.pco=fontColor.val
      tman4.pco=fontColor.val
      tman5.pco=fontColor.val
      tman6.pco=fontColor.val
      tman7.pco=fontColor.val
      tman8.pco=fontColor.val
      tman9.pco=fontColor.val
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      tman1.pco=fontColor.val
      tman2.pco=fontColor.val
      tman3.pco=fontColor.val
      tman4.pco=fontColor.val
      tman5.pco=fontColor.val
      tman6.pco=fontColor.val
      tman7.pco=fontColor.val
      tman8.pco=fontColor.val
      tman9.pco=fontColor.val
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      tman1.pco=fontColor.val
      tman2.pco=fontColor.val
      tman3.pco=fontColor.val
      tman4.pco=fontColor.val
      tman5.pco=fontColor.val
      tman6.pco=fontColor.val
      tman7.pco=fontColor.val
      tman8.pco=fontColor.val
      tman9.pco=fontColor.val
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      tman1.pco=fontColor.val
      tman2.pco=fontColor.val
      tman3.pco=fontColor.val
      tman4.pco=fontColor.val
      tman5.pco=fontColor.val
      tman6.pco=fontColor.val
      tman7.pco=fontColor.val
      tman8.pco=fontColor.val
      tman9.pco=fontColor.val
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      tman1.pco=fontColor.val
      tman2.pco=fontColor.val
      tman3.pco=fontColor.val
      tman4.pco=fontColor.val
      tman5.pco=fontColor.val
      tman6.pco=fontColor.val
      tman7.pco=fontColor.val
      tman8.pco=fontColor.val
      tman9.pco=fontColor.val
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
    //Eighth container
    cirs 380,370,30,color
    cirs 530,370,30,color
    cirs 380,430,30,color
    cirs 530,430,30,color
    line 380,340,530,340,color
    line 380,460,530,460,color
    fill 380,340,150,120,color
    line 350,370,350,430,color
    fill 350,370,30,60,color
    line 560,370,560,430,color
    fill 530,370,30,60,color
    //Nineth container
    cirs 610,370,30,color
    cirs 760,370,30,color
    cirs 610,430,30,color
    cirs 760,430,30,color
    line 610,340,760,340,color
    line 610,460,760,460,color
    fill 610,340,150,120,color
    line 580,370,580,430,color
    fill 580,370,30,60,color
    line 790,370,790,430,color
    fill 760,370,30,60,color
    //Containers end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 320,25,220,25,4,fontColor.val,color,1,1,3,"Intervalos de servicio"
      xstr 145,85,150,45,5,fontColor.val,color,0,1,3,"Mantenimiento 500 h de operación"
      xstr 375,85,160,45,5,fontColor.val,color,0,1,3,"Mantenimiento del motor"
      xstr 605,85,160,45,5,fontColor.val,color,0,1,3,"Periodo de lubricación del motor"
      xstr 145,225,155,45,5,fontColor.val,color,0,1,3,"Mantenimiento 4000 h de funcionamiento"
      xstr 375,225,155,45,5,fontColor.val,color,0,1,3,"Mantenimiento 8000 h de funcionamiento"
      xstr 605,225,145,45,5,fontColor.val,color,0,1,3,"Mantenimiento 16000 h de funcionamiento"
      xstr 145,345,145,45,5,fontColor.val,color,0,1,3,"Mantenimiento 20000 h de funcionamiento"
      xstr 375,345,145,45,5,fontColor.val,color,0,1,3,"Mantenimiento 30000 h de funcionamiento"
      xstr 605,345,145,45,5,fontColor.val,color,0,1,3,"Mantenimiento 40000 h de funcionamiento"
    }else if(sys0==1)
    {
      //Italian
      xstr 320,25,220,25,4,fontColor.val,color,1,1,3,"Intervalli di servizio"
      xstr 145,85,150,45,5,fontColor.val,color,0,1,3,"Manutenzione 500 h di funzionamento"
      xstr 375,85,160,45,5,fontColor.val,color,0,1,3,"Manutenzione del motore"
      xstr 605,85,160,45,5,fontColor.val,color,0,1,3,"Periodo di lubrificazione del motore"
      xstr 145,225,155,45,5,fontColor.val,color,0,1,3,"Manutenzione 4000 h di funzionamento"
      xstr 375,225,155,45,5,fontColor.val,color,0,1,3,"Manutenzione 8000 h di funzionamento"
      xstr 605,225,145,45,5,fontColor.val,color,0,1,3,"Manutenzione 16000 h di funzionamento"
      xstr 145,345,145,45,5,fontColor.val,color,0,1,3,"Manutenzione 20000 h di funzionamento"
      xstr 375,345,145,45,5,fontColor.val,color,0,1,3,"Manutenzione 30000 h di funzionamento"
      xstr 605,345,145,45,5,fontColor.val,color,0,1,3,"Manutenzione 40000 h di funzionamento"
    }else if(sys0==2)
    {
      //French
      xstr 320,25,220,25,4,fontColor.val,color,1,1,3,"Intervalles d'entretien"
      xstr 145,85,150,45,5,fontColor.val,color,0,1,3,"Maintenance 500 h de fonctionnement"
      xstr 375,85,160,45,5,fontColor.val,color,0,1,3,"Entretien moteur"
      xstr 605,85,160,45,5,fontColor.val,color,0,1,3,"Période de lubrification du moteur"
      xstr 145,225,155,45,5,fontColor.val,color,0,1,3,"Maintenance 4000 h de fonctionnement"
      xstr 375,225,155,45,5,fontColor.val,color,0,1,3,"Maintenance 8000 h de fonctionnement"
      xstr 605,225,145,45,5,fontColor.val,color,0,1,3,"Maintenance 16000 h de fonctionnement"
      xstr 145,345,145,45,5,fontColor.val,color,0,1,3,"Maintenance 20000 h de fonctionnement"
      xstr 375,345,145,45,5,fontColor.val,color,0,1,3,"Maintenance 30000 h de fonctionnement"
      xstr 605,345,145,45,5,fontColor.val,color,0,1,3,"Maintenance 40000 h de fonctionnement"
    }else if(sys0==3)
    {
      //English
      xstr 320,25,220,25,4,fontColor.val,color,1,1,3,"Service intervals"
      xstr 145,85,150,45,5,fontColor.val,color,0,1,3,"Maintenance 500 h of operation"
      xstr 375,85,160,45,5,fontColor.val,color,0,1,3,"Motor maintenance"
      xstr 605,85,160,45,5,fontColor.val,color,0,1,3,"Motor lubrication period"
      xstr 145,225,155,45,5,fontColor.val,color,0,1,3,"Maintenance 4000 h of operation"
      xstr 375,225,155,45,5,fontColor.val,color,0,1,3,"Maintenance 8000 h of operation"
      xstr 605,225,145,45,5,fontColor.val,color,0,1,3,"Maintenance 16000 h of operation"
      xstr 145,345,145,45,5,fontColor.val,color,0,1,3,"Maintenance 20000 h of operation"
      xstr 375,345,145,45,5,fontColor.val,color,0,1,3,"Maintenance 30000 h of operation"
      xstr 605,345,145,45,5,fontColor.val,color,0,1,3,"Maintenance 40000 h of operation"
    }else if(sys0==4)
    {
      //German
      xstr 320,25,220,25,4,fontColor.val,color,1,1,3,"Wartungsintervalle"
      xstr 145,85,150,45,5,fontColor.val,color,0,1,3,"Wartung 500 h Betrieb"
      xstr 375,85,160,45,5,fontColor.val,color,0,1,3,"Motorwartung"
      xstr 605,85,160,45,5,fontColor.val,color,0,1,3,"Zeitraum der Motorschmierung"
      xstr 145,225,155,45,5,fontColor.val,color,0,1,3,"Wartung 4000 Betriebsstunden"
      xstr 375,225,155,45,5,fontColor.val,color,0,1,3,"Wartung 8000 Betriebsstunden"
      xstr 605,225,145,45,5,fontColor.val,color,0,1,3,"Wartung 16000 Betriebsstunden"
      xstr 145,345,145,45,5,fontColor.val,color,0,1,3,"Wartung 20000 Betriebsstunden"
      xstr 375,345,145,45,5,fontColor.val,color,0,1,3,"Wartung 30000 Betriebsstunden"
      xstr 605,345,145,45,5,fontColor.val,color,0,1,3,"Wartung 40000 Betriebsstunden"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 320,25,220,25,4,fontColor.val,color,1,1,3,"Intervalos de serviço"
      xstr 145,85,150,45,5,fontColor.val,color,0,1,3,"Manutenção 500 h de operação"
      xstr 375,85,160,45,5,fontColor.val,color,0,1,3,"Manutenção do motor"
      xstr 605,85,160,45,5,fontColor.val,color,0,1,3,"Período de lubrificação do motor"
      xstr 145,225,155,45,5,fontColor.val,color,0,1,3,"Manutenção 4000 h de operação"
      xstr 375,225,155,45,5,fontColor.val,color,0,1,3,"Manutenção 8000 h de operação"
      xstr 605,225,145,45,5,fontColor.val,color,0,1,3,"Manutenção 16000 h de operação"
      xstr 145,345,145,45,5,fontColor.val,color,0,1,3,"Manutenção 20000 h de operação"
      xstr 375,345,145,45,5,fontColor.val,color,0,1,3,"Manutenção 30000 h de operação"
      xstr 605,345,145,45,5,fontColor.val,color,0,1,3,"Manutenção 40000 h de operação"
    }
    //Page text end
    //Textboxes start
    tman1.bco=color
    tman2.bco=color
    tman3.bco=color
    tman4.bco=color
    tman5.bco=color
    tman6.bco=color
    tman7.bco=color
    tman8.bco=color
    tman9.bco=color
    //Textboxes end

Touch press event bInfoIN
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

Touch release event bInfoIN
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

Touch press event bHomeIn
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

Touch release event bHomeIN
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

Touch press event bBackIN
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

Touch release event bBackIN
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
    page Menu
