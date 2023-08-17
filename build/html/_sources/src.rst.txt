src
=====

Project Overview
----------------

The AERtronic Basic sketch, named `src.ino`, serves as a program facilitating the exchange of commands between an ESP32 microcontroller unit (MCU) and a Nextion display. The code acts as a bridge, enabling communication between these two components, allowing seamless interaction and control.

**Author:** Ernesto Estrada / Aerzen Controls Team MX
**Version:** 2.0
**Dates:**
- Initial Release: 04/08/2022
- Last Update: 14/04/2023

Description
-----------

The purpose of this sketch is to establish a functional link between an ESP32 MCU and a Nextion display, enabling bidirectional communication. The MCU sends commands to the display, and the display responds accordingly, facilitating a dynamic user interface and control experience.

The setup involves a modular approach, with the main functionality divided into separate functions. The `main.hpp` file is included to ensure the necessary declarations are accessible. The setup phase initializes the communication and prepares the environment for execution. The main loop iterates to manage ongoing interactions between the MCU and the Nextion display.

This documentation aims to provide an understanding of the AERtronic Basic sketch's structure, purpose, and usage. Further sections will delve into the specific functions, variables, and processes involved in enabling seamless communication between the ESP32 MCU and the Nextion display.

Please refer to the subsequent sections for detailed explanations of key components, functions, and any additional information pertinent to utilizing the AERtronic Basic sketch effectively.

.. code-block:: cpp

    /**
     * AERtronic Basic
     * Name of the sketch: src.ino
     * Purpose: Program to send commands between the MCU ESP32 and the Nextion display.
     * 
     * :author: Ernesto Estrada / Aerzen Controls Team MX
     * :version: 2.0
     * Date: 04/08/2022
     * Update: 14/04/2023
     * 
     * Other information will be added here.
     */

    #include "main.hpp"

    // Setup code here, to run once:
    void setup() {
        mainSetup();
    }

    // Main code here, to run repeatedly:
    void loop() {
        mainLoop();
    }