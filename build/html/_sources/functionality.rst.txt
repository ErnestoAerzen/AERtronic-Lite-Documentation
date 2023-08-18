Functionality
========================================

This section outlines the data transmission and handling functions within the AERtronic Basic sketch. The functions are encapsulated in the file `Functionality.hpp` and play a vital role in processing data received from the Nextion display, triggering relevant actions, and managing system status.

**Code Overview:**

The `Functionality.hpp` file encompasses the following significant functionalities:

1. **Data Transmission Handling (`sendData()`):**

The `sendData(int data_nextion)` function interprets incoming data from the Nextion display, directing the program's behavior accordingly. The function's conditional statements are responsible for:
- Updating the current display page based on the received data.
- Enabling or disabling digital inputs and outputs according to specific conditions.
- Managing Modbus functionality by activating or deactivating it based on input.
- Confirming maintenance and incrementing the maintenance count.
- Handling resets for errors and warnings, maintaining a clean state.

2. **Page and Status Management:**

The function distinguishes between various display pages and uses the `currentPage` variable to keep track of the active page. It manages start and stop statuses of the system, enabling coordinated control.

3. **Error and Warning Handling:**

For detected errors and warnings, the function captures the corresponding time and date, storing them in designated global variables. It also updates the system's status, indicating error or warning conditions. Events for errors and warnings are recorded with timestamps for future reference.

4. **Status Box Matrix:**

The `boxMatrix` array stores error and warning codes, mapping them to specific display positions for real-time visualization. This matrix ensures efficient tracking of error and warning occurrences.

This section provides an overview of the critical functions responsible for processing incoming data from the Nextion display, executing relevant actions, and maintaining system status within the AERtronic Basic sketch. For comprehensive insights into each function's inner workings and code segments, proceed to the subsequent sections for detailed explanations.

As always, consider that the formatting and presentation may be best appreciated in a reStructuredText viewer or editor that supports proper rendering.

