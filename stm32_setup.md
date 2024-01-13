# STM32 Intro
### Before you get started...
- Make sure to go over the [Arduino Intro](https://github.com/umigv/embedded_onboarding/blob/main/arduino_intro.md), as many concepts from the Arduino can be applied to the STM32 microcontrollers.
- Also make sure that you are familiar with some [foundational coding concepts](https://github.com/umigv/embedded_onboarding/blob/main/cs_intro.md).
## Getting Started!
1. The IDE we will be using is [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html), so be sure to download that.
	- Make sure to download the correct version according to your operating system.
	- You may have to create a MyST account to download the IDE.
2. Launch it!

## Setting up projects
1. To create a new project, you can either hit the blue button that says, "Start new STM32 project" or go to `File -> New -> STM32 Project`. A window should've popped up to create our project.
2. Now, we need to select which board we will be programming on. Go to **Board Selector**, find `NUCLEO-F446ZE`, and select it.
	- Tip: You can also "favorite" the board so you don't have to search for it the next time you create a project
3. Give your project a name! You can manually select a location to save the project to.
	- Leave the **Options** as is (C, Executable, STM32Cube)
4. Click **Finish**, as well as clicking **Yes** to initializing peripherals with their default mode, as well as opening the default perspective.

## Configuring projects
- You should be greeted with a GUI showing something representing a computer chip. You can always find it at `<PROJECT_NAME>.ioc` in your project files.
- This GUI allows us to configure what we want certain pins on the microcontroller to do.
	- Of course, some pins can only be used for specific tasks. You can find info about that, as well as pin locations on this [pinout diagram](https://os.mbed.com/platforms/ST-Nucleo-F446ZE/).
- For these starter projects, the main pin function we will be using is `GPIO_OUTPUT`. You may also find timers useful when making the LED fade.
- Select the pin you're going to use and then select `GPIO_OUTPUT`.
	- Also keep in mind its location, which can be found on this [pinout diagram](https://os.mbed.com/platforms/ST-Nucleo-F446ZE/)
- Near the top, there should be a cogwheel-like icon that says **Device Configuration Tool Code Generation** 
	- Every time you change the microcontroller configuration in the `ioc` file, you **MUST** regenerate code, or else the changes won't go through.
	- You may also need to login to your MyST account through the IDE.

## Programming the STM32 Nucleo
- Navigate to `Core -> Src -> main.c`, and then find the `main()` function.
- You will find many instances of these lines:
```
/* USER CODE BEGIN 1 */
/* USER CODE END 1 */`
```
- Make sure any code you type goes **in-between** these lines. This will make sure it doesn't get overwritten when regenerating code.
-  You will also notice a `while(1)` loop inside `main()`, meaning this loop will run infinitely. You can treat everything in `main()` that happens before the loop like `setup()` in Arduino! Initialization code that will run only once can go here. Additionally, the loop (unsurprisingly) can be treated like `loop()`. Code that will run indefinitely can go here.
- Now, you are ready to start programming the Nucleo. Try to replicate the two LED projects you did with the Arduino on the Nucleo!

## Additional resources you may find useful
- [Datasheet](https://www.st.com/en/microcontrollers-microprocessors/stm32f446ze.html)
	- This goes into more detail about the inner workings and features that the Nucleo has. 
- [Outputting to an LED](https://deepbluembedded.com/stm32-gpio-write-pin-digital-output-lab/) (You can skip to the "**The Application Code In CubeIDE**" section)
	- Contains useful functions for turning an LED on and off.
- [Replicating PWM with the Nucleo](https://deepbluembedded.com/stm32-pwm-example-timer-pwm-mode-tutorial/)
	- This also contains an explanation of how PWM works in microcontrollers!
