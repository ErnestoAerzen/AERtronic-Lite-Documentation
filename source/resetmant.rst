ResetMant Nextion Page
======================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script responsible for creating a navigation drawer, page title, buttons, icons, and text elements. The script enables users to navigate and interact with the interface for maintenance record management.

Script Overview
---------------

The script comprises the following sections:

1. **Navigation Drawer**
   - This section defines the visual elements of the navigation drawer, including circles, lines, and fills, using specified colors. The navigation drawer provides a menu interface for users.

2. **Page Title**
   - A page title is created with circles, lines, and fills to visually separate different parts of the interface. It serves as an indicator of the currently displayed page.

3. **Buttons**
   - Two sets of buttons are defined with circles, lines, and fills, using different colors. These buttons allow users to perform actions, such as confirming or canceling an operation.

4. **Navigation Drawer Icons**
   - The script checks the selected theme (`fondo`) and adjusts the icons in the navigation drawer based on the theme selection. Icons are changed to match the chosen theme.

5. **Text**
   - Text elements are placed on the interface to provide instructions and labels to users. The text content varies based on the selected language (`sys0`) to accommodate different languages.

Script Explanation
------------------

Let's delve into the details of each section:

1. **Navigation Drawer**
   - Visual elements are created to form the navigation drawer, including circles, lines, and fills. These elements provide a menu-like interface for users to navigate through the application.

2. **Page Title**
   - A page title section is defined with circles, lines, and fills to visually separate different parts of the interface. It serves as an indicator of the currently displayed page.

3. **Buttons**
   - Two sets of buttons are defined. The first set uses one color, while the second set uses a different color. These buttons are used to perform actions, such as confirming or canceling an operation.

4. **Navigation Drawer Icons**
   - The script checks the selected theme (`fondo`) and configures icons accordingly. The icons' appearance is determined by the theme selection.

5. **Text**
   - Text elements are placed on the interface to provide instructions and labels to users. The text content varies based on the selected language (`sys0`) to accommodate different languages.

Conclusion
----------

This documentation provides a comprehensive understanding of a Nextion display script that creates a navigation drawer, page title, buttons, icons, and text elements. This script enables users to navigate and interact with the interface for maintenance record management. Developers can adapt and extend this script to create customized and interactive Nextion display interfaces for their applications.

Please note that this script serves as an example and should be integrated into a complete Nextion display project with appropriate user interactions, logic, and additional features as needed.

Preinitialize event ResetMant
-----------------------------

.. code-block:: javascript

    // Changes the page's background color
    ResetMant.bco=fondo
    // Changes the textbox color
    rText.bco=fondo

Postinitialize event ResetMant
------------------------------

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
    //Buttons start
    cirs 260,260,30,color
    cirs 400,260,30,color
    line 260,230,400,230,color
    line 260,290,400,290,color
    fill 260,230,140,60,color
    //
    cirs 480,260,30, 0xB123
    cirs 620,260,30,0xB123
    line 480,230,620,230,0xB123
    line 480,290,620,290,0xB123
    fill 480,230,140,60,0xB123
    //Buttons end
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
    //Text start
    if(sys0==0)
    {
      //Spanish
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Confirmar eliminar registros de mantenimiento"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Eliminar registros"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminar"
    }else if(sys0==1)
    {
      //Italian
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Conferma l'eliminazione dei record di manutenzione"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"eliminare i record"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annulla"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminare"
    }else if(sys0==2)
    {
      //French
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Confirmer la suppression des enregistrements de maintenance"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Supprimer des enregistrements"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annuler"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Éliminer"
    }else if(sys0==3)
    {
      //English
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Confirm delete maintenance records"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Delete records"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancel"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Delete"
    }else if(sys0==4)
    {
      //German
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Bestätigen Sie das Löschen der Wartungsaufzeichnungen"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Aufzeichnungen löschen"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Stornieren"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Beseitigen"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 250,140,500,35,7,fontColor.val,fondo,0,1,3,"Confirme a exclusão dos registros de manutenção"
      xstr 295,25,260,25,4,fontColor.val,color,1,1,3,"Excluir registros"
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminar"
    }

Touch press event m0
--------------------

.. code-block:: javascript

    cirs 260,260,30,fondo
    cirs 400,260,30,fondo
    line 260,230,400,230,fondo
    line 260,290,400,290,fondo
    fill 260,230,140,60,fondo

Touch release event m0
----------------------

.. code-block:: javascript

    cirs 260,260,30,color
    cirs 400,260,30,color
    line 260,230,400,230,color
    line 260,290,400,290,color
    fill 260,230,140,60,color
    if(sys0==0)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
    }else if(sys0==1)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annulla"
    }else if(sys0==2)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Annuler"
    }else if(sys0==3)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancel"
    }else if(sys0==4)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Stornieren"
    }else if(sys0==5)
    {
      xstr 300,250,120,25,0,fontColor.val,color,0,1,3,"Cancelar"
    }
    page menuServicio

Touch press event m1
--------------------

.. code-block:: javascript

    cirs 480,260,30,fondo
    cirs 620,260,30,fondo
    line 480,230,620,230,fondo
    line 480,290,620,290,fondo
    fill 480,230,140,60,fondo

Touch release event m1
----------------------

.. code-block:: javascript

    cirs 480,260,30,0xB123
    cirs 620,260,30,0xB123
    line 480,230,620,230,0xB123
    line 480,290,620,290,0xB123
    fill 480,230,140,60,0xB123
    if(sys0==0)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminar"
    }else if(sys0==1)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminare"
    }else if(sys0==2)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Éliminer"
    }else if(sys0==3)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Delete"
    }else if(sys0==4)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Beseitigen"
    }else if(sys0==5)
    {
      xstr 520,250,120,25,0,65535,0xB123,0,1,3,"Eliminar"
    }
    //
    sendme

Touch press event bInfoRM
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

Touch release event bInfoRM
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

Touch press event bHomeRM
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

Touch release event bHomeRM
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

Touch press event bBackRM
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

Touch release event bBackRM
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


