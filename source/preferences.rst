Preferences
===========

Preferences Management and Information Display
----------------------------------------------

This code file serves as an interface for managing preferences, recording maintenance data, and displaying system information on a device using the Preferences library. It features functions to initialize preferences, track operation hours, and provide memory status information.

Header Dependencies
-------------------

Preferences.h: Header file of the Preferences library, providing support for saving key-value pairs in flash memory.

Functions.hpp: Custom header containing function prototypes and necessary dependencies.

Functions
bootCounter(object, object2, object3)

Initializes preferences instances and manages data related to system counters and maintenance records. This function handles the incrementation of a reboot counter, maintains maintenance-related variables, and retrieves information about the number of system events. It facilitates organized data storage in flash memory and supports proper system operation tracking.

`printInterval1()`
~~~~~~~~~~~~~~~~~~
This function sends maintenance interval information to an output source, likely a display. It communicates the number of operation hours and lubrication hours of the machine's motor, as well as operation hours thresholds before specific milestones (4000h and 8000h). The data is presented in a user-friendly format, aiding users in tracking maintenance schedules.

`printMemory()`
~~~~~~~~~~~~~~~~
Offering insight into memory usage, this function communicates various memory-related metrics over a serial connection. The metrics include the amount of free heap memory, flash chip size, sketch size, and the number of free entries in different preference namespaces (preferences, register1, and events). The function contributes to system monitoring and optimization efforts.

Global Variables
----------------

- `preferences`: An instance of the Preferences library used for storing and retrieving key-value pairs.

- `register1`: Another instance of the Preferences library intended for managing maintenance-related data.

- `events`: An instance of the Preferences library designed for handling system event data.

- `mhours`: An integer variable storing the number of operation hours.

- `mmotor`: An integer variable storing the number of operation hours of the motor.

- `lmotor`: An integer variable storing the number of lubrication hours of the motor.

- `m4hours`: An integer variable storing the number of operation hours before 4000 hours.

- `m8hours`: An integer variable storing the number of operation hours before 8000 hours.

- `numberOfMaintenance`: An integer variable holding the count of maintenance records.

- `contador`: An integer variable used to keep track of the number of system events.

Function Dependencies
---------------------

- `Functions.hpp`: Custom header containing necessary function prototypes and dependencies.

.. code-block:: cpp

    #include <Preferences.h>
    #include "Functions.hpp"

    //Initiate an instance of Preference library
    Preferences preferences;
    Preferences register1;
    Preferences events;
    int mhours;
    int mmotor;
    int lmotor;
    int m4hours;
    int m8hours;

    int numberOfMaintenance;
    //Counter to store the number of system events
    int contador;

    void bootCounter(Preferences object, Preferences object2, Preferences object3) {
        //Creates a storage space in flash memory called "counter", false = read/write mode
        object.begin("counter", false);
        //Get the value of the counter key saved on preferences. If it doesn’t find any value, it returns 0 by default
        int counter = object.getInt("counter", 0);
        //Adds one every time the ESP32 is rebooted
        counter++;
        //Store the new value on the “counter” key:
        object.putInt("counter", counter);
        //Close the preferences
        object.end();

        //Space in memory to store the maintenance registers:
        object2.begin("maintenance", false);
        //Key to store the number of operation hours
        mhours = object2.getInt("reg1", 0);
        //Key to store the number of the operatino hours of the motor
        mmotor = object2.getInt("reg2", 0);
        //Key to store the number of lubrication hours of the motor
        lmotor = object2.getInt("reg3", 0);
        //Key to save the number of operation hours before 4000h
        m4hours = object2.getInt("reg4", 0);
        //Key to store the number of operation hours before 8000h
        m8hours = object2.getInt("reg5", 0);
        //
        numberOfMaintenance = object2.getInt("numOfMt", 0);

        //Space in memory to store the total of system events
        object3.begin("eventos", false);
        contador = object3.getInt("contador", 0);
    }

    /**
     * @brief Sends the maintenance intervals:
    */
    void printInterval1() {
        //Sends the number of operation hours of the machine:
        Serial.print("Intervalos.tman1.txt=\"" + String(mhours) + " h" + "\"");
        endLine();
        //Sends the number of operation hours of the motor:
        Serial.print("Intervalos.tman2.txt=\"" + String(mmotor) + " h" + "\"");
        endLine();
        //Sends the number of lubrication hours of the motor
        Serial.print("Intervalos.tman3.txt=\"" + String(lmotor) + " h" + "\"");
        endLine();
        //Sends the number of operatino hours before 4000h
        Serial.print("Intervalos.tman4.txt=\"" + String(m4hours) + " h" + "\"");
        endLine();
        //Sends the number of operatino hours before 8000h
        Serial.print("Intervalos.tman5.txt=\"" + String(m8hours) + " h" + "\"");
        endLine();
    }

    /**
     * @brief Sends the state of the memory over serial
    */
    void printMemory() {
        Serial.print("Memoria.tmem1.txt=\"" + String(ESP.getFreeHeap()) + "\"");
        endLine();
        //
        Serial.print("Memoria.tmem2.txt=\"" + String(ESP.getFlashChipSize()) + "\"");
        endLine();
        //
        Serial.print("Memoria.tmem3.txt=\"" + String(ESP.getSketchSize()) + "\"");
        endLine();
        //
        size_t free_entries_preferences = preferences.freeEntries();
        Serial.print("Memoria.tmem4.txt=\"" + String(free_entries_preferences) + "\"");
        endLine();
        //
        size_t free_entries_register1 = register1.freeEntries();
        Serial.print("Memoria.tmem5.txt=\"" + String(free_entries_register1) + "\"");
        endLine();
        //
        size_t free_entries_events = events.freeEntries();
        Serial.print("Memoria.tmem6.txt=\"" + String(free_entries_events) + "\"");
        endLine();
        //
        Serial.print("Memoria.n0.val=usize");
        endLine();
    }

