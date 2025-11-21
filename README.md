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

I'll see you in the next lesson.'




Hello, welcome back.

In this lesson, we are going to look at ADC independent modes.

The reason we have this title, ADC Independent Mode's, is because there are other modes that are not

listed here.

The five modes listed here are known as independent modes.

There is another category of modes known as the dual mode mode or the dual mode, I should say.

And that involves having two ADC modules.

As you know, or as you may know, the the STM32F4 microcontroller has a single ADC module.

Other STM32 versions such as the STM32F7 has two ADC modules.

The two modules allows us to have the dual mode configurations, but over here because we have a single

ADC module, we are only we are a we are only able to use the ADC independent modes.

And I should also point out that although we have a single ADC module, it doesn't mean we have a single

channel.

Module is different from channels, our single ADC module allows us to have 16 channels, meaning we

can connect 16 sensors to our microcontroller and sample them.

Right.

And we should talk more about that.

So let's take a look at these modes.

We have five modes listed here.

The first one is the single channel, single conversion mode.

The second one is the multi-channel single conversion mode.

The third one, as we can see over here, is the single channel continuous conversion mode.

Following that, we have the multi-channel continuous conversion mode and finally we have the injected

continuous conversion mode.

Now let's examine each of them one by one.

So the single channel, single conversion mode is the simplest ADC mode.

In this mode, the ADC performs a single conversion of a single channel and then stops after it is complete,

as you can see the flow diagram here, we first start and then we convert our single channel.

And then once we've once we've converted that once we've sampled the sensor or whatever analog value

it is, we stop.

And an example use case here is the measurement of a voltage level to determine if a system should be

started or not.

So imagine you have a system where the voltage has to cross a particular threshold before you start

it or not, and you just need to check it out once.

In that case, you use this single channel single conversion mode.

Let's see the next one.

The next one is the multi-channel single conversion mode, this mode is used to convert multiple channels

successively and like I mentioned earlier, up to 16 different channels with different with different

sampling times can be converted on the STM32F4.

And the reason we see different sampling time here is because the microcontroller allows us to configure

the sampling time such that you can say convert channel one at a sampling time of three processor cycles

and convert channel five, for instance, to sampling time of four hundred and eighty cycles.

So we have the we have the flexibility to select sampling time and sometimes setting certain transducers

require longer sampling time for you to accurately get a get a data you want.

That is why we are given the flexibility to be able to configure our sampling time.

And in multi-channel single conversion mode, we can have multiple channels sampled successively and

in our multiple channels, each of them can have their own sampling time as well.

And a use case here is the measurement of multiple sensors to determine whether a system should start

or not.

And that's what we show in this flow diagram.

Here we start and then we sample Channel X all the way to the last channel channel end and then we stop.

So it's single conversion once with sample all, and so we stop, right, let's see the next one.

The next one is the single channel continuous conversion mode.

And as the flow diagram here depicts, we convert a single channel continuously.

As you can see, once we are done converting it, we go back and convert it again.

And this works in the background without the intervention of the CPU.

And an excellent example of this is the measurement of the room temperature to continuously adjust the

air conditioner.

In the room, right, so the based on the temperature of the room, the air conditioner which cools

the room will be adjusted appropriately.

And in such a use case, you would want to use simple what you you would want to use single channel,

continuous conversion mode.

Next, we have the multichannel continuous conversion mode, and this one is used to convert multiple

channels continuously, up to 16 different channels with different sampling times can be converted on

our system, STM32F4 board.

And as you can see, it's just like the multi-channel single conversion mode.

The only difference is that this time it's continuous, once you've converted all the channels, you

start from the beginning again on and on a use case.

Here is the continuous measurement of multiple accelerometers to adjust the robotic arm.

Imagine you have a robotic arm that has like five joints and you want to always know the position of

each joint before you adjust it.

And you want to be doing that rapidly, you want to be doing that like every second at 1Hz

rate, which is every second, then in such a case you would want to use multi-channel continuous conversion

mode.

And the final one, this one is known as the injected conversion mode.

This is intended for use when conversion is triggered by an external event or by software.

The injected group has priority over the regular channel group.

So what we are seeing here is that you could configure a set of channels to be regular group using let's say

multiple conversion mode, and then you would configure another specialized channel as injected conversion

mode.

And that is not part of our regular group.

And the injected the injected convention mode channel has priority over the other types of mood.

So if we have other channels configured in a single conversion mode or multiple conversion mode.

The injected conversion mode channel would have priority over those, so if there's ever a case where

the process or has to decide which one to deal with first, the injector conversion mode will be dealt

with.

So interrupt the injection.

The injector conversion mode interrupts the conversion of the current channel in the regular channel

group.

Right.

And this diagram here depicts such a case.

So a use case for this is for synchronizing the conversion of channels to an event, so if you want

the ADC channel to happen to happen

at a particular synchronized time, if you can synchronize it to an event such as time, right.

So if you wanted to happen at an exact time, you would want to use injected conversion mode if you

wanted to happen after a particular event, which is also different from time, you may want to use

the injector conversion mode.

But I often don't see people use this mode as often as the others.

Right.

But it's good to know about this as well.

####TIMERS
| Timer   | Bus  | Max Timer Clock | Counter Width |
| ------- | ---- | --------------- | ------------- |
| TIM1    | APB2 | 100 MHz         | 16-bit        |
| TIM2    | APB1 | 50 MHz          | 32-bit        |
| TIM3    | APB1 | 50 MHz          | 16-bit        |
| TIM4    | APB1 | 50 MHz          | 16-bit        |
| TIM5    | APB1 | 50 MHz          | 32-bit        |
| TIM6    | APB1 | 50 MHz          | 16-bit        |
| TIM7    | APB1 | 50 MHz          | 16-bit        |
| SysTick | CPU  | 100 MHz         | 24-bit        |


