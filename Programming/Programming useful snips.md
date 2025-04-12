In the **dome driver** write / read profile/ can use this to print values to console - brill
//  Console.WriteLine($"Parkplace value: {Parkplace}");   // pk -  a test for profile empty error

Code from AI for use with a resistor voltage divider:

// Pin Definitions
const int analogPin = A0;

// Voltage Divider Scaling Factor
const float R1 = 10000.0;  // Resistor 1 value (in ohms)
const float R2 = 3300.0;   // Resistor 2 value (in ohms)
const float scalingFactor = (R1 + R2) / R2;

void setup() {
  Serial.begin(9600);  // Initialize serial communication
}

void loop() {
  int rawADC = analogRead(analogPin);  // Read the analog pin
  float voltageAtPin = rawADC * 5.0 / 1023.0;  // Convert ADC value to voltage (0–5V)
  float batteryVoltage = voltageAtPin * scalingFactor;  // Scale up to battery voltage

  Serial.print("Battery Voltage: ");
  Serial.print(batteryVoltage);
  Serial.println(" V");

  delay(1000);  // Wait 1 second before the next reading
}


to protect the pin use a 5.1 V zenerPlace the **cathode** (striped end) to the Arduino analog pin.
to check for anode / cathode with a DVM:
- **Set the DVM to Diode Test Mode**:
    
    - Most DVMs have a specific **diode test mode** or resistance mode that applies a small voltage across the diode to measure conductivity.
        
- **Connect the Test Leads**:
    
    - Place the **red lead** on one end of the diode and the **black lead** on the other.
        
- **Observe the Reading**:
    
    - **Forward Bias**:
        
        - If the diode conducts (shows a low resistance or a small voltage drop, typically 0.7V for regular diodes and higher for Zeners), the end connected to the red lead is the **anode**, and the end connected to the black lead is the **cathode**.
            
    - **Reverse Bias**:
        
        - If the diode does not conduct (shows infinite resistance or no voltage drop), the connections are reversed.
            
[[Observatory Home]]

