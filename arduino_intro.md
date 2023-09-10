# Arduino Intro

## Get started
- Install [Arduio IDE 2.x](https://www.arduino.cc/en/software) if you haven't already  
- Make sure you are familiar with basic concepts of coding such as if statements, loops, etc... Checkout this tutorial if you are not  

## Setup
1. Plug in the Arduino to your computer.
2. In Arduino IDE top menu bar `Tools > Board > Arduino AVR Boards > ` select the Arduino board you are connected to. Most likely it is going to be a `Arduino Nano` for the onboarding project
3. Top menue bar again `Tools > Port > ` select the port you are connected to the board. Check with your computer system information/device management to confirm.

## Basics
### Default functions
Upon opening the IDE, you will see two functions prepopulated. `void setup` and `void loop`  

The `setup` function is going to run **once** when the board is powered up, this is useful for setup sensors (you will have a chance to use them later), hence the name.

The `loop` function will continue running as long as the board is powered, after the `setup` function.

### Pins and Breadboard basics
- The Arduino Nano have several pins(aka headers) on each of it's long sides, the pins labeled with the corresponding pin names.
- The breadboard is a way to connect electronics easily, if you are not familiar with it, check out this [tutorial](https://www.youtube.com/watch?v=fq6U5Y14oM4&ab_channel=SimplyElectronics)

## First Project: Simple Light Blink
- Important takeaways:
    1. Get comfortable using Arduino
    2. Get comfortbale with breadboard and circuits
    3. Have some fun!  
- Follow this [tutorial](https://www.arduino.cc/en/Tutorial/BuiltInExamples/Blink)
- You can put your Arduino nano on the breadboard, **make sure the pins are on the different side** of the breadboard middle valley
- But there is a twist, the light is RGB! Use google, and your brain to figure things out~

## Second Project: Ultrasound Distance Detection
- Important takeaways:
    1. Get comfortable with software, hardware interaction 
    2. learn to install libraries
- Follow this [tutorial](https://lastminuteengineers.com/arduino-sr04-ultrasonic-sensor-tutorial/)
- LCD screen part is optional

## Third Project: Advanced Lighting RGB Unleashed
- Important takeaways:
    1. Learn about PWM signals and arduinos. [Tutorial](https://docs.arduino.cc/learn/microcontrollers/analog-output)
    2. Independent Development skills
- Specs:
    1. Create a Arduino script that uses `analogWrite()` function to dim the RGB LED
    2. The LED dim/brighten according to the following behavior
        - Start from off state
        - Increase brightness to pure red color in 1 second
        - Decrease brightness to red to 0 while increasing brightness of blue to full in 1 second
        - Decrease brightness to blue to 0 while increasing brightness of green to full in 1 second
        - Decrease brightness to green to 0 in 1 second
