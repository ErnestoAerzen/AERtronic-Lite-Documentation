Functions
==========================================

Functions Program Logic
-----------------------

This section introduces the code contained within the `.cpp` file named `Functions.cpp`. The functions defined in this file handle the reading of analog sensor values, sending and receiving data over serial communication with the Nextion display, and updating the color and values of graphical elements on different display pages.

**Code Overview:**

The `Functions.cpp` file includes the following significant components:

1. **Global Variables:**

Global constants and variables are declared to store GPIO pin numbers and potentiometer values. The `endChar` variable stores the characters used to indicate the end of a serial command.

2. **Function Definitions:**

The file contains the definitions of several functions, including:

- `endLine()`: Appends special characters to indicate the end of a serial print.
- `serialRead()`: Listens for and processes serial data from the Nextion display.
- `changeSlideColor(String slide, int value, String page)`: Changes the color of a graphical element based on a value.
- `analogValue()`: Reads the analog values from potentiometers and performs calculations.
- `printAnalogValuesHome()`, `printAnalogValuesPressure()`, and `printAnalogValuesTemp()`: Send analog values to the Nextion display and update graphical elements.
- `printErrorWarningTimeDate(String value, String time, String date)`: Updates the time and date associated with error and warning messages on a specific page.

These functions collectively handle data processing, transmission, and display updates for the AERtronic Basic sketch.

This section offers an overview of the analog data handling and display-related functions present within the `Functions.cpp` file. For detailed explanations and code implementations of each function's role, proceed to the subsequent sections.

.. code-block:: cpp

    #include <Arduino.h>
    #include "Functions.hpp"
    #include "Functionality.hpp"

    //Global variables:
    //Constant int(connot be changed during execution) to save the GPIO 34(Analog ADC1_CH6) to connect the potentiometer:
    const int POTPIN = 34;
    const int POTPIN2 = 35;
    const int POTPIN3 = 32;
    //Global variables for storing the potentiometer values:
    int potValue = 0;
    int potValue2 = 0;
    int potValue3 = 0;
    int potValue4 = 0;
    //String that needs to be sent everytime with a command over serial
    String endChar = String(char(0xff)) + String(char(0xff)) + String(char(0xff));

    //Function definitions:

    /**
     * @brief This function needs to be called every time after serial print 
     */
    void endLine() {
        Serial.write(0xff);
        Serial.write(0xff);
        Serial.write(0xff);
    }

    /**
    * @brief function to listen serial data from Nextion display
    */
    void serialRead() {
        //String to save what it has been sent from the display:
        String data_nextion;
        int code = 0;
        int page = 0;
        //Conditional to receive a print from the Nextion dsiplay:
        if(Serial.available()) {
            while(Serial.available()) {
                //Updates the variable to store what it´s been sent:
                data_nextion += char(Serial.read());
                if(data_nextion.endsWith(endChar)) {
                    code = data_nextion[0];
                    page = data_nextion[1];
                    //Executes the function according to what the variable receives:
                    sendData(page);
                    data_nextion = "";
                }
            }
        }
    }

    /**
     * @brief Function that changes the color of the Home slidebars:
     * 
     * @return void
     */
    void changeSlideColor(String slide, int value, String page) {
        Serial.print(page + "." + slide + ".val=" + String(value));
        endLine();
        //Change the color of the slide bar(h0) depending of the value that has been read:
        if(value > 4000) {
            Serial.print(page + "." + slide + ".bco1=RED");
            endLine();
        } else if(value>=3500 && value<=4000) {
            Serial.print(page + "." + slide + ".bco1=YELLOW");
            endLine();
        } else if(value < 3500) {
            Serial.print(page + "." + slide + ".bco1=1024");
            endLine();
        }
    }


    /**
     * @brief Function to reads the analog value from the potentiometer:
     * 
     * @return void
     */
    double* analogValue() {
        //Array to store the read values
        static double voltage_array[3];
        //Reading potentiometer value 1:
        potValue = analogRead(POTPIN);
        voltage_array[0] = (2.5 / 3016 ) * (potValue - 1079);
        if(voltage_array[0] < 0) {
            voltage_array[0] = 0;
        }
        //Reading potentiometer value 2:
        potValue2 = analogRead(POTPIN2);
        voltage_array[1] = (6.0/2991) * (potValue2 - 1104);
        if(voltage_array[1] < 0) {
            voltage_array[1] = 0;
        }
        //Reading potentiometer value 3:
        potValue3 = analogRead(POTPIN3);
        voltage_array[2] = ((130.0 / 1107.0) * (potValue3 - 272)) + 35;
        if(voltage_array[2] < 0) {
            voltage_array[2] = 0;
        }

        return voltage_array;
    }

    void printAnalogValuesHome() {
        //Saves the retun value of analogValue
        double* sensorValues = analogValue();
        //Sends out the read value to the Nextion display, updates x0 & h0 in the Home page:
        Serial.print("Home.value1.txt=\"" + String(sensorValues[0]) + "\"");
        endLine();
        //Sends out the read value to the Nextion display, updates x2 & h2 in the Home page:
        Serial.print("Home.value3.txt=\"" + String(sensorValues[1]) + "\"");
        endLine();
        //Sends out the read value to the Nextion display, updates x1 & h1 in the Home page:
        Serial.print("Home.value2.txt=\"" + String(sensorValues[2]) + "\"");
        endLine();
        /*Serial.print("Home.value3.txt=\"" + String(voltage_value) + "\"");
        endLine();*/

        //changes the color of the sliders
        if(potValue < 1079) {
            potValue = 0;
        }

        if(potValue2 < 1104) {
            potValue2 = 0;
        }

        if(potValue3 < 272) {
            potValue3 = 0;
        }
        changeSlideColor("h0", potValue, "Home");
        changeSlideColor("h1", potValue2, "Home");
        changeSlideColor("h2", potValue3, "Home");
    }

    void printAnalogValuesPressure() {
        //Saves the retun value of analogValue
        double* sensorValues = analogValue();
        //Sends out the read value to the Nextion display, updates x0 & h0 in the Home page:
        Serial.print("Presion.value1.txt=\"" + String(sensorValues[0]) + "\"");
        endLine();
        //Sends out the read value to the Nextion display, updates x2 & h2 in the Home page:
        Serial.print("Presion.value3.txt=\"" + String(sensorValues[1]) + "\"");
        endLine();

        if(potValue < 1079) {
            potValue = 0;
        }

        if(potValue3 < 272) {
            potValue3 = 0;
        }
        //changes the color of the sliders
        changeSlideColor("h0", potValue, "Presion");
        changeSlideColor("h1", potValue3, "Presion");
    }

    void printAnalogValuesTemp() {
        //Saves the retun value of analogValue
        double* sensorValues = analogValue();
        //Sends out the read value to the Nextion display, updates x1 & h1 in the Home page:
        Serial.print("Temperatura.value2.txt=\"" + String(sensorValues[2]) + "\"");
        endLine();

        if(potValue2 < 1104) {
            potValue2 = 0;
        }

        //changes the color of the sliders
        changeSlideColor("h2", potValue2, "Temperatura");
    }

    void printErrorWarningTimeDate(String value, String time, String date){ 
        //Sends the time and date saved of an error in h1 to page 24:
        Serial.print("Mensajes.time" + value + ".txt=\"" + time + "\"");
        endLine();
        Serial.print("Mensajes.date" + value + ".txt=\"" + date + "\"");
        endLine();
    }

