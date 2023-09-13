Idiomas Nextion Page
============================

Description
-----------

Overview
--------

This document provides an in-depth explanation of the Nextion display script created for use with the Nextion Editor. The script is designed to create an interactive user interface for language selection on a Nextion display. It defines various graphical elements, buttons, and text labels, while also implementing conditional logic to adapt the display's appearance and behavior based on user choices and theme settings.

Script Structure
----------------

The script is structured into several sections, each serving a specific purpose within the user interface:

**Nav Drawer**
~~~~~~~~~~~~~~~~

This section defines the elements of a navigation drawer, which typically appears on the side of the display. It includes four circular elements ("cirs") representing navigation icons and lines ("line") to separate them. Additionally, it configures the "fill" command to create rectangles around the circular elements. These rectangles form the clickable regions for selecting different options. This part of the script is responsible for creating a visually appealing and interactive navigation menu.

**Page Title**
~~~~~~~~~~~~~~~~

The "Page Title" section focuses on defining two circular elements ("cirs") at the top of the display, creating a visually distinct title area. It also includes lines ("line") to separate these elements and a "fill" command to create a colored background. This section enhances the aesthetics of the display by providing a clear title area.

**Buttons**
~~~~~~~~~~~~~~~~

The "Buttons" section is extensive and defines six sets of circular buttons, each corresponding to a different language option (e.g., Spanish, Italian, French). For each set, it defines four circular elements ("cirs") arranged in a 2x2 grid. Lines ("line") are used to separate the buttons and create visually distinct regions. The "fill" command is employed to highlight the selected button by coloring it differently. Additionally, this section utilizes the "xstr" command to display the name of the language on the buttons. These buttons serve as the interactive elements for language selection.

**Nav Drawer Icons**
~~~~~~~~~~~~~~~~~~~~

This section employs conditional logic to determine which icons to display in the navigation drawer based on the value of the "fondo" variable. Depending on the selected theme, different icons are shown. The icons are positioned using the "pic" command, enhancing the visual theme of the navigation drawer.

**Page Text**
~~~~~~~~~~~~~~~~

The "Page Text" section also utilizes conditional logic, specifically the "sys0" variable, to display text related to the selected language option. It uses the "xstr" command to display the language-specific text in a specified region on the display. Additionally, this section includes circular buttons and icons corresponding to the selected language, enhancing the user experience.

Conditional Logic
-----------------

The script employs conditional logic to dynamically adjust the display based on user choices and theme settings:

- **Font Color**: The "fontColor.val" variable controls the font color, allowing for different color schemes based on the selected theme.

- **Themes**: Depending on the value of the "fondo" variable, the script applies different themes to the display. Each theme includes unique icons, colors, and visual styles.

- **Language Selection**: The "sys0" variable determines which language option is currently selected, influencing the displayed text and button highlighting.

Usage
-----

This script is intended for use with the Nextion Editor, a graphical interface design tool for Nextion displays. To implement this script, ensure the Nextion display is properly configured to handle the defined variables and commands.

The primary purpose of this script is to create an engaging and user-friendly language selection interface for the Nextion display. Users can choose their preferred language, and the script dynamically adjusts the display to accommodate their selection.

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

Preinitialize event Idiomas
---------------------------

.. code-block:: javascript

    // Changes the page's background color
    Idiomas.bco=fondo
    // Variable to store the main color when the language container is selected
    selected.val=0x3B44

