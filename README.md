# Ultrasonic Distance Sensor — Arduino UNO R4 WiFi

Simple Arduino project that measures distance using an HC-SR04 ultrasonic sensor and prints results to the Serial Monitor.

## Files
- `src/main.cpp` — Arduino sketch that triggers the sensor and prints distance.
- `platformio.ini` — PlatformIO project configuration for `Arduino UNO R4 WiFi`.

## Hardware
Required components:
- `Arduino UNO R4 WiFi`
- HC-SR04 ultrasonic sensor
- Jumper wires
- Breadboard (optional)
- USB cable for programming/serial

## Wiring
- HC-SR04 VCC → `5V`
- HC-SR04 GND → `GND`
- HC-SR04 TRIG → Arduino digital pin `9`
- HC-SR04 ECHO → Arduino digital pin `10`

(Adjust pins in `src/main.cpp` if you change wiring.)

## PlatformIO / Build
1. Ensure PlatformIO is installed in your editor (VS Code, CLion with PlatformIO plugin, or use PlatformIO CLI).
2. Example minimal `platformio.ini` settings (place in project root):

    ; Use the appropriate board ID for UNO R4 WiFi if different
    [env:arduino_uno_r4_wifi]
    platform = atmelsam
    board = arduino_uno_r4_wifi
    framework = arduino
    monitor_speed = 9600

3. From PlatformIO: Build and Upload to the board.
4. Open the Serial Monitor at `9600` baud.

## Usage
- After upload, open Serial Monitor at `9600` baud.
- The sketch prints the measured distance (in centimeters) approximately once per second.

Example output:
Distance
123
 cm

## Notes
- The sketch uses `pulseIn`, which is blocking; measurement interval is approximately the `delay` value in the loop.
- Typical HC-SR04 range: ~2 cm to 400 cm; accuracy drops near limits.
- Avoid angled or soft surfaces that poorly reflect ultrasound.
- For `Arduino UNO R4 WiFi`, ensure the correct board ID is used in `platformio.ini`.

## License
MIT — adapt and reuse freely.
