Modbus
======

Modbus Communication and Control Code
-------------------------------------

This section introduces a source code file named `ModbusESP32.hpp`. This file handles Modbus communication using the ModbusMaster library and controls Modbus-related operations within the AERtronic Basic sketch.

**Code Overview:**

The `ModbusESP32.hpp` source code file includes the following significant components:

1. **Include Statements:**

The header file includes relevant libraries required for Modbus communication and functionality, such as `<ModbusMaster.h>`, "Outputs.hpp," and "Functions.hpp."

2. **Modbus Configuration:**

- Definitions for MAX485 DE (Data Enable) and RE_NEG (Receive Enable) pins are provided using the `#define` directive.
- An instance of the `ModbusMaster` class, named `node`, is created to manage Modbus communication.
- A boolean variable, `modbusStatus`, is declared to store the status of Modbus communication (active or inactive).

3. **Modbus Initialization:**

The function `setUpModbus()` is defined to set up the Modbus communication. This includes configuring the MAX485 pins, initializing the serial communication, and starting Modbus communication with a specific slave ID.

4. **Sending Modbus Data:**

The function `sendModbus()` is defined to send Modbus data. The appropriate data value (`200`, `300`, or `400`) is determined based on the `statusDigital` variable. The function sends the data to a specific register using the `node.writeSingleRegister()` function and provides appropriate feedback messages.

5. **Printing Modbus Data:**

The function `printModbus()` prints the current Modbus data value to a designated display element on the Nextion display. This function updates the graphical representation of Modbus communication status.

This section provides a concise summary of the key components and functionality of the `ModbusESP32.hpp` source code file. For a detailed understanding of the code implementation and its interactions, refer to the subsequent sections.

.. code-block:: cpp

    #include "ModbusESP32.hpp"
    #include <ModbusMaster.h>
    #include "Outputs.hpp"
    #include "Functions.hpp"

    //Definition of pin DE of module MAX485 (TX)
    #define MAX485_DE 17
    //Definition of pin RE_NEG of module MAX485 (RX)
    #define MAX485_RE__NEG 16

    //Creation of an instance of ModbusMaster
    ModbusMaster node;

    //Variable to store the status of Modbus(active or inactive)
    bool modbusStatus = false;

    //Sends data over Modbus RTU: 200-Ok, 300-Warning, 400-Error
    int data = 0; //Update this value according to what is needed!!!

    void setUpModbus() {
        //Configure pins MAX485_RE__NEG and MAX485_DE as outputs
        pinMode(MAX485_RE__NEG, OUTPUT);
        pinMode(MAX485_DE, OUTPUT);
        //Set pin RE_NEG as HIGH (Disable reception)
        digitalWrite(MAX485_RE__NEG, 1);
        //Set pin DE as HIGH (Enable transmission)
        digitalWrite(MAX485_DE, 1);

        //Begin serial communication at 115200 baud rate:
        Serial2.begin(115200);
        //Waits until Serial2 port opens:
        while(!Serial2) {
            ;
        }

        //Start Modbus RTUcommunication with slave id = 1
        node.begin(1, Serial2);
    }

    void sendModbus() {

        // Verificar si se ha presentado un evento en el sistema
        // Por ejemplo, si un sensor ha detectado un valor fuera de los límites normales
        if(statusDigital == 0) {
            data = 200;
        } else if(statusDigital == 1) {
            data = 300;
        } else if(statusDigital == 2) {
            data = 400;
        }

        //Sends the value of data to the 0 register of the slave
        uint8_t result = node.writeSingleRegister(0, data);

        if(result == node.ku8MBSuccess) {
            //Prints a succesful message of transmission
            Serial2.println("Succesful data sent");
        } else {
            //Print a failure message of transmission
            Serial2.print("Unable to send data, result = ");
            //Prints the result of the operation:
            Serial2.println(result);
        }

        Serial.print("fill 700,455,100,25,65535");
        endLine();
        Serial.print("xstr 700,445,100,25,6,RED,65535,1,1,3,\"Modbus On\"");
        endLine();
    }

    void printModbus() {
        Serial.print("Comunicacion.tm.txt=\"" + String(data) + "\"");
        endLine();
    }

Modbus Communication and Control Header
---------------------------------------

This section introduces a header file named `ModbusESP32.hpp`. This header file declares function prototypes and global variables related to Modbus communication and control within the AERtronic Basic sketch.

**Header Overview:**

The header file includes the following significant declarations:

1. **Function Prototypes:**

The header declares three functions that are crucial for Modbus communication and control:

- `setUpModbus()`: This function sets up the Modbus communication by configuring the necessary pins, initializing serial communication, and starting Modbus communication with a specific slave ID.
- `sendModbus()`: This function sends Modbus data based on the current `statusDigital` value. The data is sent to a specific register using the ModbusMaster library functions.
- `printModbus()`: This function prints the current Modbus data value to a designated display element on the Nextion display.

2. **Global Variables:**

The header declares the following global variables:

- `modbusStatus`: A boolean variable that stores the status of Modbus communication (active or inactive).
- `data`: An integer variable that holds the data value to be sent over Modbus. The value is determined based on the `statusDigital` variable.

These function prototypes and global variables are essential components of Modbus communication and control in the AERtronic Basic sketch. They enable effective interaction with Modbus devices and update the Nextion display with relevant information.

This section provides a concise overview of the function prototypes and global variables declared in the `ModbusESP32.hpp` header file. For a comprehensive understanding of how these components are utilized and their interactions within the sketch, refer to the subsequent sections.

.. code-block:: cpp

    #include <Arduino.h>

    void setUpModbus();
    void sendModbus();
    void printModbus();
    
    extern bool modbusStatus;
    extern int data;