Postinitialize event Idiomas
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
    cirs 310,40,30,color
    cirs 540,40,30,color
    line 310,10,540,10,color
    line 310,70,540,70,color
    fill 310,10,240,60,color
    //Page title end
    //Buttons start
    //First button
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    xstr 225,145,120,35,7,fontColor.val,color,0,1,3,"Español"
    //Second button
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    xstr 455,145,120,35,7,fontColor.val,color,0,1,3,"Italiano"
    //Third button
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    xstr 685,145,120,35,7,fontColor.val,color,0,1,3,"Français"
    //Fourth button
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    xstr 225,315,120,35,7,fontColor.val,color,0,1,3,"Deutsch"
    //Fifth button
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    xstr 455,315,120,35,7,fontColor.val,color,0,1,3,"English"
    //Sixth button
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    xstr 685,315,120,35,7,fontColor.val,color,0,1,3,"Português"
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
      //Flags icons
      pic 140,130,211
      pic 370,130,212
      pic 600,130,213
      pic 140,300,214
      pic 370,300,215
      pic 600,300,216
    }else if(fondo==63391)
    {
      //Font color
      fontColor.val=0
      //Theme 2
      pic 25,30,89
      pic 25,120,148
      pic 25,400,150
      //Flags icons
      pic 140,130,217
      pic 370,130,218
      pic 600,130,219
      pic 140,300,220
      pic 370,300,221
      pic 600,300,222
    }else if(fondo==65438)
    {
      //Font color
      fontColor.val=0
      //Theme 3
      pic 25,30,100
      pic 25,120,152
      pic 25,400,154
      //Flags icons
      pic 140,130,223
      pic 370,130,224
      pic 600,130,225
      pic 140,300,226
      pic 370,300,227
      pic 600,300,228
    }else if(fondo==63421)
    {
      //Font color
      fontColor.val=0
      //Theme 4
      pic 25,30,111
      pic 25,120,156
      pic 25,400,158
      //Flags icons
      pic 140,130,229
      pic 370,130,230
      pic 600,130,231
      pic 140,300,232
      pic 370,300,233
      pic 600,300,234
    }else if(fondo==6339)
    {
      //Font color
      fontColor.val=65535
      //Theme 5
      pic 25,30,122
      pic 25,120,160
      pic 25,400,162
      //Flags icons
      pic 140,130,235
      pic 370,130,236
      pic 600,130,237
      pic 140,300,238
      pic 370,300,239
      pic 600,300,240
    }else if(fondo==8484)
    {
      //Font color
      fontColor.val=65535
      //Theme 6
      pic 25,30,133
      pic 25,120,164
      pic 25,400,166
      //Flags icons
      pic 140,130,241
      pic 370,130,242
      pic 600,130,243
      pic 140,300,244
      pic 370,300,245
      pic 600,300,246
    }
    //Nav Drawer icons end
    //Page text start
    if(sys0==0)
    {
      //Spanish
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Idiomas"
      //First button
      cirs 150,130,30,selected.val
      cirs 300,130,30,selected.val
      cirs 150,190,30,selected.val
      cirs 300,190,30,selected.val
      line 150,100,300,100,selected.val
      line 150,220,300,220,selected.val
      fill 150,100,150,120,selected.val
      line 120,130,120,190,selected.val
      fill 120,130,30,60,selected.val
      line 330,130,330,190,selected.val
      fill 300,130,30,60,selected.val
      pic 140,130,247
      xstr 225,145,120,35,7,65535,selected.val,0,1,3,"Español"
    }else if(sys0==1)
    {
      //Italian
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Le lingue"
      cirs 380,130,30,selected.val
      cirs 530,130,30,selected.val
      cirs 380,190,30,selected.val
      cirs 530,190,30,selected.val
      line 380,100,530,100,selected.val
      line 380,220,530,220,selected.val
      fill 380,100,150,120,selected.val
      line 350,130,350,190,selected.val
      fill 350,130,30,60,selected.val
      line 560,130,560,190,selected.val
      fill 530,130,30,60,selected.val
      pic 370,130,248
      xstr 455,145,120,35,7,65535,selected.val,0,1,3,"Italiano"
    }else if(sys0==2)
    {
      //French
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Langues"
      cirs 610,130,30,selected.val
      cirs 760,130,30,selected.val
      cirs 610,190,30,selected.val
      cirs 760,190,30,selected.val
      line 610,100,760,100,selected.val
      line 610,220,760,220,selected.val
      fill 610,100,150,120,selected.val
      line 580,130,580,190,selected.val
      fill 580,130,30,60,selected.val
      line 790,130,790,190,selected.val
      fill 760,130,30,60,selected.val
      pic 600,130,249
      xstr 685,145,120,35,7,65535,selected.val,0,1,3,"Français"
    }else if(sys0==3)
    {
      //English
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Languages"
      cirs 380,300,30,selected.val
      cirs 530,300,30,selected.val
      cirs 380,360,30,selected.val
      cirs 530,360,30,selected.val
      line 380,270,530,270,selected.val
      line 380,390,530,390,selected.val
      fill 380,270,150,120,selected.val
      line 350,300,350,360,selected.val
      fill 350,300,30,60,selected.val
      line 560,300,560,360,selected.val
      fill 530,300,30,60,selected.val
      pic 370,300,250
      xstr 455,315,120,35,7,65535,selected.val,0,1,3,"English"
    }else if(sys0==4)
    {
      //German
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Sprachen"
      cirs 150,300,30,selected.val
      cirs 300,300,30,selected.val
      cirs 150,360,30,selected.val
      cirs 300,360,30,selected.val
      line 150,270,300,270,selected.val
      line 150,390,300,390,selected.val
      fill 150,270,150,120,selected.val
      line 120,300,120,360,selected.val
      fill 120,300,30,60,selected.val
      line 330,300,330,360,selected.val
      fill 300,300,30,60,selected.val
      pic 140,300,251
      xstr 225,315,120,35,7,65535,selected.val,0,1,3,"Deutsch"
    }else if(sys0==5)
    {
      //Portuguese
      xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Línguas"
      cirs 610,300,30,selected.val
      cirs 760,300,30,selected.val
      cirs 610,360,30,selected.val
      cirs 760,360,30,selected.val
      line 610,270,760,270,selected.val
      line 610,390,760,390,selected.val
      fill 610,270,150,120,selected.val
      line 580,300,580,360,selected.val
      fill 580,300,30,60,selected.val
      line 790,300,790,360,selected.val
      fill 760,300,30,60,selected.val
      pic 600,300,252
      xstr 685,315,120,35,7,65535,selected.val,0,1,3,"Português"
    }
    //Page text end