.. code-block:: cpp

    #include <Arduino.h>
    #include "Functionality.hpp"
    #include "Functions.hpp"
    #include "timeESP.hpp"
    #include "preferences.hpp"
    #include "Inputs.hpp"
    #include "Outputs.hpp"
    #include "ModbusESP32.hpp"

    //Declaration of a Pages type variable
    Pages currentPage = NOPAGE;

    //Global strings to save the time and date when an error occurs:
    String timeErrorh0;
    String dateErrorh0;
    String timeErrorh1;
    String dateErrorh1;
    String timeErrorh2;
    String dateErrorh2;
    String timeErrorh3;
    String dateErrorh3;
    //Global strings to save the time and date when a warning appears:
    String timeWarningh0;
    String dateWarningh0;
    String timeWarningh1;
    String dateWarningh1;
    String timeWarningh2;
    String dateWarningh2;
    String timeWarningh3;
    String dateWarningh3;
    //Array to store the error an warning
    String boxMatrix[8] = {"null", "null", "null", "null", "null", "null", "null", "null"};


    /**
    * @brief Stores functionality for sending to the Nextion display according to what is received over serial
    */
    void sendData(int data_nextion) {
        //If else statements to update the page to display
        if(data_nextion == 4) {
            //Home page is int 4
            currentPage = HOME;
        } else if(data_nextion == 12) {
            //Presion page is int 12
            currentPage = PRESSURE;
        } else if(data_nextion == 13) {
            //Temperatura page is int 13
            currentPage = TEMP;
        } else if(data_nextion == 8) {
            //Intervalos page is int 8
            currentPage = INTERVALOS;
        } else if(data_nextion == 9) {
            //Tiempos page is int 9
            currentPage = PAGETIMES;
        } else if(data_nextion == 25) {
            //Mensajes page is int 25
            currentPage = MEN;
        } else if(data_nextion == 26) {
            //Eventos1 page is int 26
            currentPage = EVENTS;
        } else if(data_nextion == 34) {
            //ResetEv page is int 34
            currentPage = RESET_EV;
        } else if(data_nextion == 35) {
            //Resetmant page is int 35
            currentPage = RESET_MANT;
        } else if(data_nextion == 36) {
            //Advertencia page is int 36
            currentPage = ADVERTENCIA;
        } else if(data_nextion == 7) {
            //EstadoModulo page is int 7
            currentPage = ESTADO;
        } else if(data_nextion == 39) {
            //Menoria page is int 39
            currentPage = MEMORY;
        } else if(data_nextion == 27) {
            //Eventos2 page is int 27
            currentPage = EVENTS2;
        } else if(data_nextion == 28) {
            //Eventos3 page is int 28
            currentPage = EVENTS3;
        } else if(data_nextion == 29) {
            //Eventos4 page is int 29
            currentPage = EVENTS4; 
        } else if(data_nextion == 30) {
            //Eventos5 page is int 30
            currentPage = EVENTS5;
        } else if(data_nextion == 31) {
            //Eventos6 page is int 31
            currentPage = EVENTS6;
        } else if(data_nextion == 32) {
            //Eventos7 page is int 32
            currentPage = EVENTS7;
        } else if(data_nextion == 24) {
            //Comunicacion page is int 24
            currentPage = MODBUS;
        } else if(data_nextion == 40) {
            //ConfirmarM page is int 40
            currentPage = CONFIRM;
        }

        if(data_nextion == 254) {
            currentPage = NOPAGE;
        }
    
        //Enables and disables digital inputs and outputs
        if(data_nextion == 240) {
            start_status = HIGH;
            stop_status = LOW;
        } else if(data_nextion == 241) {
            start_status = LOW;
            stop_status = HIGH;
        } else if(data_nextion == 242) {
            start_status = LOW;
            stop_status = LOW;
        }

        //Additional functionality "ResetContador"
        if(data_nextion == 243) {
            resetOp();
        }

        //Modbus functionality
        //Modbus on
        if(data_nextion == 244) {
            setUpModbus();
            modbusStatus = true;
            //Sends a message to the nextion display
            Serial.print("fill 200,300,250,35,65535");
            endLine();
            Serial.print("xstr 200,300,250,35,6,RED,65535,1,1,3,\"Modbus On\"");
            endLine();
        } else if(data_nextion == 245) {
            //Modbus off
            modbusStatus = false;
            //Sends a message to the nextion display
            Serial.print("fill 700,455,100,25,65535");
            endLine();
            Serial.print("fill 200,300,250,35,65535");
            endLine();
            Serial.print("xstr 200,300,250,35,6,RED,65535,1,1,3,\"Modbus Off\"");
            endLine();
            Serial2.end();
        }

        //Confirm maintenance
        if(data_nextion == 239) {
            numberOfMaintenance++;
            //Space in memory to store the maintenance registers:
            register1.begin("maintenance", false);
            //Key to store the number of maintenances:
            register1.putInt("numOfMt", numberOfMaintenance);

            //Add a reset for the number of maintenance hours!!
        }

        //Reset errors and warnings
        if(data_nextion == 238) {
            boxMatrix[0] = "null";
            boxMatrix[1] = "null";
            boxMatrix[2] = "null";
            boxMatrix[3] = "null";
            boxMatrix[4] = "null";
            boxMatrix[5] = "null";
            boxMatrix[6] = "null";
            boxMatrix[7] = "null";
        }

        //Saves the time and date when an error occurs in h0 slide bar(Nextion): "ErrorH0"
        if(data_nextion == 246) {
            //Saves the returned strings to the corresponding global variables:
            timeErrorh0 = currentTime(rtc);
            dateErrorh0 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 2;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateErrorh0 + "-" + timeErrorh0 + " 7");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the error in its corresponding place according to the time it appeared:
            //Update first empty boxMatrix with "EH0"
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "EH0";
                    //An error in the h0 slidebar corresponds to 7 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=7");
                    endLine();
                    break;
                }
            }
        }

        //Saves the time and date when a warning occurs in h0 slide bar(Nextion): "WarningH0"
        if(data_nextion == 247) {
            //Saves the returned strings to the corresponding global variables:
            timeWarningh0 = currentTime(rtc);
            dateWarningh0 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 1;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateWarningh0 + "-" + timeWarningh0 + " 8");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the warning in its corresponding place according to the time it appeared:
            //Update first empty boxMatrix with "WH0"
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "WH0";
                    //A warning in the h0 slidebar corresponds to 8 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=8");
                    endLine();
                    break;
                }
            }
        }
    
        //Saves the time and date when an error occurs in h1 slide bar(Nextion): "ErrorH1"
        if(data_nextion == 248) {
            //Saves the returned strings to the corresponding global variables:
            timeErrorh1 = currentTime(rtc);
            dateErrorh1 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 2;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateErrorh1 + "-" + timeErrorh1 + " 1");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the error in its corresponding place according to the time it appeared:
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "EH1";
                    //An error in the h1 slidebar corresponds to 1 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=1");
                    endLine();
                    break;
                }
            }
        }
        //Saves the time and date when a warning occurs in h1 slide bar(Nextion): "WarningH1"
        if(data_nextion == 249) {
            //Saves the returned strings to the corresponding global variables:
            timeWarningh1 = currentTime(rtc);
            dateWarningh1 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 1;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateWarningh1 + "-" + timeWarningh1 + " 2");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the warning in its corresponding place according to the time it appeared:
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "WH1";
                    //A warning in the h1 slidebar corresponds to 2 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=2");
                    endLine();
                    break;
                }
            }
        }

        //Saves the time and date when an error occurs in the h2 slide bar(Nextion): "ErrorH2"
        if(data_nextion == 250) {
            //Saves the returned strings to the corresponding global variables:
            timeErrorh2 = currentTime(rtc);
            dateErrorh2 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 2;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateErrorh2 + "-" + timeErrorh2 + " 3");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the error in its corresponding place according to the time it appeared:
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "EH2";
                    //An error in the h2 slidebar corresponds to 3 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=3");
                    endLine();
                    break;
                }
            }
        }

        //Saves the time and date when a warning occurs in h2 slide bar(Nextion): "WarningH2"
        if(data_nextion == 251) {
            //Saves the returned strings to the corresponding global variables:
            timeWarningh2 = currentTime(rtc);
            dateWarningh2 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 1;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateWarningh2 + "-" + timeWarningh2 + " 4");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the warning in its corresponding place according to the time it appeared:
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "WH2";
                    //A warning in the h2 slidebar corresponds to 4 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=4");
                    endLine();
                    break;
                }
            }
        }

        //Saves the time and date when an error occurs in the h3 slide bar(Nextion): "ErrorH3"
        if(data_nextion == 252) {
            //Saves the returned strings to the corresponding global variables:
            timeErrorh3 = currentTime(rtc);
            dateErrorh3 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 2;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateErrorh3 + "-" + timeErrorh3 + " 5");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the error in its corresponding place according to the time it appeared:
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null") {
                    boxMatrix[i] = "EH3";
                    //An error in the h3 slidebar corresponds to 5 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=5");
                    endLine();
                    break;
                }
            }
        }

        //Saves the time and date when a warning occurs in h3 slide bar(Nextion): "WarningH3"
        if(data_nextion == 253) {
            //Saves the returned strings to the corresponding global variables:
            timeWarningh3 = currentTime(rtc);
            dateWarningh3 = currentDate(rtc);
            //Updates the status of the system
            statusDigital = 1;
            //Saves the system event:
            events.begin("eventos", false);
            events.putString("event" + char(contador), dateWarningh3 + "-" + timeWarningh3 + " 6");
            //Stores the number of total system events
            contador++;
            events.putInt("contador", contador);
            events.end();
            //Stores the warning in its corresponding place according to the time it appeared:
            for(int i = 0; i < 8; i++) {
                if(boxMatrix[i] == "null"){ 
                    boxMatrix[i] = "WH3";
                    //A warning in the h3 slidebar corresponds to 6 and sends it to the page Mensajes.box(i + 1)(Nextion):
                    Serial.print("box" + String(i + 1) + "=6");
                    endLine();
                    break;
                }
            }
        }
    }


