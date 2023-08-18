main
====

Main Program Logic for MCU-Nextion Command Communication
--------------------------------------------------------

This section presents the core logic of the AERtronic Basic sketch (`src.ino`), which is responsible for establishing communication and interaction between an ESP32 microcontroller unit (MCU) and a Nextion display. The code orchestrates various functions to manage inputs, outputs, time synchronization, page-specific operations, and more.

**Code Overview:**

The main program is split into the `mainSetup()` and `mainLoop()` functions, each serving distinct purposes during the execution of the sketch.

`mainSetup()`
--------------

The `mainSetup()` function initializes essential components and prepares the system for operation. The following steps are performed:

- Serial communication is established at a baud rate of 115200.
- Digital inputs and outputs are configured using `inputsFunc()` and `outputFunc()` functions, respectively.
- Time and date synchronization with the Nextion display is awaited through `receiveTime()` function.
- The necessary namespaces for boot counting, preferences, registers, and events are initialized.
- A delay of 500 milliseconds is included to ensure stability.

`mainLoop()`
-------------

The `mainLoop()` function is responsible for the ongoing operation of the sketch. It performs the following tasks in a cyclic manner:

- Executes common functions for all pages, such as reading serial data, updating internal time, and reading analog sensor values.
- Depending on the current page displayed on the Nextion display, specific operations are performed:
  - Analog values are read and printed for home, pressure, and temperature pages.
  - Current time and date are displayed for various pages.
  - Page-specific functions are called, like handling messages, sending time data, displaying maintenance intervals, and managing events.
  - Input and output status is monitored on the ESTADO (state) page.
  - Modbus data is sent on the MODBUS page if modbusStatus is true.
  - Maintenance messages are displayed if maintenance hours exceed a certain threshold.
- The loop continues to run at a one-second interval using a delay of 1000 milliseconds.

Additionally, specific conditions trigger actions such as returning to the home page in the event of warnings or errors, sending Modbus data if enabled, and displaying maintenance messages.

This section provides an overview of the core functionality of the AERtronic Basic sketch. For more detailed explanations of individual functions, specific page operations, and code segments, refer to subsequent sections.

.. code-block:: cpp

    //Insert header files here:
    #include "Functions.hpp"
    #include "Functionality.hpp"
    #include "Inputs.hpp"
    #include "Outputs.hpp"
    #include "timeESP.hpp"
    #include "preferences.hpp"
    #include "pages.hpp"
    #include "ModbusESP32.hpp"

    void mainSetup() {
        //Initializes serial communication at the desire baud rate:
        Serial.begin(115200);

        //Set the digital inputs & outputs:
        inputsFunc();
        outputFunc();

        //Waits until receives time and date from Nextion display
        receiveTime();

        //Initializes the namespaces that stores every time the ESP32 is booted and the maintenance registers:
        bootCounter(preferences, register1, events);

        //Including a delay time for stability
        delay(500);
    }

    void mainLoop() {
        //Functions that executes in all pages:
        //Function that sends/receives serial data
        serialRead();
        //Internal clock and updates variables to store in NVS memory
        opTime();
        //Always read sensor
        analogValue();

        //Functions that executes in each page:
        switch (currentPage) {
        case HOME:
            //Functions that read analog values
            //analogValue();
            printAnalogValuesHome();
            //Displays the current time and date in the home page
            currentTime(rtc_current);
            currentDate(rtc_current);
            break;
        case PRESSURE:
            //Function that reads analog value only for pressure sensors
            //analogValue();
            printAnalogValuesPressure();
            //Displays the current time and date in the pressure page
            currentTime(rtc_current);
            currentDate(rtc_current);
            break;
        case TEMP:
            //Function that reads analog values only for temperature sensors
            //analogValue();
            printAnalogValuesTemp();
            //Displays the current time and date in the temp page
            currentTime(rtc_current);
            currentDate(rtc_current);
            break;
        case MEN:
            //Only calls the function if the page is 24/Mensajes:
            page24();    
            break;
        case PAGETIMES:
            //Sends the time to the display
            printopTime();
            break;
        case INTERVALOS:
            //Sends the maintenance intervals:
            printInterval1();
            break;
        case EVENTS:
            //Sends the stored events:
            // First parameter = number of places in the event log, second parameter = page number
            printEvents(13, 1);
            break;
        case EVENTS2:
            //Sends the stored events:
            printEvents(26, 2);
            break;
        case EVENTS3:
            //Sends the stored events:
            printEvents(39, 3);
            break;
        case EVENTS4:
            //Sends the stored events:
            printEvents(52, 4);
            break;
        case EVENTS5:
            //Sends the stored events:
            printEvents(65, 5);
            break;
        case EVENTS6:
            //Sends the stored events:
            printEvents(78, 6);
            break;
        case EVENTS7:
            //Sends the stored events:
            printEvents(91, 7);
            break;     
        case RESET_EV:
            //Function to delete events
            deleteEvents();
            break;
        case RESET_MANT:
            //Function to delete maintenance registers
            deleteRegisters();
            break;
        case ADVERTENCIA:
            //Reboots the system to change time and date
            rebootSystem();
            break;
        case ESTADO:
            //Reads the digital inputs and outputs
            readInputs();
            outputStatus();
            break;
        case MEMORY:
            //Sends the state of the memory over serial
            printMemory();
            break;
        case MODBUS: 
            //Sends the current data to the comunacion page
            printModbus();
            break;
        case CONFIRM:
            //Prints the number of maintenances
            printMaintenances();                      
        default:
        break;
        }

        //Goes back to the home page if there is a warning or error
        if(currentPage != HOME && (potValue > 3000 || potValue2 > 3000 || potValue3 > 3000)) {
            Serial.print("page Home");
            endLine();
        }

        //Modbus functionality
        if(modbusStatus) {
            sendModbus();
        }

        //Sends a message to indicate that a maintenance is required
        if(mhours > 500) {
            printMaintenanceMessage();
        }
    
        //Repeats the loop function every time after the delay, 1000=1 seg because of the ESP32 time rtc functions to store time and date every second:
        delay(1000);
    }

Header Declarations for Main Program Logic
------------------------------------------

This section outlines the header declarations for the main program logic of the AERtronic Basic sketch. The declarations are included in the `main.hpp` header file and serve as the interface to the primary functions `mainSetup()` and `mainLoop()`, which orchestrate the communication and interaction between an ESP32 microcontroller unit (MCU) and a Nextion display.

**Code Overview:**

`mainSetup()`
--------------

The `mainSetup()` function is responsible for initializing essential components and setting up the system for operation. It performs tasks such as configuring serial communication, initializing digital inputs and outputs, synchronizing time with the Nextion display, and preparing namespaces and preferences. A delay is included to ensure stability.

`mainLoop()`
-------------

The `mainLoop()` function manages the ongoing operation of the sketch. It executes common functions for all pages, handles page-specific operations based on the current display page, and manages various conditions such as warnings, errors, and maintenance messages. The loop maintains a one-second interval using a delay.

The `main.hpp` header file serves as the entry point for these functions and encapsulates the core logic of the AERtronic Basic sketch.

For comprehensive details on the implementation of `mainSetup()` and `mainLoop()`, as well as their roles in establishing MCU-Nextion communication and interaction, refer to the subsequent sections for more in-depth explanations and code segments.

.. code-block:: cpp

    #include <Arduino.h>

    void mainSetup();
    void mainLoop();