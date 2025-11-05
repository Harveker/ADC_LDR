# ADC_LDR - Light Sensor Project

This is an STM32F4 microcontroller project that reads analog values from a Light Dependent Resistor (LDR) using an ADC (Analog-to-Digital Converter).

## Hardware

- **Microcontroller**: STM32F411CEUx
- **Package**: UFQFPN48
- **Sensor**: LDR (Light Dependent Resistor) connected to ADC1 Channel 0 (PA0)

## Features

- ADC reading from LDR sensor
- Timer (TIM4) integration
- GPIO outputs for LED control or other peripherals
- HAL library-based implementation

## Project Structure

```
ADC_LDR/
├── Core/
│   ├── Inc/           # Header files
│   └── Src/           # Source files
├── Drivers/
│   ├── CMSIS/         # CMSIS library
│   └── STM32F4xx_HAL_Driver/  # HAL drivers
├── .vscode/           # VSCode configuration
├── ADC_LDR.ioc        # STM32CubeMX project file
├── Makefile           # Build configuration
└── STM32F411XX_FLASH.ld  # Linker script
```

## Building the Project

### Prerequisites

- ARM GCC toolchain (`arm-none-eabi-gcc`)
- Make utility
- ST-Link tools (for flashing)

### Build Commands

```bash
# Build the project
make

# Clean build artifacts
make clean
```

### VSCode Integration

This project includes VSCode tasks:
- **Build**: `Ctrl+Shift+B` (default build task)
- **Clean**: Run "clean" task from task menu
- **Chip Erase**: Run "chip erase" task (requires ST-Link)

## Flashing

Use ST-Link tools to flash the built binary to the microcontroller:

```bash
st-flash write build/ADC_LDR.bin 0x8000000
```

## ADC Configuration

- **ADC Channel**: ADC1_IN0 (PA0-WKUP)
- **Clock Prescaler**: PCLK/4
- **Sampling Time**: 3 cycles
- **ADC Range**: 
  - Minimum (dark): ~199 (0.16V)
  - Maximum (light): ~3894 (3.14V)

## Security

Please review [SECURITY.md](SECURITY.md) for information about protecting personal information in this repository.

## License

This project uses STMicroelectronics HAL libraries which are licensed under their own terms. See the LICENSE files in the `Drivers` directory for details.

## Contributing

When contributing to this project:
1. Follow the existing code style
2. Test your changes on hardware when possible
3. Review [SECURITY.md](SECURITY.md) before committing
4. Ensure no personal information is included in commits