Header File Description: Preferences Management and System Information Display
------------------------------------------------------------------------------

This header file serves as an interface for managing preferences, recording maintenance data, and displaying system information on a device utilizing the ESP32 preferences library. It includes declarations for global variables, as well as function prototypes related to managing preferences and providing system information.

Header Dependencies
-------------------

- `Arduino.h`: The header file that includes standard definitions for the Arduino framework.

- `Preferences.h`: Header file of the ESP32 preferences library, which provides functionality for storing and retrieving data in flash memory.

- `esp_heap_caps.h`: Header file that provides access to heap memory capabilities in the ESP32.

- `EEPROM.h`: Header file for the EEPROM library, which allows reading and writing data to non-volatile memory on the microcontroller.

Global Variables and Extern Declarations
----------------------------------------

- `preferences`: An instance of the ESP32 preferences library used for storing and retrieving key-value pairs in flash memory.

- `register1`: Another instance of the ESP32 preferences library intended for managing maintenance-related data.

- `events`: An instance of the ESP32 preferences library designed for handling system event data.

- `mhours`: An integer variable storing the number of operation hours.

- `mmotor`: An integer variable storing the number of operation hours of the motor.

- `lmotor`: An integer variable storing the number of lubrication hours of the motor.

- `m4hours`: An integer variable storing the number of operation hours before 4000 hours.

- `m8hours`: An integer variable storing the number of operation hours before 8000 hours.

- `contador`: An integer variable used to keep track of the number of system events.

- `numberOfMaintenance`: An integer variable holding the count of maintenance records.

Function Declarations
----------------------

- `bootCounter(Preferences object, Preferences object2, Preferences object3)`: Initializes preferences instances and manages data related to system counters and maintenance records. This function handles the incrementation of a reboot counter, maintains maintenance-related variables, and retrieves information about the number of system events. It facilitates organized data storage in flash memory and supports proper system operation tracking.

- `printInterval1()`: Sends maintenance interval information to an output source, likely a display. It communicates the number of operation hours and lubrication hours of the machine's motor, as well as operation hours thresholds before specific milestones (4000h and 8000h). The data is presented in a user-friendly format, aiding users in tracking maintenance schedules.

- `printMemory()`: Offers insight into memory usage, communicating various memory-related metrics over a serial connection. The metrics include the amount of free heap memory, flash chip size, sketch size, and the number of free entries in different preference namespaces (preferences, register1, and events). This function contributes to system monitoring and optimization efforts.

.. code-block:: cpp

    #include <Arduino.h>
    //Including ESP32 preferences library to store data on flash memory
    #include <Preferences.h>
    #include <esp_heap_caps.h>
    #include <EEPROM.h>
    
    //Initiate an instance of Preference library
    extern Preferences preferences;
    extern Preferences register1;
    extern Preferences events;
    extern int mhours;
    extern int mmotor;
    extern int lmotor;
    extern int m4hours;
    extern int m8hours;
    extern int contador;
    extern int numberOfMaintenance;
    
    //Function declarations:
    void bootCounter(Preferences object, Preferences object2, Preferences object3);
    //int maintenanceRegister(Preferences obj);
    void printInterval1();
    void printMemory();