Enum and Function Declarations for Page Management and Data Handling
--------------------------------------------------------------------

This section introduces the `.hpp` file named `Functionality.hpp`, which encapsulates key enumerations and function declarations that manage page navigation, error and warning handling, and data transmission within the AERtronic Basic sketch.

**Code Overview:**

The `Functionality.hpp` file includes the following significant components:

1. **Nextion Page Enumeration (`PAGES_H`):**

An enumeration named `Pages` defines symbolic constants representing various pages in the Nextion display interface. This enumeration serves as an organized way to manage and identify different display pages.

2. **Global Variables:**

Global variables are declared to store essential data, including time and date information associated with errors and warnings, as well as a matrix for tracking error and warning occurrences. The variable `currentPage` of the `Pages` type tracks the current active page.

3. **Function Declarations:**

The file includes function declarations for the functions:
- `sendData(int data_nextion)`: Handles data received from the Nextion display, executing actions based on the input.
- `page24()`: Specific functionality associated with the page numbered 24.

These declarations provide an interface for these functions and describe their intended purpose within the sketch.

This section offers a concise overview of the enumerated page options, global variables for error, warning, and page tracking, and the essential function declarations present within the `Functionality.hpp` file. For a comprehensive understanding of each enumerated value and function's role, including their code implementations, proceed to the subsequent sections for detailed explanations.

As always, consider that the formatting and presentation may be best appreciated in a reStructuredText viewer or editor that supports proper rendering.

.. code-block:: cpp

    #include <Arduino.h>

    //Enum to store the name of the Nextion pages
    #ifndef PAGES_H
    #define PAGES_H

    enum Pages {
        HOME,
        MEN,
        PAGETIMES,
        INTERVALOS,
        EVENTS,
        EVENTS2,
        EVENTS3,
        EVENTS4,
        EVENTS5,
        EVENTS6,
        EVENTS7,
        RESET_EV,
        RESET_MANT,
        ADVERTENCIA,
        ESTADO,
        MEMORY,
        MODBUS,
        NOPAGE,
        PRESSURE,
        TEMP,
        CONFIRM
    };
    #endif // PAGES_H
    //Variable to store the current page of the enum options
    extern Pages currentPage;
    //Global strings to save the time and date when an error occurs:
    extern String timeErrorh0;
    extern String dateErrorh0;
    extern String timeErrorh1;
    extern String dateErrorh1;
    extern String timeErrorh2;
    extern String dateErrorh2;
    extern String timeErrorh3;
    extern String dateErrorh3;
    //Global strings to save the time and date when a warning appears:
    extern String timeWarningh0;
    extern String dateWarningh0;
    extern String timeWarningh1;
    extern String dateWarningh1;
    extern String timeWarningh2;
    extern String dateWarningh2;
    extern String timeWarningh3;
    extern String dateWarningh3;
    //Array to store the error an warning
    extern String boxMatrix[8];
    //Counter to store the number of system events
    extern int contador;
    //Function declarations:
    void sendData(int data_nextion);
    void page24();