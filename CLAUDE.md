# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains captured infrared (IR) remote control codes for various consumer electronics devices. The codes are captured using ESP32 devices running ESPHome firmware and are primarily stored in Pronto hex format. The repository serves as a reference library for home automation projects that need to replicate remote control functionality.

## Repository Structure

The repository is organized by device manufacturer:

- `denon/` - IR codes for Denon audio receivers (model RC-1244)
- `eufy/` - IR codes for Eufy robot vacuums 
- `sony/` - IR codes for Sony Bravia TVs (model RMF-TX520U)

Each directory contains markdown files documenting:
- Specific device model information
- ESPHome configuration used for capture
- Raw IR data in Pronto hex format organized by button/function
- Code examples for ESPHome integration

## IR Code Format

All IR codes in this repository are captured as Pronto hex format from ESPHome logs. The format includes:
- Carrier frequency (typically 38kHz)
- Raw timing data for IR pulses
- Multiple repetitions per button press (usually 2-4 times for reliability)

Example structure:
```
### Key: 'Power'
[timestamp][I][remote.pronto:237]: 0000 006D 000D 0000 005D 0016 002F...
```

## ESPHome Integration

The captured codes are designed for integration with ESPHome remote transmitter components. Each device file includes:

1. **Capture Configuration** - ESPHome YAML for IR receiver setup
2. **Transmit Configuration** - Button templates for remote transmission
3. **Code Conversion** - Examples using tools like Sensus IR converter

## Working with IR Codes

### Adding New Devices
1. Create new directory using manufacturer name (lowercase)
2. Use descriptive filename with model number: `model-name.md`
3. Follow existing format with sections for:
   - Device description
   - ESPHome capture config
   - Raw IR data per button
   - Transmission examples

### Code Format Standards
- Use Pronto hex format as captured from ESPHome logs
- Include multiple repetitions when captured
- Document carrier frequency (usually 38kHz)
- Organize buttons logically (power, numbers, navigation, etc.)

### ESPHome Configuration
Standard capture setup uses:
- GPIO15 for IR receiver
- `dump: all` for complete protocol capture
- Manual IP configuration for reliable logging

## Common Tasks

### Viewing IR Codes
Read markdown files directly - no build process required. Files contain human-readable documentation with embedded code examples.

### Converting Codes for Use
Use tools like the Sensus IR converter (https://pasthev.github.io/sensus/) to convert Pronto hex to ESPHome YAML format for transmission.

### Testing IR Codes
Integration testing requires physical ESP32 hardware with IR transmitter connected. No software-only testing available.

## Repository Maintenance

This is a documentation-only repository with no build system, linting, or automated testing. Changes involve:

1. Adding new device documentation
2. Updating existing IR code collections
3. Improving ESPHome configuration examples

Files are version controlled through Git, with focus on preserving captured IR data and improving documentation clarity.