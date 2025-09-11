# STM32F4 
TO FAMILIARIZE WITH STM32

-> The **STM32F411VE** is a microcontroller from the STM32 family by STMicroelectronics, based on the ARM Cortex-M4 core. 
<br>-> The **STM32F411VE Discovery Kit** is a development board that allows you to explore and evaluate the capabilities of the STM32F411VE microcontroller.

### Key Features of STM32F411VE:

- **Core**: ARM Cortex-M4 (with Floating Point Unit)
- **Flash Memory**: 512KB
- **RAM**: 128KB
- **Clock Speed**: Up to 100 MHz
- **I/O Pins**: 50 GPIO pins
- **Communication Interfaces**:
  - 2x I2C
  - 3x SPI
  - 3x USART
  - 1x USB 2.0 Full-Speed device
  - 1x CAN
- **Timers**: 7 timers, including advanced control timers
- **Analog Features**: 
  - 12-bit DAC
  - 12-bit ADC (up to 3 channels)
- **Power Supply**: 3.3V (with external 5V input)
- **Debugging**: SWD (Serial Wire Debug)

### Key Features of the Discovery Board:

- **On-board ST-LINK/V2 debugger**: For programming and debugging.
- **LCD Display**: Some versions have an LCD (e.g., 240x320 TFT) to display information and interact with the microcontroller.
- **Audio/Voice**: Some kits include a microphone or audio-related peripherals.
- **Expansion Connectors**: For attaching additional modules or sensors.
- **LEDs and Buttons**: Usually includes multiple LEDs for output and push buttons for input testing.

### Development Environment:

You can program the STM32F411VE Discovery board using popular IDEs like:

- **STM32CubeIDE**: A free, integrated development environment that combines code editing, compilation, debugging, and flashing.
- **Keil MDK**: A professional IDE for ARM-based applications.
- **IAR Embedded Workbench**: Another popular IDE for STM32 development.

### Applications:
- Robotics
- IoT devices
- Automotive applications
- Industrial control systems
- Audio processing

## UART CONFIGURATION
TWO METHODS:
- PROGRAMMING USING REGISTERS
- NORMMAL PROGRAMMING

## DSP
* EXPORT PROECT FILE
* CREATED NEW FILE
* ADD UART.h & signal.h to Inc , ADD UART.c & signal.c to Src
* Properties->C/C++ Build - Settings -> MCU/MPU GCC Linker - Libraries -> add library & its path from CMSIS-LIB-GCC 
* Properties->C/C++ General - Path and symbols -> ADD ARM_MATH_CM4 & _FPU_PRESENT
* Properties->C/C++ Build - Settings -> MCU/MPU Settings -> enable (tick mark) float with printf & scanf but still error shows then command the printf prgm and call the user defined fn:
* To debug : Run->Debud Configuration->Debugger - Serial Wire Viewer(SWV) -> 2 tick marks & max. SWO clock(kH?z) -2000
* Window -> show view -> SWV -> SWV Data Trace Timeline Graph -> start trace -> configuration - add variable name -> resume :: graph shows
* 
