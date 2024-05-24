## Example Summary

Application that toggles an LED(s) using a GPIO pin interrupt.

## Peripherals & Pin Assignments

When this project is built, the SysConfig tool will generate the TI-Driver
configurations into the __ti_drivers_config.c__ and __ti_drivers_config.h__
files. Information on pins and resources used is present in both generated
files. Additionally, the System Configuration file (\*.syscfg) present in the
project may be opened with SysConfig's graphical user interface to determine
pins and resources used.

* `CONFIG_GPIO_LED_0` - Indicates that the board was initialized within
`mainThread()` also toggled by `CONFIG_GPIO_BUTTON_0`
* `CONFIG_GPIO_LED_1` - Toggled by `CONFIG_GPIO_BUTTON_1`
* `CONFIG_GPIO_BUTTON_0` - Toggles `CONFIG_GPIO_LED_0`
* `CONFIG_GPIO_BUTTON_1` - Toggles `CONFIG_GPIO_LED_1`

## BoosterPacks, Board Resources & Jumper Settings

For board specific jumper settings, resources and BoosterPack modifications,
refer to the __Board.html__ file.

> If you're using an IDE such as Code Composer Studio (CCS) or IAR, please
refer to Board.html in your project directory for resources used and
board-specific jumper settings.

The Board.html can also be found in your SDK installation:

        <SDK_INSTALL_DIR>/source/ti/boards/<BOARD>

## Example Usage

* Run the example. `CONFIG_GPIO_LED_0` turns ON to indicate driver
initialization is complete.

* `CONFIG_GPIO_LED_0` is toggled by pushing `CONFIG_GPIO_BUTTON_0`.
* `CONFIG_GPIO_LED_1` is toggled by pushing `CONFIG_GPIO_BUTTON_1`.

## Application Design Details

* The `gpioButtonFxn0`/`gpioButtonFxn1` functions are configured in the driver configuration
file. These functions are called in the context of the GPIO interrupt.

* Not all boards have more than one button, so `CONFIG_GPIO_LED_1` may not be
toggled.

* There is no button de-bounce logic in the example.

TI-RTOS:

* When building in Code Composer Studio, the configuration project will be
imported along with the example. These projects can be found under
\<SDK_INSTALL_DIR>\/kernel/tirtos/builds/\<BOARD\>/(release|debug)/(ccs|gcc).
The configuration project is referenced by the example, so it
will be built first. The "release" configuration has many debug features
disabled. These features include assert checking, logging and runtime stack
checks. For a detailed difference between the "release" and "debug"
configurations, please refer to the TI-RTOS Kernel User's Guide.

FreeRTOS:

* Please view the `FreeRTOSConfig.h` header file for example configuration
information.

# My Work

## Summarize the project and what problem it was solving.
The project involves creating a temperature control system using a microcontroller, with input and output capabilities managed through UART and I2C interfaces. The system periodically checks the button inputs to adjust the temperature set-point, reads the current temperature from a sensor, and updates an LED to indicate heating control. It then communicates  the system status to an external server (or monitor) via UART.<br>
The primary problem it solves is maintaining a desired temperature set-point within an environment
## What did you do particularly well?
I think I did very well in itegrating the the peripherals (UART, I2C, timers, and GPIO) into the project to create the functional temperature controlling system. I also did well following a modular approach by structuring the code into distinct functions to initialize the peripherals, handle button presses, read the temperatures, update the LEDs, and UART communication.
## Where could you improve?
I think I should incorporate more error handling code. It would make the system more reliable and fault tolerant.
## What tools and/or resources are you adding to your support network?
I would leverage the extensive documentation by TI, participate in forums and communities. It could provide some valuable insights and show me solutions to common problems. 
## What skills from this project will be particularly transferable to other projects and/or course work?
I think the task scheduling and timing mechanism aspects of the project is transferrable and valuable in any project that may require precise timing and responsiveness.
## How did you make this project maintainable, readable, and adaptable?
I would add more comments and documentation and describe the system's design, functionalities, and API references in a comprehensive manner. 
I would also enforce an adherence to coding standards. The code should follow consistent coding standards and best practices, including naming conventions and file organization

