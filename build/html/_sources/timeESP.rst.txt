TimeESP
=======

Source Code Description: Time Management and Information Display
----------------------------------------------------------------

This source code file serves as an interface for managing time-related functions, receiving time and date data, and displaying them on a device. It interfaces with the ESP32Time library to provide real-time clock (RTC) capabilities. The code includes functions to receive time data from an external display, send current time and date to a display, manage operation time of the machine, and reset operation hours.

Source Code Dependencies
------------------------

- `timeESP.hpp`: Header file containing declarations related to time management.

- `Functions.hpp`: Custom header containing function prototypes and necessary dependencies.

- `preferences.hpp`: Header file containing declarations related to preferences management.

Global Variables
----------------

- `rtc`: An instance of the `ESP32Time` object, which provides access to RTC functions.

- `rtc_current`: An object to store the current time and date.

- `opseg`: An integer variable storing seconds of operation.

- `opmin`: An integer variable storing minutes of operation.

- `ophour`: An integer variable storing hours of operation.

Functions
---------

- `receiveTime()`: Waits for and receives time and date data from an external display (likely a Nextion display). It processes the received data, separates and parses it, and sets the initial time and date of the RTC.

- `currentTime(ESP32Time obj)`: Takes an `ESP32Time` object as input and sends the current time to a display (likely a Nextion display). The function returns a string with the current time, useful for error or warning messages.

- `currentDate(ESP32Time obj)`: Takes an `ESP32Time` object as input and sends the current date to a display (likely a Nextion display). The function returns a string with the current date, useful for error or warning messages.

- `opTime()`: Manages the operation time of the machine. It increments operation seconds, minutes, and hours. It also updates maintenance-related variables and stores them in preference namespaces.

- `resetOp()`: Resets the operation hours by resetting operation seconds, minutes, and hours. It displays a message indicating that the counter has been reset.

- `printopTime()`: Sends the machine's operation time to a display (likely a Nextion display). The time is presented in hours, minutes, and seconds format.

Function Dependencies
---------------------

- `timeESP.hpp`: Header file containing necessary declarations related to time management.

- `Functions.hpp`: Custom header containing necessary function prototypes and dependencies.

.. code-block:: cpp

    #include "timeESP.hpp"
    #include "Functions.hpp"
    #include "preferences.hpp"

    //ESP32Time object to utilize RTC functions:
    ESP32Time rtc;
    //Object to store the current time and date
    ESP32Time rtc_current; 
    //Variables to store seconds, minutes and hours of operation:
    int opseg = 0;
    int opmin = 0;
    int ophour = 0;

    /**
     * @brief Function to receive the time and date from the display
    */
    void receiveTime() {
        //Waits until receives data from Nextion display
        String timeNextion = "";
        while(timeNextion == "") {
            timeNextion = Serial.readString();
            delay(1000);
        }
        //Variables to store data from nextion
        String seconds = "";
        String minutes = "";
        String hour = "";
        String days = "";
        String month = "";
        String year = "";

        //Separates the string data
        for(int i = 1; i < timeNextion.length(); i++) {
            if(timeNextion[i] != ',') {
                if(seconds.length() < 2) {
                    seconds += timeNextion[i];
                } else if(minutes.length() < 2) {
                    minutes += timeNextion[i];
                } else if(hour.length() < 2) {
                    hour += timeNextion[i];
                } else if(days.length() < 2) {
                    days += timeNextion[i];
                } else if(month.length() < 2) {
                    month += timeNextion[i];
                } else if(year.length() < 4) {
                    year += timeNextion[i];
                }
            }
        }

        //Sets the initial time and date of the RTC, format(sec,min,hr,day,month,yr):
        rtc.setTime(atoi(seconds.c_str()), atoi(minutes.c_str()), atoi(hour.c_str()), atoi(days.c_str()), atoi(month.c_str()), atoi(year.c_str()));
        rtc_current = rtc;
    }

    /**
     * @brief Function to send the current time to Nextion Display
     * 
     * @return the string with the current time according to RTC 
     */
    String currentTime(ESP32Time obj) {
        int seconds = obj.getSecond();
        int minutes = obj.getMinute();
        String hour = obj.getAmPm(true);
        int hours = obj.getHour(true);
        //Prints the time to the Nextion display:
        Serial.print("t0.txt=\"" + String(hours) + ":" + String(minutes) + ":" + String(seconds) + "\"");
        endLine();
        //Updates every second:
        //delay(1000);
        //Stores and returns the current time useful when an error or warning occurs:
        String nowTime = String(hours) + ":" + String(minutes) + ":" + String(seconds);
        return nowTime;
    }

    /**
     * @brief Function to send the current date to the Nextion display:
     * 
     * @return the string with current date according to RTC
     */
    String currentDate(ESP32Time obj) {
        int day = obj.getDay();
        int month = obj.getMonth() + 1; //+1 bc returns a value between 0-11
        int year = obj.getYear();
        //Prints the date to the Nextion display over serial.
        Serial.print("t1.txt=\"" + String(day) + "/" + String(month) + "/" + String(year) + "\"");
        endLine();
        //Stores and returns the current date useful when an error or warning occurs:
        String nowDate = String(day) + "/" + String(month) + "/" + String(year);
        return nowDate;
    }

    /**
     * @brief Function to store the operation time of the machine
    */
    void opTime() {
        //Adds one every time the main loop runs:
        opseg++;

        if(opseg == 60) {
            //Adds 1 to minute every 60 seconds
            opmin++;
            //Resets seconds
            opseg = 0;
        }

        if(opmin == 60) {
            //Adds 1 to hour every 60 minutes:
            ophour++;
            //Adds 1 to the number of operation hours to every key-value
            mhours++;
            mmotor++;
            lmotor++;
            m4hours++;
            m8hours++;
            //Saves the number of operation hours in every key-value
            register1.begin("maintenance", false);
            register1.putInt("reg1", mhours);
            register1.putInt("reg2", mmotor);
            register1.putInt("reg3", lmotor);
            register1.putInt("reg4", m4hours);
            register1.putInt("reg5", m8hours);
            //resets minutes:
            opmin = 0;
        }
    }

    /**
     * @brief Resets the operation hours
    */
    void resetOp() {
        opseg = 0;
        opmin = 0;
        ophour = 0;
        Serial.print("xstr 320,380,250,35,6,RED,fondo,1,1,3,\"Contador reiniciado\"");
        endLine();
    }

    /**
     * @brief Sends the op time to the display
    */
    void printopTime() {
        Serial.print("Tiempos.topTime.txt=\"" + String(ophour) + "h " + String(opmin) + "min " + String(opseg) + "\"");
        endLine();
    }

