InSesion Nextion Page
============================

Description
-----------

Overview
--------

This document provides an in-depth explanation of the Nextion display script designed for a login interface created using the Nextion Editor. The script defines various graphical elements, including buttons, input fields, and icons, while also implementing conditional logic to adapt the display's appearance based on theme and language selection.

Script Structure
----------------

The script is organized into several sections, each serving a specific purpose within the user interface:

**Nav Drawer**
~~~~~~~~~~~~~~~~

This section defines the elements of a navigation drawer, which typically appears on the side of the display. It includes four circular elements ("cirs") representing navigation icons and lines ("line") to separate them. Additionally, it configures the "fill" command to create rectangles around the circular elements, forming visually appealing navigation options.

**Page Title**
~~~~~~~~~~~~~~~~

The "Page Title" section focuses on defining two circular elements ("cirs") at the top of the display, creating a visually distinct title area. It also includes lines ("line") to separate these elements and a "fill" command to provide a colored background for the title.

**User Box**
~~~~~~~~~~~~~~~~

This section defines a rectangular user input box with sharp edges. It utilizes the "line" command to draw the box's outline and accurately position the box on the display. This area is intended for users to enter their username.

**Password Text Box**
~~~~~~~~~~~~~~~~~~~~~

Similar to the user box, this section defines a rectangular input field for entering a password. It uses the "line" command to draw the box's boundaries. Both the user box and password text box contribute to the login functionality of the interface.

**Nav Drawer Icons**
~~~~~~~~~~~~~~~~~~~~

Conditional logic is employed in this section to determine which icons to display in the navigation drawer based on the value of the "fondo" variable. Different icons are displayed for various themes, enhancing the visual appeal of the navigation drawer. The icons are precisely positioned using the "pic" command.

Conditional Logic
-----------------

The script uses conditional logic to dynamically adjust the display based on theme and language selection:

- **Font Color**: The "fontColor.val" variable controls the font color, allowing for different color schemes based on the selected theme.

- **Themes**: Depending on the value of the "fondo" variable, the script applies different themes to the display. Each theme includes unique icons, colors, and visual styles.

- **Language Selection**: The "sys0" variable determines which language option is currently selected, influencing the displayed text. Language-specific labels for the login interface are defined based on the selected language.

Usage
-----

This script is designed to be used with the Nextion Editor, a graphical interface design tool for Nextion displays. To implement this script effectively, ensure that the Nextion display is correctly configured to handle the defined variables and commands.

The primary purpose of this script is to create an engaging and user-friendly login interface on the Nextion display. Users can enter their username and password in the designated input fields.

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

Preinitialize event InSesion
----------------------------

.. code-block:: javascript

    // Changes the page's background color
    InSesion.bco=fondo
    // Focus in the first textbox when the page is loaded
    textbox.val=0

