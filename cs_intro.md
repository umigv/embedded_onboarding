# Basics in C/C++
C and C++ are very powerful programming languages. They are especially popular among embedded developers because it allows us to get fine control over memory usage while maintaining high speed. Open up VScode, `File > New File > .cpp` and then make a new file called `HelloWorld.cpp`. Copy/paste the following code.

## Hello World
```c++
#include <iostream>

int main() {
    std::cout << "Hello World!";
    return 0;
}
```


This code creates a function called main. It then uses the std(stands for: standard) function cout(stands for: character output) to print out the string "Hello World".  
  
To run this code go to the top menu bar. `Terminal > New Terminal`. A new terminal window should open from the bottom of the screen. In the terminal type `g++ HelloWorld.cpp -o haha.exe` This line compiles the file `HelloWorld.cpp` and makes it into an executable file called `haha.exe`. The convention is to make the file name and exe name the same, but this shows that it doesn't have to be the same. To run the code, type `./haha.exe` into the terminal. You should see Hello World pop up in the terminal.

Good job, you made your first C++ program

## Variables and Data Types 
A variable is a name given to a memory location, which you can use to store information. C++ is a strongly typed language, which means you have to specify the data type of a variable, this [article](https://www.tutorialspoint.com/cplusplus/cpp_data_types.htm) gives a list of the primitive types in C++. The most often used ones include bool(boolean: true or false), int (integer), and double(double precision decimal number). Notably, string is not in this list because it is a data type from the standard library(std).

Try storing your faviorate number into a double variable and print it out.

## More Advanced Coding
Try using these resource to learn more!
[if statement](https://www.programiz.com/cpp-programming/if-else)
[while loop](https://www.w3schools.com/cpp/cpp_while_loop.asp)
[for loop](https://www.w3schools.com/cpp/cpp_for_loop.asp)
[array](https://www.w3schools.com/cpp/cpp_arrays.asp)
[functions](https://www.w3schools.com/cpp/cpp_functions.asp)