Analog Data Handling and Display Functions Header
-------------------------------------------------

This section introduces the header file named `Functions.hpp`. This header file declares global variables and function prototypes used in handling analog sensor data, serial communication, and graphical display updates in the AERtronic Basic sketch.

**Code Overview:**

The `Functions.hpp` header file includes the following significant components:

1. **Global Variables:**

Global variables are declared to store the values read from potentiometers. These variables are used to store analog sensor readings for subsequent processing and display updates.

2. **Function Declarations:**

The file declares the following function prototypes:

- `endLine()`: Appends special characters to indicate the end of a serial print.
- `serialRead()`: Listens for and processes serial data from the Nextion display.
- `analogValue()`: Reads analog values from potentiometers and performs calculations.
- `changeSlideColor(String slide, int value, String page)`: Changes the color of a graphical element based on a value.
- `printErrorWarningTimeDate(String value, String time, String date)`: Updates the time and date associated with error and warning messages on a specific page.
- `printAnalogValuesHome()`, `printAnalogValuesPressure()`, and `printAnalogValuesTemp()`: Functions to send analog values to the Nextion display and update graphical elements.

These function declarations provide a clear overview of the functionalities present in the `Functions.hpp` header file.

This section offers an overview of the functions and variables declared within the `Functions.hpp` header file. For more detailed explanations and the complete code implementation, refer to the subsequent sections.

.. code-block:: cpp

    #include <Arduino.h>

    //Global variables for storing the potentiometer values:
    extern int potValue;
    extern int potValue2;
    extern int potValue3;
    
    //Functions declarations:
    void endLine();
    void serialRead();
    double* analogValue();
    void changeSlideColor(String slide, int value, String page);
    void printErrorWarningTimeDate(String value, String time, String date);
    void printAnalogValuesHome();
    void printAnalogValuesPressure();
    void printAnalogValuesTemp();