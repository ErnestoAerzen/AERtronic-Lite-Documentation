Outputs
=======

Digital Outputs Control
-----------------------

This section introduces the code file named `Outputs.hpp`. This code file contains functions and declarations related to controlling digital outputs in the AERtronic Basic sketch.

**Code Overview:**

The code file includes the following significant components:

1. **Digital Output Pins:**

The code file defines constants to represent the pin numbers for the digital outputs used in the system:

- `OKAY`: Represents the pin number for the "OK" output.
- `WARNING`: Represents the pin number for the "WARNING" output.
- `ALARM`: Represents the pin number for the "ALARM" output.

2. **Global Variable:**

The code file declares a global variable:

- `statusDigital`: An integer variable that stores the current status of the system. The value can be 0 (OK), 1 (WARNING), or 2 (ALARM). The variable is used to determine which output should be active based on the system's status.

3. **Function Definitions:**

The code file defines the following functions:

- `outputFunc()`: This function sets up the digital output pins by configuring them as outputs.
- `outputStatus()`: This function controls the state of the digital outputs based on the `statusDigital` value. It adjusts the state of the output pins to represent the system's status (OK, WARNING, or ALARM).

These function definitions and global variables are integral to controlling the digital outputs of the AERtronic Basic sketch. They ensure that the appropriate output is activated based on the system's status and contribute to the overall functionality of the system.

This section provides a concise overview of the digital outputs control code in the `Outputs.hpp` file. For a comprehensive understanding of how these components are utilized and their interactions within the sketch, refer to the subsequent sections.

.. code-block:: cpp

    #include "Outputs.hpp"
    #include "Functions.hpp"
    #include <Arduino.h>

    //Set the GPIO we are going to use as digital outputs
    //Set pin numbers:
    const int OKAY = 26;
    const int WARNING = 27;
    const int ALARM = 14;
    //Variable to store the current status of the system, 0=OK, 1=WARNIGN, 2=ALARM
    int statusDigital = 0;

    /**
     * @brief Function to set the digital outputs that are going to be included in the main file
     * @return void
    */
    void outputFunc() {
        //Digital output OK
        pinMode(OKAY, OUTPUT);
        //Digital output WARNING
        pinMode(WARNING, OUTPUT);
        //Digital output ALARM
        pinMode(ALARM, OUTPUT);
    }

    void outputStatus() {
        if(statusDigital == 0) {
            //Pin 26 indicates everything is OK
            digitalWrite(OKAY, HIGH);
            digitalWrite(WARNING, LOW);
            digitalWrite(ALARM, LOW);
            //Shows that the pin 26 in enable
            Serial.print("cirs 200,270,20,0x3B44");
            endLine();
            //Shows that there are no warnings or errors
            Serial.print("cirs 200,340,20,RED");
            endLine();
            Serial.print("cirs 200,410,20,RED");
            endLine();
        } else if(statusDigital == 1) {
            //Pin 27 indicates that there is a warning active
            digitalWrite(WARNING, HIGH);
            digitalWrite(OKAY, LOW);
            digitalWrite(ALARM, LOW);
            //Shows the status of the outputs
            Serial.print("cirs 200,270,20,RED");
            endLine();
            Serial.print("cirs 200,340,20,0x3B44");
            endLine();
            Serial.print("cirs 200,410,20,RED");
            endLine();
        } else if(statusDigital == 2) {
            //Pin 14 indicates that there is an alarm active
            digitalWrite(ALARM, HIGH);
            digitalWrite(OKAY, LOW);
            digitalWrite(WARNING, LOW);
            //Shows the status of the outputs
            Serial.print("cirs 200,270,20,RED");
            endLine();
            Serial.print("cirs 200,340,20,RED");
            endLine();
            Serial.print("cirs 200,410,20,0x3B44");
            endLine();
        }
    }

Digital Outputs Control Header
------------------------------

This section introduces the header file named `Outputs.hpp`. This header file contains function declarations and variable externs related to controlling digital outputs in the AERtronic Basic sketch.

**Header Overview:**

The header file includes the following significant components:

1. **Digital Output Pins:**

The header file declares extern constants to represent the pin numbers for the digital outputs used in the system:

- `OKAY`: Represents the pin number for the "OK" output.
- `WARNING`: Represents the pin number for the "WARNING" output.
- `ALARM`: Represents the pin number for the "ALARM" output.

2. **Global Variable Externs:**

The header file declares extern global variables:

- `statusDigital`: An integer variable that stores the current status of the system. The value can be 0 (OK), 1 (WARNING), or 2 (ALARM). The variable is used to determine which output should be active based on the system's status.

3. **Function Declarations:**

The header file declares the following function prototypes:

- `outputFunc()`: This function sets up the digital output pins by configuring them as outputs.
- `outputStatus()`: This function controls the state of the digital outputs based on the `statusDigital` value. It adjusts the state of the output pins to represent the system's status (OK, WARNING, or ALARM).

These function declarations and variable externs are essential for using the digital outputs control functionalities provided by the AERtronic Basic sketch. They allow for interaction with the outputs and facilitate the management of system status.

Refer to the subsequent sections for a comprehensive understanding of the implementations and usages of these function prototypes and variables within the sketch.

.. code-block:: cpp

    #include <Arduino.h>

    //Set the GPIO we are going to use as digital outputs
    //Set pin numbers:
    extern const int OKAY;
    extern const int WARNING;
    extern const int ALARM;
    //Variable to store the current status of the system
    extern int statusDigital;
    //Function declarations
    void outputFunc();
    void outputStatus();