Postinitialize event InSesion
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
    //Page title start
    cirs 310,40,30,color
    cirs 540,40,30,color
    line 310,10,540,10,color
    line 310,70,540,70,color
    fill 310,10,240,60,color
    //Page title end
    //User box start
    line 265,90,305,90,0x3B44
    line 375,90,650,90,0x3B44
    line 650,90,650,130,0x3B44
    line 265,90,265,130,0x3B44
    line 265,130,650,130,0x3B44
    //User box end
    //Password text box start
    line 265,150,305,150,0xDF39
    line 395,150,650,150,0xDF39
    line 650,150,650,190,0xDF39
    line 265,150,265,190,0xDF39
    line 265,190,650,190,0xDF39
    //Password text box start
    //Nav Drawer icons start
    if(fondo==65534)
    {
      //Font color
      fontColor.val=0
      //Theme 1
      pic 25,30,78
      pic 25,120,144
      pic 25,400,146
      //Log in icons
      pic 205,90,253
      pic 205,150,254
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Log in icons
      pic 205,90,255
      pic 205,150,256
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Log in icons
      pic 205,90,257
      pic 205,150,258
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Log in icons
      pic 205,90,259
      pic 205,150,260
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Log in icons
      pic 205,90,261
      pic 205,150,262
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Log in icons
      pic 205,90,263
      pic 205,150,264
    }
    //Nav Drawer icons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Iniciar sesión"
      xstr 315,80,150,15,2,fontColor.val,color,0,1,3,"Usuario"
      xstr 275,140,150,15,2,fontColor.val,color,1,1,3,"Contraseña"
    }else if(sys0==1)
    {
      //Italian
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Accesso"
      xstr 315,80,150,15,2,fontColor.val,color,0,1,3,"Utente"
      xstr 275,140,150,15,2,fontColor.val,color,1,1,3,"Parola d'ordine"
    }else if(sys0==2)
    {
      //French
      xstr 310,25,230,25,4,fontColor.val,color,1,1,3,"Commencer la session"
      xstr 315,80,150,15,2,fontColor.val,color,0,1,3,"Utilisateur"
      xstr 275,140,150,15,2,fontColor.val,color,1,1,3,"Mot de passe"
    }else if(sys0==3)
    {
      //English
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Log in"
      xstr 315,80,150,15,2,fontColor.val,color,0,1,3,"User"
      xstr 275,140,150,15,2,fontColor.val,color,1,1,3,"Password"
    }else if(sys0==4)
    {
      //German
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Einloggen"
      xstr 315,80,150,15,2,fontColor.val,color,0,1,3,"Benutzer"
      xstr 275,140,150,15,2,fontColor.val,color,1,1,3,"Passwort"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Iniciar sessão"
      xstr 315,80,150,15,2,fontColor.val,color,0,1,3,"Usuário"
      xstr 275,140,150,15,2,fontColor.val,color,1,1,3,"Senha"
    }
    //Page text end
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Keyboard pics
    //first row lower case
    pic 125,240,379
    pic 190,240,380
    pic 255,240,381
    pic 320,240,382
    pic 385,240,383
    pic 450,240,384
    pic 515,240,385
    pic 580,240,386
    pic 645,240,387
    pic 710,240,388
    //second row lower case
    pic 125,290,389
    pic 190,290,390
    pic 255,290,391
    pic 320,290,392
    pic 385,290,393
    pic 450,290,394
    pic 515,290,395
    pic 580,290,396
    pic 645,290,397
    pic 710,290,398
    //third row lower case
    pic 125,340,399
    pic 190,340,400
    pic 255,340,401
    pic 320,340,402
    pic 385,340,403
    pic 450,340,404
    pic 515,340,405
    pic 580,340,406
    pic 645,340,407
    pic 710,340,408
    //fourth row lower case
    pic 125,390,409
    pic 190,390,410
    pic 255,390,411
    pic 320,390,412
    pic 580,390,413
    pic 645,390,414

Touch release event tUsuario
----------------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val

Touch press event tContraseña
-----------------------------

.. code-block:: javascript

    textbox.val=1
    //Focus on this textbox
    timerOn.val=2
    line 265,150,305,150,0x3B44
    line 395,150,650,150,0x3B44
    line 650,150,650,190,0x3B44
    line 265,150,265,190,0x3B44
    line 265,190,650,190,0x3B44
    //Hide the user textbox focus
    line 265,90,305,90,0xDF39
    line 375,90,650,90,0xDF39
    line 650,90,650,130,0xDF39
    line 265,90,265,130,0xDF39
    line 265,130,650,130,0xDF39

Touch release event tContraseña
-------------------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tContraseña.txt,contraL.val

Touch press event m0
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 125,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="q"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="q"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="Q"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="Q"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="1"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="1"
      }
    }

Touch release event m0
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 125,240,379
    }else if(keyboard.val==1)
    {
      pic 125,240,415
    }else if(keyboard.val==2)
    {
      pic 125,240,444
    }

Touch press event m1
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 190,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="w"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="w"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="W"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="W"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="2"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="2"
      }
    }

Touch release event m1
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 190,240,380
    }else if(keyboard.val==1)
    {
      pic 190,240,416
    }else if(keyboard.val==2)
    {
      pic 190,240,445
    }

Touch press event m2
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 255,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="e"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="e"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="E"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="E"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="3"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="3"
      }
    }

Touch release event m2
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 255,240,381
    }else if(keyboard.val==1)
    {
      pic 255,240,417
    }else if(keyboard.val==2)
    {
      pic 255,240,446
    }

Touch press event m3
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 320,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="r"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="r"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="R"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="R"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="4"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="4"
      }
    }

Touch release event m3
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 320,240,382
    }else if(keyboard.val==1)
    {
      pic 320,240,418
    }else if(keyboard.val==2)
    {
      pic 320,240,447
    }

Touch press event m4
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 385,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="t"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="t"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="T"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="T"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="5"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="5"
      }
    }

Touch release event m4
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 385,240,383
    }else if(keyboard.val==1)
    {
      pic 385,240,419
    }else if(keyboard.val==2)
    {
      pic 385,240,448
    }

Touch press event m5
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 450,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="y"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="y"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="Y"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="Y"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="6"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="6"
      }
    }

Touch release event m5
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 450,240,384
    }else if(keyboard.val==1)
    {
      pic 450,240,420
    }else if(keyboard.val==2)
    {
      pic 450,240,449
    }

