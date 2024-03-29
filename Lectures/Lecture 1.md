***
# Systems Programming
# Professor David Menendez
# Lecture 1: C Introduction and Review
***
## Programming with C
- First two weeks will be a review of C
- Memory Management
- Interfaces with the operating system
- Reference Compiler is GCC 9.3 - installed on the iLab

## Working with Unix-style operating systems
- Linux or Posix
- File System
- Multitasking and process control
- Multithreading
	- pthread interface (from Posix)
- Network Communication
	- Sockets

## Project-Oriented Class
- Three or Four programming assignments
	- Groups of Two
		- Anyone from any section of systems

## Sample C Program
```C
#include <stdio.h>
#include <stdlib.h>

/* 
 * int argc - Number of input arguments
 * char **argv - Array of input arguments
 */
int main(int argc, char **argv)
{
	printf("Hello, world!\n");

	return EXIT_SUCCESS; // Equivalent to returning 0
}
```
- Compile by using:
	- `gcc -Wall hello.c -o hello`
		- `-Wall` returns all warnings
		- `-o hello` means outputs will be written to a file called hello
	- `./hello` runs the c file

## Why C?
- C is a relatively simple programming language
	- Gives great visibility into the lower-level aspects of the computer
	- Designed to run and compile on low-powered hardware
- C vs. Java
	- Similar Syntax and Orientation
	- They differ by libraries
	- Java is an interpreted language
		- `javac` takes the java source code and turns it into "bytecode"
		- `java` then takes that bytecode and executes it
	- C is a compiled language
		- `GCC` translates the source code and converts it to machine code
			- machine code is binary instructions that CPUs can read
- Compile Time vs. Run Time
	- Compile Time is the translation process
		- Most errors occur during compile-time (e.g. syntax, types)
	- Run Time is when the program is actually executing
		- Examples include: bad arguments to function, division by zero, not being able to open a file, etc.

```C
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char **argv)
{
	printf("Argc is %d\n", argc);
	printf("Our special number is %d\n", 1 / argc); // argc starts at 1

	return EXIT_SUCCESS;
}
```

## Stages of Compilation
- Preprocessing 
	- Translates source code to other source code
- Compilation 
	- Translates source code to machine code
- Linking 
	- Combines my machine code with code from the standard library

## GCC commands
- `gcc myprogram.c`
	- Compiles and links program and creates executable `a.out`
- `gcc myprogram.c -o myprogram`
	- Compiles and links program and creates executable `myprogram`
- `gcc -c myprogram.c`
	- Compiles program and created "object file" `myprogram.o`
- `gcc myprogram.o mylibrary.o mydatastructure.o -o prog`
	- Links specified object files and creates executable `prog`

## Types
- C has a small set of built-in types
	- integers
		- signed or unsigned
		- regular, short, or long
