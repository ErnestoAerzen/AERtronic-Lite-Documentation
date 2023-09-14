Popup Nextion Page
=====================

Description
-----------

Introduction
------------

This document provides a detailed explanation of a Nextion display script used to display a system message based on the selected language. The message is accompanied by a background color change and a timer to exit the message.

Script Overview
---------------

The script consists of the following sections:

1. **Background Color Change (t0.bco=fondo)**
   - This command changes the background color of text component `t0` based on the value of `fondo`.

2. **System Message**
   - The script displays a system message in different languages based on the value of `sys0`.
   - The message text is assigned to the `t0.txt` property of text component `t0`.

3. **Timer to Exit (tm0.en=1)**
   - A timer (`tm0`) is enabled (`tm0.en=1`) to automatically exit the displayed message after a set duration.

Script Explanation
------------------

Let's break down each section of the script:

1. **Background Color Change**
   - The background color of text component `t0` is changed based on the value of `fondo`. This allows for visual distinction of messages based on the theme.

2. **System Message**
   - Depending on the selected language (`sys0`), a system message is displayed in the appropriate language. Supported languages include Spanish, Italian, French, English, German, and Portuguese.
   - The text is assigned to the `t0.txt` property of text component `t0`. This text component is commonly used to display messages.

3. **Timer to Exit**
   - A timer (`tm0`) is enabled (`tm0.en=1`) to ensure that the displayed message automatically exits after a specified duration. The timer configuration is not shown in this script and should be set separately.

Conclusion
-----------

This documentation provides insight into the functionality of a Nextion display script designed to display system messages in different languages. It outlines the color customization and automatic message exit features to enhance the user interface. Developers can adapt this script to display messages and provide multilingual support in their Nextion display applications.

Please note that this script serves as an example and should be integrated into a complete Nextion display project with appropriate timer settings and any additional features as needed.

Preinitialize event Popup
-------------------------

.. code-block:: javascript

    // Changes the page's background color
    Popup.bco=fondo

Postinitialize event Popup
--------------------------

.. code-block:: javascript

    //Message
    t0.bco=fondo
    if(sys0==0)
    {
      t0.txt="Por favor asegúrese que ha tomado en cuenta los mensajes del sistema."
    }else if(sys0==1)
    {
      t0.txt="Assicurati di aver preso in considerazione i messaggi di sistema."
    }else if(sys0==2)
    {
      t0.txt="Assurez-vous d'avoir pris en compte les messages système."
    }else if(sys0==3)
    {
      t0.txt="Please make sure that you have taken system messages into account."
    }else if(sys0==4)
    {
      t0.txt="Bitte stellen Sie sicher, dass Sie Systemmeldungen berücksichtigt haben."
    }else if(sys0==5)
    {
      t0.txt="Certifique-se de ter levado em consideração as mensagens do sistema."
    }
    //Timer to exit
    tm0.en=1