Touch press event m6
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 515,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="u"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="u"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="U"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="U"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="7"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="7"
      }
    }

Touch release event m6
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 515,240,385
    }else if(keyboard.val==1)
    {
      pic 515,240,421
    }else if(keyboard.val==2)
    {
      pic 515,240,450
    }

Touch press event m7
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 580,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="i"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="i"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="I"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="I"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="8"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="8"
      }
    }

Touch release event m7
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 580,240,386
    }else if(keyboard.val==1)
    {
      pic 580,240,422
    }else if(keyboard.val==2)
    {
      pic 580,240,451
    }

Touch press event m8
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 645,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="o"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="o"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="O"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="O"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="9"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="9"
      }
    }

Touch release event m8
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 645,240,387
    }else if(keyboard.val==1)
    {
      pic 645,240,423
    }else if(keyboard.val==2)
    {
      pic 645,240,452
    }

Touch press event m9
--------------------

.. code-block:: javascript

    //Changes the background color
    fill 710,240,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="p"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="p"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="P"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="P"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="0"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="0"
      }
    }

Touch release event m9
----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 710,240,388
    }else if(keyboard.val==1)
    {
      pic 710,240,424
    }else if(keyboard.val==2)
    {
      pic 710,240,453
    }

Touch press event m10
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 125,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="a"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="a"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="A"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="A"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="!"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="!"
      }
    }

Touch release event m10
------------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 125,290,389
    }else if(keyboard.val==1)
    {
      pic 125,290,425
    }else if(keyboard.val==2)
    {
      pic 125,290,454
    }

Touch press event m11
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 190,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="s"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="s"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="S"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="S"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="@"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="@"
      }
    }

Touch release event m11
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 190,290,390
    }else if(keyboard.val==1)
    {
      pic 190,290,426
    }else if(keyboard.val==2)
    {
      pic 190,290,455
    }

Touch press event m12
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 255,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="d"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="d"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="D"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="D"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="#"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="#"
      }
    }

Touch release event m12
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 255,290,391
    }else if(keyboard.val==1)
    {
      pic 255,290,427
    }else if(keyboard.val==2)
    {
      pic 255,290,456
    }

Touch press event m13
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 320,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="f"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="f"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="F"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="F"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="$"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="$"
      }
    }

Touch release event m13
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 320,290,392
    }else if(keyboard.val==1)
    {
      pic 320,290,428
    }else if(keyboard.val==2)
    {
      pic 320,290,457
    }

Touch press event m14
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 385,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="g"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="g"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="G"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="G"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="%"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="%"
      }
    }

Touch release event m14
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 385,290,393
    }else if(keyboard.val==1)
    {
      pic 385,290,429
    }else if(keyboard.val==2)
    {
      pic 385,290,458
    }

Touch press event m15
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 450,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="h"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="h"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="H"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="H"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="&"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="&"
      }
    }

Touch release event m15
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 450,290,394
    }else if(keyboard.val==1)
    {
      pic 450,290,430
    }else if(keyboard.val==2)
    {
      pic 450,290,459
    }

Touch press event m16
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 515,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="j"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="j"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="J"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="J"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="'"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="'"
      }
    }

Touch release event m16
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 515,290,395
    }else if(keyboard.val==1)
    {
      pic 515,290,431
    }else if(keyboard.val==2)
    {
      pic 515,290,460
    }

Touch press event m17
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 580,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="k"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="k"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="K"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="K"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="("
      }else if(textbox.val==1)
      {
        tContraseña.txt+="("
      }
    }

Touch release event m17
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 580,290,396
    }else if(keyboard.val==1)
    {
      pic 580,290,432
    }else if(keyboard.val==2)
    {
      pic 580,290,461
    }

Touch press event m18
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 645,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="l"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="l"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="L"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="L"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+=")"
      }else if(textbox.val==1)
      {
        tContraseña.txt+=")"
      }
    }

Touch release event m18
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 645,290,397
    }else if(keyboard.val==1)
    {
      pic 645,290,433
    }else if(keyboard.val==2)
    {
      pic 645,290,462
    }

Touch press event m19
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 710,290,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="?"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="?"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+=";"
      }else if(textbox.val==1)
      {
        tContraseña.txt+=";"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="="
      }else if(textbox.val==1)
      {
        tContraseña.txt+="="
      }
    }

Touch release event m19
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 710,290,398
    }else if(keyboard.val==1)
    {
      pic 710,290,434
    }else if(keyboard.val==2)
    {
      pic 710,290,463
    }

Touch press event m20
---------------------

