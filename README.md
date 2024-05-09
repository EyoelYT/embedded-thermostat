## The Project
The project involves creating a temperature control system using a microcontroller, with input and output capabilities managed through UART and I2C interfaces. The system periodically checks the button inputs to adjust the temperature set-point, reads the current temperature from a sensor, and updates an LED to indicate heating control. It then communicates  the system status to an external server (or monitor) via UART.<br>
The primary problem it solves is maintaining a desired temperature set-point within an environment
## Aspects of Project
I think I did very well in itegrating the the peripherals (UART, I2C, timers, and GPIO) into the project to create the functional temperature controlling system. I also did well following a modular approach by structuring the code into distinct functions to initialize the peripherals, handle button presses, read the temperatures, update the LEDs, and UART communication.
I think I should incorporate more error handling code. It would make the system more reliable and fault tolerant.
## Tools and Resources used
I leveraged the extensive documentation by TI, including the forums and communities.
I think the task scheduling and timing mechanism aspects of the project is transferrable and valuable in any project that may require precise timing and responsiveness.

I would add more comments and documentation and describe the system's design, functionalities, and API references in a comprehensive manner. 
I would also enforce an adherence to coding standards. The code should follow consistent coding standards and best practices, including naming conventions and file organization

