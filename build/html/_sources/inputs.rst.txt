Inputs
======

Digital Inputs and Status Checking Functions
--------------------------------------------

This section introduces a source file named `Inputs.cpp`. This source file contains functions related to handling digital input pins and checking their statuses in the AERtronic Basic sketch.

**Code Overview:**

The `Inputs.cpp` source file includes the following significant components:

1. **Include Statements:**

The source file includes necessary header files, such as `"Inputs.hpp"`, `"Outputs.hpp"`, `"Functions.hpp"`, and `<Arduino.h>`, to access relevant functions and libraries.

2. **Global Constants:**

Constant values are assigned to represent the pin numbers for digital inputs. These constants are used to identify the pins connected to specific digital inputs, such as "START" and "STOP."

3. **Global Variables:**

Global variables are declared to store the status of digital inputs, including "start_status" and "stop_status." These variables keep track of whether the digital inputs are in a HIGH (active) or LOW (inactive) state.

4. **Function Definitions:**

The source file defines the following functions:

- `inputsFunc()`: Initializes the digital input pins by configuring their pinMode.
- `readInputs()`: Reads and checks the status of the digital inputs, updating graphical display elements based on the inputs' statuses. It uses the "start_status" and "stop_status" variables to determine whether the inputs are HIGH or LOW.

These function definitions provide an overview of the digital input handling and status checking functionalities implemented in the `Inputs.cpp` source file.

This section offers a high-level overview of the functions, variables, and constants defined within the `Inputs.cpp` source file. For more detailed explanations and the complete code implementation, refer to the subsequent sections.

.. code-block:: cpp

    #include "Inputs.hpp"
    #include "Outputs.hpp"
    #include "Functions.hpp"
    #include <Arduino.h>

    //Set the GPIO we are going to use as digital inputs
    //Set pin numbers:
    const int START = 33;
    const int STOP = 25;
    //Variables for storing the inputs status
    int start_status = 0;
    int stop_status = 0;

    /**
    * @brief Function to set the digital inputs to be included in the main file.
    * @return void
    */
    void inputsFunc() {
        //Digital input start:
        pinMode(START, INPUT);
        //Digital input stop:
        pinMode(STOP, INPUT);
    }

    /**
     * @Function to check the status of the digital inputs.
     * @return void
    */
    void readInputs() {
        //Updates the status of the inputs: TEST(Evaluate to delete)
        /*start_status = digitalRead(START);
        stop_status = digitalRead(STOP);*/
    
        //Code to test the digital inputs
        if(start_status == HIGH) {
            //digitalWrite(OKAY, HIGH);
            Serial.print("cirs 200,130,20,0x3B44");
            endLine();
        } else {
            //digitalWrite(OKAY, LOW);
            Serial.print("cirs 200,130,20,RED");
            endLine();
        }
    
        if(stop_status == HIGH) {
            //digitalWrite(WARNING, HIGH);
            Serial.print("cirs 200,200,20,0x3B44");
            endLine();
        } else {
            //digitalWrite(WARNING, LOW);
            Serial.print("cirs 200,200,20,RED");
            endLine();
        }
    }


Digital Inputs and Status Checking Header
-----------------------------------------

This section introduces a header file named `Inputs.hpp`. This header file defines global constants, variables, and function declarations related to handling digital input pins and checking their statuses in the AERtronic Basic sketch.

**Code Overview:**

The `Inputs.hpp` header file includes the following significant components:

1. **Include Statement:**

The header file includes the `<Arduino.h>` library, which provides essential functions and definitions for working with the Arduino platform.

2. **Global Constants:**

Constant values are declared using the `extern` keyword to represent the pin numbers for digital inputs, such as "START" and "STOP." These constants are used to identify the pins connected to specific digital inputs.

3. **Global Variables:**

Global variables are declared using the `extern` keyword to store the status of digital inputs. These variables include "start_status" and "stop_status," which track whether the digital inputs are in a HIGH (active) or LOW (inactive) state.

4. **Function Declarations:**

Function prototypes are defined for functions that are implemented in the corresponding `Inputs.cpp` source file:

- `inputsFunc()`: Initializes the digital input pins by configuring their pinMode.
- `readInputs()`: Reads and checks the status of the digital inputs, updating graphical display elements based on the inputs' statuses. It uses the "start_status" and "stop_status" variables to determine whether the inputs are HIGH or LOW.

These function declarations provide a clear overview of the functions and variables that are used for digital input handling and status checking.

This section offers a concise summary of the constants, variables, and functions defined within the `Inputs.hpp` header file. For more detailed explanations and the complete code implementation, refer to the subsequent sections.

.. code-block:: cpp

    #include <Arduino.h>
    
    //Set the GPIO we are going to use as digital inputs
    //Set pin numbers:
    extern const int START;
    extern const int STOP;
    //Variables for storing the inputs status
    extern int start_status;
    extern int stop_status;
    //Function declarations
    void inputsFunc();
    void readInputs();
    