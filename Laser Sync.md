### Description
A laser and sensor are used to detect the sync position of the dome. Sync is used to improve accuracy of measuring dome rotation. There might be cumulative errors in measuring azimuth or slippage of the encoder wheel. Sync ensures that once per rotation  (or more if slews pass the sync point), the azimuth angle is synchronised to a known point - the angle used is due east 270 Degrees

### Devices
* Laser transmitter
- 650nm wavelength pinout S= signal. - = Gnd, middle pin 5V
- 

* Laser Sensor

- SFH 300 Phototransistor

diagram of sensor

       +5V
        |
        R (1kΩ - 10kΩ)
        |
        |-------> Output Signal to Arduino (analog input)
    (C) |
           SFH 300
        |---------|
       GND       (E)
Higher value R increases sensitivity but may introduce noise

I built the diagram below using circuit-diagram.org [link](https://www.circuit-diagram.org/editor/)

![[Laser Sensor.PNG]]

example code from copilot:
```
int sensorPin = A0; // Analog pin connected to phototransistor output
int sensorValue;

void setup() {
  Serial.begin(9600);
}

void loop() {
  sensorValue = analogRead(sensorPin);  // Read the phototransistor signal
  Serial.println(sensorValue);         // Print the value to monitor response
  delay(100);                          // Small delay for readability
}
```

[[Observatory Home]]