Touch press event m0
--------------------

.. code-block:: javascript

    //changes the system language
    sys0=0
    //Deletes previous text
    fill 330,25,200,25,color
    //Spanish
    xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Idiomas"
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    if(fondo==65534)
    {
      pic 140,130,211
    }else if(fondo==63391)
    {
      pic 140,130,217
    }else if(fondo==65438)
    {
      pic 140,130,223
    }else if(fondo==63421)
    {
      pic 140,130,229
    }else if(fondo==6339)
    {
      pic 140,130,235
    }else if(fondo==8484)
    {
      pic 140,130,241
    }
    xstr 225,145,120,35,7,BLACK,color,0,1,3,"Español"
    //It focus only in this button changes the bg color of the other buttons
    //button 2
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    if(fondo==65534)
    {
      pic 370,130,212
    }else if(fondo==63391)
    {
      pic 370,130,218
    }else if(fondo==65438)
    {
      pic 370,130,224
    }else if(fondo==63421)
    {
      pic 370,130,230
    }else if(fondo==6339)
    {
      pic 370,130,236
    }else if(fondo==8484)
    {
      pic 370,130,242
    }
    xstr 455,145,120,35,7,BLACK,color,0,1,3,"Italiano"
    //button 3
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    if(fondo==65534)
    {
      pic 600,130,213
    }else if(fondo==63391)
    {
      pic 600,130,219
    }else if(fondo==65438)
    {
      pic 600,130,225
    }else if(fondo==63421)
    {
      pic 600,130,231
    }else if(fondo==6339)
    {
      pic 600,130,237
    }else if(fondo==8484)
    {
      pic 600,130,243
    }
    xstr 685,145,120,35,7,BLACK,color,0,1,3,"Français"
    //button 4
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    if(fondo==65534)
    {
      pic 140,300,214
    }else if(fondo==63391)
    {
      pic 140,300,220
    }else if(fondo==65438)
    {
      pic 140,300,226
    }else if(fondo==63421)
    {
      pic 140,300,232
    }else if(fondo==6339)
    {
      pic 140,300,238
    }else if(fondo==8484)
    {
      pic 140,300,244
    }
    xstr 225,315,120,35,7,BLACK,color,0,1,3,"Deutsch"
    //button 5
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    if(fondo==65534)
    {
      pic 370,300,215
    }else if(fondo==63391)
    {
      pic 370,300,221
    }else if(fondo==65438)
    {
      pic 370,300,227
    }else if(fondo==63421)
    {
      pic 370,300,233
    }else if(fondo==6339)
    {
      pic 370,300,239
    }else if(fondo==8484)
    {
      pic 370,300,245
    }
    xstr 455,315,120,35,7,BLACK,color,0,1,3,"English"
    //button 6
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    if(fondo==65534)
    {
      pic 600,300,216
    }else if(fondo==63391)
    {
      pic 600,300,222
    }else if(fondo==65438)
    {
      pic 600,300,228
    }else if(fondo==63421)
    {
      pic 600,300,234
    }else if(fondo==6339)
    {
      pic 600,300,240
    }else if(fondo==8484)
    {
      pic 600,300,246
    }
    xstr 685,315,120,35,7,BLACK,color,0,1,3,"Português"


Touch release event m0
----------------------