.. code-block:: javascript

    fill 125,340,60,40,color
    if(keyboard.val==0||keyboard.val==2)
    {
      //0=Lower case/1=Upper case/2=Numeric
      keyboard.val=1
      //First row upper case
      pic 125,240,415
      pic 190,240,416
      pic 255,240,417
      pic 320,240,418
      pic 385,240,419
      pic 450,240,420
      pic 515,240,421
      pic 580,240,422
      pic 645,240,423
      pic 710,240,424
      //Second row upper case
      pic 125,290,425
      pic 190,290,426
      pic 255,290,427
      pic 320,290,428
      pic 385,290,429
      pic 450,290,430
      pic 515,290,431
      pic 580,290,432
      pic 645,290,433
      pic 710,290,434
      //Third row upper case
      pic 190,340,435
      pic 255,340,436
      pic 320,340,437
      pic 385,340,438
      pic 450,340,439
      pic 515,340,440
      pic 580,340,441
      pic 645,340,442
      pic 710,340,443
      //Fourth row upper case
      pic 125,390,409
    }else if(keyboard.val==1)
    {
      //Lower case Keyboard
      keyboard.val=0
      //first row lower case
      pic 125,240,379
      pic 190,240,380
      pic 255,240,381
      pic 320,240,382
      pic 385,240,383
      pic 450,240,384
      pic 515,240,385
      pic 580,240,386
      pic 645,240,387
      pic 710,240,388
      //second row lower case
      pic 125,290,389
      pic 190,290,390
      pic 255,290,391
      pic 320,290,392
      pic 385,290,393
      pic 450,290,394
      pic 515,290,395
      pic 580,290,396
      pic 645,290,397
      pic 710,290,398
      //third row lower case
      pic 125,340,399
      pic 190,340,400
      pic 255,340,401
      pic 320,340,402
      pic 385,340,403
      pic 450,340,404
      pic 515,340,405
      pic 580,340,406
      pic 645,340,407
      pic 710,340,408
      //fourth row lower case
      pic 125,390,409
      pic 190,390,410
      pic 255,390,411
      pic 320,390,412
      pic 580,390,413
      pic 645,390,414
    }

Touch release event m20
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores image
    pic 125,340,399

Touch press event m21
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 190,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="z"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="z"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="Z"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="Z"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="{"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="{"
      }
    }

Touch release event m21
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 190,340,400
    }else if(keyboard.val==1)
    {
      pic 190,340,435
    }else if(keyboard.val==2)
    {
      pic 190,340,464
    }

Touch press event m22
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 255,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="x"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="x"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="X"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="X"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="}"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="}"
      }
    }

Touch release event m22
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 255,340,401
    }else if(keyboard.val==1)
    {
      pic 255,340,436
    }else if(keyboard.val==2)
    {
      pic 255,340,465
    }

Touch press event m23
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 320,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="c"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="c"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="C"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="C"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="["
      }else if(textbox.val==1)
      {
        tContraseña.txt+="["
      }
    }

Touch release event m23
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 320,340,402
    }else if(keyboard.val==1)
    {
      pic 320,340,437
    }else if(keyboard.val==2)
    {
      pic 320,340,466
    }

Touch press event m24
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 385,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="v"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="v"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="V"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="V"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="]"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="]"
      }
    }

Touch release event m24
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 385,340,403
    }else if(keyboard.val==1)
    {
      pic 385,340,438
    }else if(keyboard.val==2)
    {
      pic 385,340,467
    }

Touch press event m25
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 450,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="b"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="b"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="B"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="B"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+=":"
      }else if(textbox.val==1)
      {
        tContraseña.txt+=":"
      }
    }

Touch release event m25
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 450,340,404
    }else if(keyboard.val==1)
    {
      pic 450,340,439
    }else if(keyboard.val==2)
    {
      pic 450,340,468
    }

Touch press event m26
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 515,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="n"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="n"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="N"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="N"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="\\"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="\\"
      }
    }

Touch release event m26
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 515,340,405
    }else if(keyboard.val==1)
    {
      pic 515,340,440
    }else if(keyboard.val==2)
    {
      pic 515,340,469
    }

Touch press event m27
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 580,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="m"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="m"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="M"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="M"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="|"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="|"
      }
    }

Touch release event m27
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 580,340,406
    }else if(keyboard.val==1)
    {
      pic 580,340,441
    }else if(keyboard.val==2)
    {
      pic 580,340,470
    }

Touch press event m28
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 645,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="<"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="<"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+=","
      }else if(textbox.val==1)
      {
        tContraseña.txt+=","
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="~"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="~"
      }
    }

Touch release event m28
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 645,340,407
    }else if(keyboard.val==1)
    {
      pic 645,340,442
    }else if(keyboard.val==2)
    {
      pic 645,340,471
    }

