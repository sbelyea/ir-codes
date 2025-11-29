# IR Remote Control Codes

A collection of captured infrared (IR) remote control codes for home automation projects. All codes are captured using ESP32 devices with ESPHome firmware and provided in Pronto hex format.

## Supported Devices

- **Denon RC-1244** - Audio receiver remote (power, inputs, volume, sound modes)
- **Eufy Robot Vacuum** - Auto mode and home commands 
- **Sony RMF-TX520U** - Bravia TV remote (power, channels, apps, navigation)

## Usage

Each device folder contains:
- Complete button mappings with IR codes
- ESPHome configuration examples
- Integration instructions for home automation

Compatible with ESPHome, Home Assistant, and other IR transmitter projects.

## Code Format

All codes use Pronto hex format as captured from ESPHome logs:
```
0000 006D 000D 0000 005D 0016 002F 0016 0018...
```

Use tools like [Sensus IR Converter](https://pasthev.github.io/sensus/) to convert for your platform.

## Contributing

To add new devices:
1. Create manufacturer folder (lowercase)
2. Follow existing markdown format
3. Include ESPHome capture configuration
4. Document all button functions