.. code-block:: javascript

    //Background color depending if it is selected or not
    if(sys0==0)
    {
      cirs 150,130,30,selected.val
      cirs 300,130,30,selected.val
      cirs 150,190,30,selected.val
      cirs 300,190,30,selected.val
      line 150,100,300,100,selected.val
      line 150,220,300,220,selected.val
      fill 150,100,150,120,selected.val
      line 120,130,120,190,selected.val
      fill 120,130,30,60,selected.val
      line 330,130,330,190,selected.val
      fill 300,130,30,60,selected.val
      pic 140,130,247
      xstr 225,145,120,35,7,65535,selected.val,0,1,3,"Español"
    }else
    {
      cirs 150,130,30,color
      cirs 300,130,30,color
      cirs 150,190,30,color
      cirs 300,190,30,color
      line 150,100,300,100,color
      line 150,220,300,220,color
      fill 150,100,150,120,color
      line 120,130,120,190,color
      fill 120,130,30,60,color
      line 330,130,330,190,color
      fill 300,130,30,60,color
      pic 140,130,211
      xstr 225,145,120,35,7,65535,color,0,1,3,"Español"
    }

Touch press event m1
--------------------

.. code-block:: javascript

    //changes the system language
    sys0=1
    //Deletes previous text
    fill 330,25,200,25,color
    //Italian
    xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Le lingue"
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    if(fondo==65534)
    {
      pic 370,130,212
    }else if(fondo==63391)
    {
      pic 370,130,218
    }else if(fondo==65438)
    {
      pic 370,130,224
    }else if(fondo==63421)
    {
      pic 370,130,230
    }else if(fondo==6339)
    {
      pic 370,130,236
    }else if(fondo==8484)
    {
      pic 370,130,242
    }
    xstr 455,145,120,35,7,BLACK,color,0,1,3,"Italiano"
    //It foucus only in this button changes the bg color of the other buttons
    //button 1
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    if(fondo==65534)
    {
      pic 140,130,211
    }else if(fondo==63391)
    {
      pic 140,130,217
    }else if(fondo==65438)
    {
      pic 140,130,223
    }else if(fondo==63421)
    {
      pic 140,130,229
    }else if(fondo==6339)
    {
      pic 140,130,235
    }else if(fondo==8484)
    {
      pic 140,130,241
    }
    xstr 225,145,120,35,7,BLACK,color,0,1,3,"Español"
    //button 3
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    if(fondo==65534)
    {
      pic 600,130,213
    }else if(fondo==63391)
    {
      pic 600,130,219
    }else if(fondo==65438)
    {
      pic 600,130,225
    }else if(fondo==63421)
    {
      pic 600,130,231
    }else if(fondo==6339)
    {
      pic 600,130,237
    }else if(fondo==8484)
    {
      pic 600,130,243
    }
    xstr 685,145,120,35,7,BLACK,color,0,1,3,"Français"
    //button 4
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    if(fondo==65534)
    {
      pic 140,300,214
    }else if(fondo==63391)
    {
      pic 140,300,220
    }else if(fondo==65438)
    {
      pic 140,300,226
    }else if(fondo==63421)
    {
      pic 140,300,232
    }else if(fondo==6339)
    {
      pic 140,300,238
    }else if(fondo==8484)
    {
      pic 140,300,244
    }
    xstr 225,315,120,35,7,BLACK,color,0,1,3,"Deutsch"
    //button 5
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    if(fondo==65534)
    {
      pic 370,300,215
    }else if(fondo==63391)
    {
      pic 370,300,221
    }else if(fondo==65438)
    {
      pic 370,300,227
    }else if(fondo==63421)
    {
      pic 370,300,233
    }else if(fondo==6339)
    {
      pic 370,300,239
    }else if(fondo==8484)
    {
      pic 370,300,245
    }
    xstr 455,315,120,35,7,BLACK,color,0,1,3,"English"
    //button 6
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    if(fondo==65534)
    {
      pic 600,300,216
    }else if(fondo==63391)
    {
      pic 600,300,222
    }else if(fondo==65438)
    {
      pic 600,300,228
    }else if(fondo==63421)
    {
      pic 600,300,234
    }else if(fondo==6339)
    {
      pic 600,300,240
    }else if(fondo==8484)
    {
      pic 600,300,246
    }
    xstr 685,315,120,35,7,BLACK,color,0,1,3,"Português"

Touch release event m1
----------------------

.. code-block:: javascript

    //Background color when is selected
    cirs 380,130,30,selected.val
    cirs 530,130,30,selected.val
    cirs 380,190,30,selected.val
    cirs 530,190,30,selected.val
    line 380,100,530,100,selected.val
    line 380,220,530,220,selected.val
    fill 380,100,150,120,selected.val
    line 350,130,350,190,selected.val
    fill 350,130,30,60,selected.val
    line 560,130,560,190,selected.val
    fill 530,130,30,60,selected.val
    pic 370,130,248
    xstr 455,145,120,35,7,65535,selected.val,0,1,3,"Italiano"

