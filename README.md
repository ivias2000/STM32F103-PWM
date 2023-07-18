# STM32F103-PWM
This C code appears to be a main program file targeting a microcontroller, likely an STM32 microcontroller, using Timer 1 (TIM1) with Pulse Width Modulation (PWM) to control an output signal. Let's go through the key components of the code:

Includes:![download](https://github.com/ivias2000/STM32F103-PWM/assets/125237611/c6201eac-42f6-4cc8-82e8-4b8111af3510)

The code includes various header files representing different libraries used in the project. These headers provide access to functions and constants required for the peripherals and libraries used in the application.

Global Variables:

count: A global variable initialized to 499 (probably the initial value for the PWM duty cycle).
Main Function:
The main function is the entry point of the program. It initializes the microcontroller's peripherals, specifically TIM1 in PWM mode, and enters an infinite loop.

System Clock Configuration:
The SystemClock_Config function configures the system clock for the microcontroller.

Infinite Loop:
Within the infinite loop, the code does the following:

Increments the count variable by 1 each time the loop executes.![Screenshot 2023-07-18 113315](https://github.com/ivias2000/STM32F103-PWM/assets/125237611/e23d7c42-d286-4a1a-8060-af8e09af2513)

Sets the PWM duty cycle by updating the CCR1 register of TIM1 with the current value of count. This means the PWM duty cycle will vary between 0 and 999 (inclusive) during the loop execution.
If count reaches 1000, it is reset to 0 to repeat the PWM cycle.
Delay:
After updating the PWM duty cycle, the code introduces a 5 ms delay using HAL_Delay. This will control the frequency of the PWM signal and the duration of each duty cycle.

Please note that the code is using HAL_Delay, which introduces blocking delays. Depending on your application, this may or may not be desirable. If precise timing is needed or other tasks must be performed concurrently, consider using hardware timers or an RTOS (Real-Time Operating System) for multitasking.

To use this code on GitHub, follow the steps mentioned earlier to create a new repository and upload this C code as the main program file. Additionally, you can include a README.md file in your repository to provide more information about the project and how to use the code.
