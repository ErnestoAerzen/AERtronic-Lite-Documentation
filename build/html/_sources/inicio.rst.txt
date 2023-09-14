Inicio Nextion Page
============================

Description
-----------

Overview
--------

This document provides a detailed explanation of the Nextion display script designed to enhance the user interface and functionality. The script is intended for use with the Nextion Editor and comprises two key components: enabling a timer and theme-based icon customization.

Script Structure
----------------

The script consists of the following sections:

**Enabling the Timer**
~~~~~~~~~~~~~~~~~~~~

This section serves to enable a timer labeled "tm0." By setting the "tm0.en" attribute to 1, the timer is activated. Timers in Nextion displays can be used for various purposes, such as triggering events at specific intervals.

**Themes and Aerzen Icons**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Conditional logic is employed in this section to customize icons based on the value of the "fondo" variable, which presumably represents different themes. Each theme is associated with a unique set of icons related to "Aerzen."

- If the "fondo" variable equals 65534, a specific set of Aerzen icons is displayed using the "pic" command. These icons are positioned at coordinates (260, 200) and (340, 214) with corresponding index values 6 and 7.

- Similar conditional blocks exist for other values of the "fondo" variable (63391, 65438, 63421, 6339, and 8484), each defining a distinct set of Aerzen icons for the chosen theme. The icons' positions and index values are specified within each conditional block.

Usage
-----

This script is intended for use with the Nextion Editor, a visual interface design tool for Nextion displays. The script enhances the user experience by enabling a timer and dynamically customizing icons based on the selected theme.

To implement this script effectively, ensure that the Nextion display is configured to handle the defined timer ("tm0") and that the "fondo" variable corresponds to the available themes. Additionally, ensure that the icon images are available and properly indexed within the Nextion Editor.

Users can interact with the display, and the icons will reflect their chosen theme, providing a visually pleasing and user-friendly experience.

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

Preinitialize event Inicio
--------------------------

.. code-block:: javascript

    // Change the background color of the page 
    Inicio.bco=fondo

Postinitialize event Inicio
---------------------------

.. code-block:: javascript

    // Enables the timer tm0
    tm0.en=1
    //Themes
    if(fondo==65534)
    {
      //Aerzen icons
      pic 260,200,6
      pic 340,214,7
    }else if(fondo==63391)
    {
      //Aerzen icons
      pic 260,200,8
      pic 340,214,9
    }else if(fondo==65438)
    {
      //Aerzen icons
      pic 260,200,10
      pic 340,214,11
    }else if(fondo==63421)
    {
      //Aerzen icons
      pic 260,200,12
      pic 340,214,13
    }else if(fondo==6339)
    {
      //Aerzen icons
      pic 260,200,14
      pic 340,214,15
    }else if(fondo==8484)
    {
      //Aerzen icons
      pic 260,200,16
      pic 340,214,17
    }

Timer event tm0
---------------

.. code-block:: javascript

    tm0.tim=100
    counter.val++
    //Themes start
    if(fondo==65534)
    {
      p0.pic=va0.val
      va0.val++
      if(va0.val>37)
      {
        va0.val=30
      }
    }else if(fondo==63391)
    {
      p0.pic=va1.val
      va1.val++
      if(va1.val>45)
      {
        va1.val=38
      }
    }else if(fondo==65438)
    {
      p0.pic=va2.val
      va2.val++
      if(va2.val>53)
      {
        va2.val=46
      }
    }else if(fondo==63421)
    {
      p0.pic=va3.val
      va3.val++
      if(va3.val>61)
      {
        va3.val=54
      }
    }else if(fondo==6339)
    {
      p0.pic=va4.val
      va4.val++
      if(va4.val>69)
      {
        va4.val=62
      }
    }else if(fondo==8484)
    {
      p0.pic=va5.val
      va5.val++
      if(va5.val>77)
      {
        va5.val=70
      }
    }
    //Thems end
    if(counter.val==50)
    {
      page Home
    }
    