Touch press event m2
--------------------

.. code-block:: javascript

    //changes the system language
    sys0=2
    //Deletes previous text
    fill 330,25,200,25,color
    //French
    xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Langues"
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    if(fondo==65534)
    {
      pic 600,130,213
    }else if(fondo==63391)
    {
      pic 600,130,219
    }else if(fondo==65438)
    {
      pic 600,130,225
    }else if(fondo==63421)
    {
      pic 600,130,231
    }else if(fondo==6339)
    {
      pic 600,130,237
    }else if(fondo==8484)
    {
      pic 600,130,243
    }
    xstr 685,145,120,35,7,BLACK,color,0,1,3,"Français"
    //It foucus only in this button changes the bg color of the other buttons
    //button 1
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    if(fondo==65534)
    {
      pic 140,130,211
    }else if(fondo==63391)
    {
      pic 140,130,217
    }else if(fondo==65438)
    {
      pic 140,130,223
    }else if(fondo==63421)
    {
      pic 140,130,229
    }else if(fondo==6339)
    {
      pic 140,130,235
    }else if(fondo==8484)
    {
      pic 140,130,241
    }
    xstr 225,145,120,35,7,BLACK,color,0,1,3,"Español"
    //button 2
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    if(fondo==65534)
    {
      pic 370,130,212
    }else if(fondo==63391)
    {
      pic 370,130,218
    }else if(fondo==65438)
    {
      pic 370,130,224
    }else if(fondo==63421)
    {
      pic 370,130,230
    }else if(fondo==6339)
    {
      pic 370,130,236
    }else if(fondo==8484)
    {
      pic 370,130,242
    }
    xstr 455,145,120,35,7,BLACK,color,0,1,3,"Italiano"
    //button 4
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    if(fondo==65534)
    {
      pic 140,300,214
    }else if(fondo==63391)
    {
      pic 140,300,220
    }else if(fondo==65438)
    {
      pic 140,300,226
    }else if(fondo==63421)
    {
      pic 140,300,232
    }else if(fondo==6339)
    {
      pic 140,300,238
    }else if(fondo==8484)
    {
      pic 140,300,244
    }
    xstr 225,315,120,35,7,BLACK,color,0,1,3,"Deutsch"
    //button 5
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    if(fondo==65534)
    {
      pic 370,300,215
    }else if(fondo==63391)
    {
      pic 370,300,221
    }else if(fondo==65438)
    {
      pic 370,300,227
    }else if(fondo==63421)
    {
      pic 370,300,233
    }else if(fondo==6339)
    {
      pic 370,300,239
    }else if(fondo==8484)
    {
      pic 370,300,245
    }
    xstr 455,315,120,35,7,BLACK,color,0,1,3,"English"
    //button 6
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    if(fondo==65534)
    {
      pic 600,300,216
    }else if(fondo==63391)
    {
      pic 600,300,222
    }else if(fondo==65438)
    {
      pic 600,300,228
    }else if(fondo==63421)
    {
      pic 600,300,234
    }else if(fondo==6339)
    {
      pic 600,300,240
    }else if(fondo==8484)
    {
      pic 600,300,246
    }
    xstr 685,315,120,35,7,BLACK,color,0,1,3,"Português"

Touch release event m2
----------------------

.. code-block:: javascript

    //changes the bg color when is selected
    cirs 610,130,30,selected.val
    cirs 760,130,30,selected.val
    cirs 610,190,30,selected.val
    cirs 760,190,30,selected.val
    line 610,100,760,100,selected.val
    line 610,220,760,220,selected.val
    fill 610,100,150,120,selected.val
    line 580,130,580,190,selected.val
    fill 580,130,30,60,selected.val
    line 790,130,790,190,selected.val
    fill 760,130,30,60,selected.val
    pic 600,130,249
    xstr 685,145,120,35,7,65535,selected.val,0,1,3,"Français"

Touch press event m3
--------------------