Header Description: Time Management and Information Display
-----------------------------------------------------------

This header file provides the declarations and external references required for managing time-related functions, receiving time and date data, and displaying them on a device. It interfaces with the `ESP32Time` library to utilize the ESP32 real-time clock (RTC) capabilities. The header includes function declarations to send and receive time data, manage operation time of the machine, and reset operation hours.

Header Dependencies
-------------------

- `Arduino.h`: Standard header for Arduino platform.

- `ESP32Time.h`: Header file of the `ESP32Time` library, providing access to RTC functions.

Global Variables
----------------

- `rtc`: An external instance of the `ESP32Time` object, serving as the main RTC object for the system.

- `rtc_current`: An external object to store the current time and date.

- `opseg`: An external integer variable storing seconds of operation.

- `opmin`: An external integer variable storing minutes of operation.

- `ophour`: An external integer variable storing hours of operation.

Function Declarations
----------------------

- `String currentTime(ESP32Time obj)`: Takes an `ESP32Time` object as input and returns a string with the current time. This function is responsible for formatting the time data for display purposes.

- `String currentDate(ESP32Time obj)`: Takes an `ESP32Time` object as input and returns a string with the current date. Similar to the `currentTime` function, this function formats the date data for display.

- `void receiveTime()`: Receives time and date data from an external source (e.g., a Nextion display). This function processes and sets the initial time and date of the RTC based on the received data.

- `void opTime()`: Manages the operation time of the machine. It increments operation seconds, minutes, and hours and updates the related global variables accordingly.

- `void printopTime()`: Sends the machine's operation time to a display (likely a Nextion display). This function formats and presents the operation time in hours, minutes, and seconds.

- `void resetOp()`: Resets the operation hours of the machine. It sets the operation seconds, minutes, and hours to zero and can display a message indicating the reset.

Function Dependencies
----------------------

- `ESP32Time.h`: Header file of the `ESP32Time` library, required for accessing RTC functions and objects.

.. code-block:: cpp

    #include <Arduino.h>
    //Including the time library to use the ESP32 rtc and declare a ESP32Time object:
    #include <ESP32Time.h>
    //Main rtc object
    extern ESP32Time rtc;
    //Object to store the current time and date
    extern ESP32Time rtc_current;
    //Variables to store seconds, minutes and hours of operation:
    extern int opseg;
    extern int opmin;
    extern int ophour;
    
    //Functions declarations:
    String currentTime(ESP32Time obj);
    String currentDate(ESP32Time obj);
    void receiveTime();
    void opTime();
    void printopTime();
    void resetOp();