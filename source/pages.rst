Pages
=====

Nextion Display Functionality Module
------------------------------------

This module contains a collection of functions designed to facilitate information management and display on a Nextion display. These functions are specifically tailored for use when the display's active page is set to 24.

Functions
---------

page24()
    This function is responsible for populating the Nextion display with relevant information when the active page is set to 24. It iterates through a predefined set of boxes, each representing a potential error or warning scenario. Based on the status of these boxes, the function sends corresponding error, warning, time, and date data to the Nextion display. This dynamic data presentation allows users to quickly identify and respond to critical events.

printEvents(maxEvent, eventPage)
    This function serves the purpose of displaying stored events on the Nextion display. By retrieving event data stored in the system's preferences, the function selectively transmits this information to the display. The transmission includes relevant event details and is augmented with visual cues like alarm or warning indicators, providing users with essential event context at a glance.

deleteEvents()
    The deleteEvents function offers a way to manage the accumulation of event data by allowing users to wipe all stored events under the 'eventos' namespace. Through this operation, the function helps maintain a clutter-free event history, ensuring that only pertinent event data remains accessible.

deleteRegisters()
    As its name suggests, this function addresses the management of maintenance records. By clearing stored maintenance data within the 'maintenance' namespace, deleteRegisters supports the efficient organization of maintenance-related information. This includes resetting various maintenance-related variables, aiding in maintaining accurate maintenance records.

rebootSystem()
    In scenarios where a system reboot is necessary, the rebootSystem function provides a systematic approach. The function first introduces a delay of 5 seconds, allowing ongoing processes to conclude gracefully. After the delay, it triggers a system restart using the ESP.restart() function. This controlled reboot mechanism enhances system reliability and stability.

printMaintenances()
    This function offers users insight into the number of maintenance records present in the system. By sending the count of maintenance records to the Nextion display, printMaintenances fosters transparency, empowering users to make informed decisions regarding maintenance operations.

printMaintenanceMessage()
    Facilitating effective communication with users, printMaintenanceMessage generates graphical messages on the Nextion display. By strategically positioning circles, lines, and text, the function visually prompts users to perform necessary maintenance tasks. This visual guide simplifies user interaction and enhances the likelihood of timely and appropriate responses.

Module Dependencies
-------------------

- pages.hpp: Provides page-related functions and definitions for the Nextion display.
- Functionality.hpp: Offers utility functions for various system tasks.
- Functions.hpp: Contains a collection of functions for different aspects of the system.
- preferences.hpp: Provides functions to manage preferences and stored data.