.. code-block:: javascript

    //changes the system language
    sys0=4
    //Deletes previous text
    fill 330,25,200,25,color
    //German
    xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Sprachen"
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    if(fondo==65534)
    {
      pic 140,300,214
    }else if(fondo==63391)
    {
      pic 140,300,220
    }else if(fondo==65438)
    {
      pic 140,300,226
    }else if(fondo==63421)
    {
      pic 140,300,232
    }else if(fondo==6339)
    {
      pic 140,300,238
    }else if(fondo==8484)
    {
      pic 140,300,244
    }
    xstr 225,315,120,35,7,BLACK,color,0,1,3,"Deutsch"
    //It foucus only in this button changes the bg color of the other buttons
    //button 1
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    if(fondo==65534)
    {
      pic 140,130,211
    }else if(fondo==63391)
    {
      pic 140,130,217
    }else if(fondo==65438)
    {
      pic 140,130,223
    }else if(fondo==63421)
    {
      pic 140,130,229
    }else if(fondo==6339)
    {
      pic 140,130,235
    }else if(fondo==8484)
    {
      pic 140,130,241
    }
    xstr 225,145,120,35,7,BLACK,color,0,1,3,"Español"
    //button 2
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    if(fondo==65534)
    {
      pic 370,130,212
    }else if(fondo==63391)
    {
      pic 370,130,218
    }else if(fondo==65438)
    {
      pic 370,130,224
    }else if(fondo==63421)
    {
      pic 370,130,230
    }else if(fondo==6339)
    {
      pic 370,130,236
    }else if(fondo==8484)
    {
      pic 370,130,242
    }
    xstr 455,145,120,35,7,BLACK,color,0,1,3,"Italiano"
    //button 3
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    if(fondo==65534)
    {
      pic 600,130,213
    }else if(fondo==63391)
    {
      pic 600,130,219
    }else if(fondo==65438)
    {
      pic 600,130,225
    }else if(fondo==63421)
    {
      pic 600,130,231
    }else if(fondo==6339)
    {
      pic 600,130,237
    }else if(fondo==8484)
    {
      pic 600,130,243
    }
    xstr 685,145,120,35,7,BLACK,color,0,1,3,"Français"
    //button 5
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    if(fondo==65534)
    {
      pic 370,300,215
    }else if(fondo==63391)
    {
      pic 370,300,221
    }else if(fondo==65438)
    {
      pic 370,300,227
    }else if(fondo==63421)
    {
      pic 370,300,233
    }else if(fondo==6339)
    {
      pic 370,300,239
    }else if(fondo==8484)
    {
      pic 370,300,245
    }
    xstr 455,315,120,35,7,BLACK,color,0,1,3,"English"
    //button 6
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    if(fondo==65534)
    {
      pic 600,300,216
    }else if(fondo==63391)
    {
      pic 600,300,222
    }else if(fondo==65438)
    {
      pic 600,300,228
    }else if(fondo==63421)
    {
      pic 600,300,234
    }else if(fondo==6339)
    {
      pic 600,300,240
    }else if(fondo==8484)
    {
      pic 600,300,246
    }
    xstr 685,315,120,35,7,BLACK,color,0,1,3,"Português"

Touch release event m3
----------------------

.. code-block:: javascript

    //changes the bg color when is selected
    cirs 150,300,30,selected.val
    cirs 300,300,30,selected.val
    cirs 150,360,30,selected.val
    cirs 300,360,30,selected.val
    line 150,270,300,270,selected.val
    line 150,390,300,390,selected.val
    fill 150,270,150,120,selected.val
    line 120,300,120,360,selected.val
    fill 120,300,30,60,selected.val
    line 330,300,330,360,selected.val
    fill 300,300,30,60,selected.val
    pic 140,300,250
    xstr 225,315,120,35,7,65535,selected.val,0,1,3,"Deutsch"

Touch press event m4
--------------------

