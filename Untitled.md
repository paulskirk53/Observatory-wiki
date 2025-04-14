
```


void setup() {
   Serial.begin(9600);

   // Read the existing EEPROM value
   uint16_t stored_value = eeprom_read_word(&my_eeprom_value);
   Serial.print("Stored Value: ");
   Serial.println(stored_value);

   // Write a new value
   uint16_t new_value = stored_value + 1;  // Increment stored value
   eeprom_update_word(&my_eeprom_value, new_value);

   Serial.print("New Value Written: ");
   Serial.println(new_value);
}

void loop() {
   // Empty loop
}

```


```
#define x y
```