Touch press event m29
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 710,340,60,40,color
    //Keyboard functionality
    if(keyboard.val==0)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+=">"
      }else if(textbox.val==1)
      {
        tContraseña.txt+=">"
      }
    }else if(keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="/"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="/"
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="+"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="+"
      }
    }

Touch release event m29
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 710,340,408
    }else if(keyboard.val==1)
    {
      pic 710,340,443
    }else if(keyboard.val==2)
    {
      pic 710,340,472
    }

Touch press event m30
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 125,390,60,40,color
    //Keyboard functionality
    if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="*"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="*"
      }
    }
    keyboard.val=2
    //Numeric keyboard
    //First row
    pic 125,240,444
    pic 190,240,445
    pic 255,240,446
    pic 320,240,447
    pic 385,240,448
    pic 450,240,449
    pic 515,240,450
    pic 580,240,451
    pic 645,240,452
    pic 710,240,453
    //Second row
    pic 125,290,454
    pic 190,290,455
    pic 255,290,456
    pic 320,290,457
    pic 385,290,458
    pic 450,290,459
    pic 515,290,460
    pic 580,290,461
    pic 645,290,462
    pic 710,290,463
    //Third row
    pic 190,340,464
    pic 255,340,465
    pic 320,340,466
    pic 385,340,467
    pic 450,340,468
    pic 515,340,469
    pic 580,340,470
    pic 645,340,471
    pic 710,340,472
    //Fourth row
    pic 580,390,473

Touch release event m30
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0)
    {
      pic 125,390,409
    }else if(keyboard.val==1)
    {
      pic 125,390,409
    }else if(keyboard.val==2)
    {
      fill 125,390,60,40,65534
      pic 125,390,474
    }

Touch press event m31
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 190,390,60,40,color
    //Keyboard functionality
    if(textbox.val==0)
    {
      tUsuario.txt=""
    }else if(textbox.val==1)
    {
      tContraseña.txt=""
    }

Touch release event m31
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    pic 190,390,410

Touch press event m32
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 255,390,60,40,color
    if(textbox.val==0)
    {
      tUsuario.txt-=1
    }else if(textbox.val==1)
    {
      tContraseña.txt-=1
    }

Touch release event m32
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the picture
    pic 255,390,411

Touch press event m33
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 320,390,255,40,color
    //Keyboard functionality
    if(textbox.val==0)
    {
      tUsuario.txt+=" "
    }else if(textbox.val==1)
    {
      tContraseña.txt+=" "
    }

Touch release event m33
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the picture
    pic 320,390,412

Touch press event m34
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 580,390,60,40,color
    //Keyboard functionality
    if(keyboard.val==0||keyboard.val==1)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="."
      }else if(textbox.val==1)
      {
        tContraseña.txt+="."
      }
    }else if(keyboard.val==2)
    {
      if(textbox.val==0)
      {
        tUsuario.txt+="-"
      }else if(textbox.val==1)
      {
        tContraseña.txt+="-"
      }
    }

Touch release event m34
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    if(keyboard.val==0||keyboard.val==1)
    {
      pic 580,390,413
    }else if(keyboard.val==2)
    {
      pic 580,390,473
    }

Touch press event m35
---------------------

.. code-block:: javascript

    //Changes the background color
    fill 645,390,125,40,color
    if(tUsuario.txt=="admin"&&tContraseña.txt=="123")
    {
      page MenuConf
    }

Touch release event m35
-----------------------

.. code-block:: javascript

    //Checks the length of the string to stop timer
    strlen tUsuario.txt,usuarioL.val
    strlen tContraseña.txt,contraL.val
    //Restores the button image
    pic 645,390,414

Touch press event bInfoIS
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

Touch release event bInfoIS
---------------------------

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

Touch press event bHomeIS
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

Touch release event bHomeIS
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

Touch press event bBackIS
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

Touch release event bBackIS
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

Timer event tm0
---------------

.. code-block:: javascript

    //timerOn values(0=tUsuario focus,1=tContraseña focus,2=hide)
    if(timerOn.val==0&&usuarioL.val==0)
    {
      tm0.en=1
      tm0.tim=1000
      xstr 270,95,20,30,7,BLACK,0xF7BD,0,1,3,"|"
      delay=500
      fill 270,95,20,30,0xF7BD
    }else if(timerOn.val==2&&contraL.val==0)
    {
      tm0.en=1
      tm0.tim=1000
      xstr 270,155,20,30,7,BLACK,0xF7BD,0,1,3,"|"
      delay=500
      fill 270,155,20,30,0xF7BD
    }
    