.. code-block:: javascript

    //changes the system language
    sys0=3
    //Deletes previous text
    fill 330,25,200,25,color
    //English
    xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Languages"
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    if(fondo==65534)
    {
      pic 370,300,215
    }else if(fondo==63391)
    {
      pic 370,300,221
    }else if(fondo==65438)
    {
      pic 370,300,227
    }else if(fondo==63421)
    {
      pic 370,300,233
    }else if(fondo==6339)
    {
      pic 370,300,239
    }else if(fondo==8484)
    {
      pic 370,300,245
    }
    xstr 455,315,120,35,7,BLACK,color,0,1,3,"English"
    //It foucus only in this button changes the bg color of the other buttons
    //button 1
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    if(fondo==65534)
    {
      pic 140,130,211
    }else if(fondo==63391)
    {
      pic 140,130,217
    }else if(fondo==65438)
    {
      pic 140,130,223
    }else if(fondo==63421)
    {
      pic 140,130,229
    }else if(fondo==6339)
    {
      pic 140,130,235
    }else if(fondo==8484)
    {
      pic 140,130,241
    }
    xstr 225,145,120,35,7,BLACK,color,0,1,3,"Español"
    //button 2
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    if(fondo==65534)
    {
      pic 370,130,212
    }else if(fondo==63391)
    {
      pic 370,130,218
    }else if(fondo==65438)
    {
      pic 370,130,224
    }else if(fondo==63421)
    {
      pic 370,130,230
    }else if(fondo==6339)
    {
      pic 370,130,236
    }else if(fondo==8484)
    {
      pic 370,130,242
    }
    xstr 455,145,120,35,7,BLACK,color,0,1,3,"Italiano"
    //button 3
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    if(fondo==65534)
    {
      pic 600,130,213
    }else if(fondo==63391)
    {
      pic 600,130,219
    }else if(fondo==65438)
    {
      pic 600,130,225
    }else if(fondo==63421)
    {
      pic 600,130,231
    }else if(fondo==6339)
    {
      pic 600,130,237
    }else if(fondo==8484)
    {
      pic 600,130,243
    }
    xstr 685,145,120,35,7,BLACK,color,0,1,3,"Français"
    //button 4
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    if(fondo==65534)
    {
      pic 140,300,214
    }else if(fondo==63391)
    {
      pic 140,300,220
    }else if(fondo==65438)
    {
      pic 140,300,226
    }else if(fondo==63421)
    {
      pic 140,300,232
    }else if(fondo==6339)
    {
      pic 140,300,238
    }else if(fondo==8484)
    {
      pic 140,300,244
    }
    xstr 225,315,120,35,7,BLACK,color,0,1,3,"Deutsch"
    //button 6
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    if(fondo==65534)
    {
      pic 600,300,216
    }else if(fondo==63391)
    {
      pic 600,300,222
    }else if(fondo==65438)
    {
      pic 600,300,228
    }else if(fondo==63421)
    {
      pic 600,300,234
    }else if(fondo==6339)
    {
      pic 600,300,240
    }else if(fondo==8484)
    {
      pic 600,300,246
    }
    xstr 685,315,120,35,7,BLACK,color,0,1,3,"Português"

Touch release event m4
----------------------

.. code-block:: javascript

    //changes the bg color when is selected
    cirs 380,300,30,selected.val
    cirs 530,300,30,selected.val
    cirs 380,360,30,selected.val
    cirs 530,360,30,selected.val
    line 380,270,530,270,selected.val
    line 380,390,530,390,selected.val
    fill 380,270,150,120,selected.val
    line 350,300,350,360,selected.val
    fill 350,300,30,60,selected.val
    line 560,300,560,360,selected.val
    fill 530,300,30,60,selected.val
    pic 370,300,251
    xstr 455,315,120,35,7,65535,selected.val,0,1,3,"English"

Touch press event m5
--------------------