.. code-block:: cpp

   #include "pages.hpp"
    #include "Functionality.hpp"
    #include "Functions.hpp"
    #include "preferences.hpp"


    /**
    * @brief Stores functionality for sending to the Nextion display when the page is 24
    */
    void page24() {
        for(int i = 0; i < 8; i++) {
            String box = boxMatrix[i];
            if(box == "EH1") {
                printErrorWarningTimeDate("T" + String(i + 1), timeErrorh1, dateErrorh1);
            } else if(box == "WH1") {
                printErrorWarningTimeDate("T" + String(i + 1), timeWarningh1, dateWarningh1);
            } else if(box == "EH2") {
                printErrorWarningTimeDate("T" + String(i + 1), timeErrorh2, dateErrorh2);
            } else if(box == "WH2") {
                printErrorWarningTimeDate("T" + String(i + 1), timeWarningh2, dateWarningh2);
            } else if(box == "EH3") {
                printErrorWarningTimeDate("T" + String(i + 1), timeErrorh3, dateErrorh3);
            } else if(box == "WH3") {
                printErrorWarningTimeDate("T" + String(i + 1), timeWarningh3, dateWarningh3);
            } else if(box == "EH0") {
                printErrorWarningTimeDate("T" + String(i + 1), timeErrorh0, dateErrorh0);
            } else if(box == "WH0") {
                printErrorWarningTimeDate("T" + String(i + 1), timeWarningh0, dateWarningh0);
            }
        }
    }

    /**
     * @brief Sends the stored events to the Nextion display
    */
    void printEvents(int maxEvent, int eventPage) {
        events.begin("eventos" , false);
        for(int i = maxEvent - 13; i < maxEvent; i++) {
            String currentEvent = events.getString("event" + char(i), "");
            Serial.print("Eventos" + String(eventPage) + ".e" + String(i + 1) + ".txt=\"" + currentEvent);
            if(currentEvent[currentEvent.length() - 1] == '7') {
                Serial.print(" Suction pressure alarm\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '8') {
                Serial.print(" Suction pressure warning\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '1') {
                Serial.print(" Final pressure alarm\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '2') {
                Serial.print(" Final pressure warning\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '3') {
                Serial.print(" Final temperature alarm\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '4') {
                Serial.print(" Final temperature warning\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '5') {
                Serial.print(" Oil temperature alarm\"");
                endLine();
            } else if(currentEvent[currentEvent.length() - 1] == '6') {
                Serial.print(" Oil temperature warning\"");
                endLine();
            } else {
                Serial.print(" \"");
                endLine();
            }
        } 
        events.end();
    }

    void deleteEvents() {
        //Deletes all preferences under the namespace
        events.begin("eventos", false);
        events.clear();
        events.end();
        contador = 0;
        Serial.print("ResetEv.eText.txt=\"Eventos eliminados\"");
        endLine();
    }

    void deleteRegisters() {
        //Deletes all preferences under this namaspace
        register1.begin("maintenance", false);
        register1.clear();
        register1.end();
        mhours = 0;
        mmotor = 0;
        lmotor = 0;
        m4hours = 0;
        m8hours = 0;
        Serial.print("ResetMant.rText.txt=\"Registros eliminados\"");
        endLine();
    }

    void rebootSystem() {
        delay(5000);
        ESP.restart();
    }

    void printMaintenances() {
        Serial.print("ConfirmarM.t0.txt=\"" + String(numberOfMaintenance) + "\"");
        endLine();
    }

    void printMaintenanceMessage() {
        Serial.print("cirs 150,40,30,0x42EE");
        endLine();
        Serial.print("cirs 760,40,30,0x42EE");
        endLine();
        Serial.print("line 150,10,760,10,0x42EE");
        endLine();
        Serial.print("line 150,70,760,70,0x42EE");
        endLine();
        Serial.print("fill 150,10,610,60,0x42EE");
        endLine();
        Serial.print("xstr 160,30,250,25,4,65535,63488,0,0,3,\"Realizar mantenimiento\"");
        endLine();
    }

Pages header
------------

This header file defines a set of functions intended to manage and display information on a Nextion display when the active page is set to 24. These functions offer dynamic data presentation, event management, and system maintenance capabilities.

Functions
---------

page24()
    This function is designed to be invoked when the active page on the Nextion display is set to 24. Its purpose is to populate the display with contextually relevant information based on the status of predefined boxes. The function facilitates the visualization of errors, warnings, time, and date data associated with specific scenarios.

printEvents(maxEvent, eventPage)
    Responsible for displaying stored event data on the Nextion display, this function communicates event details to the user. It retrieves event information from the system's preferences and presents it in a user-friendly format on the display. Visual indicators like alarm or warning icons provide immediate context about event severity.

deleteEvents()
    This function allows users to manage the accumulation of event data by clearing all stored events within the 'eventos' namespace. By invoking this function, users can maintain a streamlined event history, focusing on critical events while eliminating obsolete ones.

deleteRegisters()
    Addressing the management of maintenance records, this function clears stored maintenance data under the 'maintenance' namespace. It contributes to organized maintenance record keeping by resetting relevant variables and ensuring accurate records are maintained.

rebootSystem()
    When a controlled system reboot is required, the rebootSystem function provides a systematic approach. It introduces a delay to allow ongoing processes to conclude and then initiates a system restart using the ESP.restart() function. This controlled reboot mechanism enhances system reliability and stability.

printMaintenances()
    This function informs users about the number of maintenance records stored in the system. It communicates the count of maintenance records to the Nextion display, empowering users to make informed decisions regarding maintenance operations.

printMaintenanceMessage()
    Offering visual guidance to users, this function generates graphical messages on the Nextion display. By positioning graphical elements strategically, it prompts users to perform required maintenance tasks. This visual approach simplifies user interaction and encourages timely responses.

Function Dependencies
---------------------

- Arduino.h: Core header providing fundamental definitions and functions for the Arduino platform.

.. code-block:: cpp

    #include <Arduino.h>

    void page24();
    void printEvents(int maxEvent, int eventPage);
    void deleteEvents();
    void deleteRegisters();
    void rebootSystem();
    void printMaintenances();
    void printMaintenanceMessage();