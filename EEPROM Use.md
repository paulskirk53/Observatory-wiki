In some of the microcontollers, eeprom is used to persist values and provide a facility for changing values at runtime - e.g. it could be useful to be able to change the speed at which the dome rotates.

The library used is avr/eeprom.h and the use of the keyword EEMEM is very useful for abstracted memory management - you don't have to use pointers to values.

Also to avoid unecessary writes to eeprom, there is the eeprom_update function

Example
# Declare a value in EEPROM
```

#include <avr/eeprom.h>

// Declare a variable in EEPROM
uint16_t EEMEM my_eeprom_value;

```
- The `my_eeprom_value` variable is now stored in EEPROM.
    
- You can access it using EEPROM functions like `eeprom_read_word` and `eeprom_update_word`

# **Functions for Reading and Writing EEPROM**

#### **Reading EEPROM (**`eeprom_read_word`**)**

Reads a `uint16_t` value stored in a specified EEPROM location.

Example:

```

#include <avr/eeprom.h>

void setup() {
    Serial.begin(9600);

    // Read the value from EEPROM
    uint16_t value = eeprom_read_word(&my_eeprom_value);
    Serial.println(value);
}

void loop() {
    // Empty loop
}

```