.. code-block:: javascript

    //changes the system language
    sys0=5
    //Deletes previous text
    fill 330,25,200,25,color
    //Portuguese
    xstr 330,25,200,25,4,fontColor.val,color,1,1,3,"Línguas"
    cirs 610,300,30,color
    cirs 760,300,30,color
    cirs 610,360,30,color
    cirs 760,360,30,color
    line 610,270,760,270,color
    line 610,390,760,390,color
    fill 610,270,150,120,color
    line 580,300,580,360,color
    fill 580,300,30,60,color
    line 790,300,790,360,color
    fill 760,300,30,60,color
    if(fondo==65534)
    {
      pic 600,300,216
    }else if(fondo==63391)
    {
      pic 600,300,222
    }else if(fondo==65438)
    {
      pic 600,300,228
    }else if(fondo==63421)
    {
      pic 600,300,234
    }else if(fondo==6339)
    {
      pic 600,300,240
    }else if(fondo==8484)
    {
      pic 600,300,246
    }
    xstr 685,315,120,35,7,BLACK,color,0,1,3,"Português"
    //It foucus only in this button changes the bg color of the other buttons
    //button 1
    cirs 150,130,30,color
    cirs 300,130,30,color
    cirs 150,190,30,color
    cirs 300,190,30,color
    line 150,100,300,100,color
    line 150,220,300,220,color
    fill 150,100,150,120,color
    line 120,130,120,190,color
    fill 120,130,30,60,color
    line 330,130,330,190,color
    fill 300,130,30,60,color
    if(fondo==65534)
    {
      pic 140,130,211
    }else if(fondo==63391)
    {
      pic 140,130,217
    }else if(fondo==65438)
    {
      pic 140,130,223
    }else if(fondo==63421)
    {
      pic 140,130,229
    }else if(fondo==6339)
    {
      pic 140,130,235
    }else if(fondo==8484)
    {
      pic 140,130,241
    }
    xstr 225,145,120,35,7,BLACK,color,0,1,3,"Español"
    //button 2
    cirs 380,130,30,color
    cirs 530,130,30,color
    cirs 380,190,30,color
    cirs 530,190,30,color
    line 380,100,530,100,color
    line 380,220,530,220,color
    fill 380,100,150,120,color
    line 350,130,350,190,color
    fill 350,130,30,60,color
    line 560,130,560,190,color
    fill 530,130,30,60,color
    if(fondo==65534)
    {
      pic 370,130,212
    }else if(fondo==63391)
    {
      pic 370,130,218
    }else if(fondo==65438)
    {
      pic 370,130,224
    }else if(fondo==63421)
    {
      pic 370,130,230
    }else if(fondo==6339)
    {
      pic 370,130,236
    }else if(fondo==8484)
    {
      pic 370,130,242
    }
    xstr 455,145,120,35,7,BLACK,color,0,1,3,"Italiano"
    //button 3
    cirs 610,130,30,color
    cirs 760,130,30,color
    cirs 610,190,30,color
    cirs 760,190,30,color
    line 610,100,760,100,color
    line 610,220,760,220,color
    fill 610,100,150,120,color
    line 580,130,580,190,color
    fill 580,130,30,60,color
    line 790,130,790,190,color
    fill 760,130,30,60,color
    if(fondo==65534)
    {
      pic 600,130,213
    }else if(fondo==63391)
    {
      pic 600,130,219
    }else if(fondo==65438)
    {
      pic 600,130,225
    }else if(fondo==63421)
    {
      pic 600,130,231
    }else if(fondo==6339)
    {
      pic 600,130,237
    }else if(fondo==8484)
    {
      pic 600,130,243
    }
    xstr 685,145,120,35,7,BLACK,color,0,1,3,"Français"
    //button 4
    cirs 150,300,30,color
    cirs 300,300,30,color
    cirs 150,360,30,color
    cirs 300,360,30,color
    line 150,270,300,270,color
    line 150,390,300,390,color
    fill 150,270,150,120,color
    line 120,300,120,360,color
    fill 120,300,30,60,color
    line 330,300,330,360,color
    fill 300,300,30,60,color
    if(fondo==65534)
    {
      pic 140,300,214
    }else if(fondo==63391)
    {
      pic 140,300,220
    }else if(fondo==65438)
    {
      pic 140,300,226
    }else if(fondo==63421)
    {
      pic 140,300,232
    }else if(fondo==6339)
    {
      pic 140,300,238
    }else if(fondo==8484)
    {
      pic 140,300,244
    }
    xstr 225,315,120,35,7,BLACK,color,0,1,3,"Deutsch"
    //button 5
    cirs 380,300,30,color
    cirs 530,300,30,color
    cirs 380,360,30,color
    cirs 530,360,30,color
    line 380,270,530,270,color
    line 380,390,530,390,color
    fill 380,270,150,120,color
    line 350,300,350,360,color
    fill 350,300,30,60,color
    line 560,300,560,360,color
    fill 530,300,30,60,color
    if(fondo==65534)
    {
      pic 370,300,215
    }else if(fondo==63391)
    {
      pic 370,300,221
    }else if(fondo==65438)
    {
      pic 370,300,227
    }else if(fondo==63421)
    {
      pic 370,300,233
    }else if(fondo==6339)
    {
      pic 370,300,239
    }else if(fondo==8484)
    {
      pic 370,300,245
    }
    xstr 455,315,120,35,7,BLACK,color,0,1,3,"English"

Touch release event m5
----------------------

.. code-block:: javascript

    //changes the bg color when is selected
    cirs 610,300,30,selected.val
    cirs 760,300,30,selected.val
    cirs 610,360,30,selected.val
    cirs 760,360,30,selected.val
    line 610,270,760,270,selected.val
    line 610,390,760,390,selected.val
    fill 610,270,150,120,selected.val
    line 580,300,580,360,selected.val
    fill 580,300,30,60,selected.val
    line 790,300,790,360,selected.val
    fill 760,300,30,60,selected.val
    pic 600,300,252
    xstr 685,315,120,35,7,65535,selected.val,0,1,3,"Português"

Touch press event bInfoID
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

Touch release event bInfoID
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

Touch press event bHomeID
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

Touch release event bHomeID
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

Touch press event bBackID
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

Touch release event bBackID
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
