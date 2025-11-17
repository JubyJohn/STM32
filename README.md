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


##ADC
Welcome back.

In this lesson, we shall give an overview of what an ADC or an analog to digital converter is.

Analog to digital converters are among the most widely used devices for data acquisition.

Digital computers use binary or discrete values, but in the physical world, everything is analog or

continuous temperature, pressure, humidity, velocity, are just a few examples of physical quantities

that we deal with every day.

A physical quantity is converted to electrical signals using a device called transducer, and the transducer

simply converts a physical quantity to either voltage or current .Transducers.

use to generate electrical output are referred to us sensors, sensors for temperatures, velocity,

pressure, light and many other natural physical quantities produce an output that is voltage or sometimes

current.

Therefore, we need an analog to digital converter to translate the analog signals to digital numbers

so that the microcontroller can read and process these numbers.

Now let's talk about the concept of ADC resolution. An ADC has in bits resolution where and can be

eight, 10, 12, 16 or even 24.

So we hear so you hear of people saying this ADC is 10 bit is 12, is 16 bit. Higher resolution ADC

provide a smaller step size where step size is the smallest change that can be detected by an ADC.

This table over here shows the number of steps as well as the step size, given the number of bits the

ADC has.

So for instance, 8-bit ADC bits would have two hundred and fifty six steps.

And how do we know this?

We simply do two to the power eight and we get 256.

And to compute the step size we've got to take the reference voltage into account.

So assuming the reference voltage is 5V, which we simply do five divided by 256 and this gives us

19 and this gives us 19.53mV. A 10-bits ADC has a 1024

step size and the smallest change this 10 bit ADC can detect is 4.88mV,

in the same way at twelve bits

ADC has four thousand and ninety six number of steps and a smallest change this ADC can detect is a

change in 1.2mV.

A sixteen bits ADC would have sixty five thousand five hundred and thirty six steps and the smallest

change this ADC will be able to detect will be 0.076mV.

Vref is an input voltage use for the reference voltage, the voltage connected to this pin

most microcontrollers have the Vref and we can connect our own input voltage to or we can just use

the same voltage as the one used by the MCU.

So the voltage connected to the Vref, along with the resolution of the ADC chip, determine the

step size, as you can see over here.

So assuming our Vref is 5V and the resolution of the ADC is eight bit, then we end up with

19.53mV step size.

Right.

So that's all there is for the short overview on ADCs and we shall see how the work programmatically.

I'll see you in the next lesson.
