
# VLSI Physical Design for ASICs




## Objective
The objective of VLSI (Very Large Scale Integration) physical design for ASICs (Application-Specific Integrated Circuits) is to transform a digital circuit's logical representation into a physical layout that meets various performance, power, area, and manufacturability requirements.
## Installation
Referring: https://github.com/kunalg123/riscv_workshop_collaterals/blob/master/run.sh

To install the RISC-V toolchain on Ubuntu, follow these steps:
1. Install Prerequisites:
Before you can build the RISC-V toolchain, you'll need to install some software dependencies:

```bash
sudo apt update
sudo apt install autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev git
```
2. Clone the RISC-V GNU Toolchain Repository:
```bash
git clone --recursive https://github.com/riscv/riscv-gnu-toolchain
```
3. Build and Install the Toolchain:
Navigate into the toolchain directory and initiate the build:
```bash
cd riscv-gnu-toolchain
./configure --prefix=/opt/riscv
make
```
4. Update Your Path:
After installing, you'll want to add the toolchain binaries to your PATH:
```bash
echo 'export PATH=$PATH:/opt/riscv/bin' >> ~/.bashrc
source ~/.bashrc
```
5. Test the Installation:
Check the version of the GCC compiler:
```bash
riscv64-unknown-elf-gcc --version
```


## Skills Acquired
->Architectural Design

->RTL Design / Behavioral Modeling

->Floorplanning

->Placement

->Clock Tree Synthesis

->Routing
## Table of Contents

## DAY 1
Introduction to RISCV ISA and GNU Compiler Toolchain
* Introduction to Basic Keywords
    * [Introduction](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction "Introduction")
    * [Application software to Hardware](https://github.com/aishwarya-2511/PES-ASIC-CLASS#application-software-to-hardware "Application software to Hardware")
    * [Description of Course Content](https://github.com/aishwarya-2511/PES-ASIC-CLASS#description-of-course-content "Description of Course Content")
* Labwork for RISCV Toolchain
    * [C Program](https://github.com/aishwarya-2511/PES-ASIC-CLASS#c-program "C Program")
    * [RISCV GCC Compiler and Disassemble](https://github.com/aishwarya-2511/PES-ASIC-CLASS#riscv-gcc-compiler-and-disassemble "RISCV GCC Compiler and Disassemble")
    * [Spike Simulation and Debugging](https://github.com/aishwarya-2511/PES-ASIC-CLASS#spike-simulation-and-debugging "Spike Simulation and Debugging")
* Integer Number Representation
    * [Unsigned numbers](https://github.com/aishwarya-2511/PES-ASIC-CLASS#unsigned-numbers "Unsigned numbers")
    * [Signed numbers](https://github.com/aishwarya-2511/PES-ASIC-CLASS#signed-numbers "Signed numbers")
    * [Labwork For Signed and Unsigned Numbers](https://github.com/aishwarya-2511/PES-ASIC-CLASS#labwork "Labwork For Signed and Unsigned Numbers")



## DAY 2
Introduction to ABI and Basic Verification Flow
* Application Binary Interface
    * [Introduction to ABI](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-abi "Introduction to ABI")
    * [Memory Allocation for Double Words](https://github.com/aishwarya-2511/PES-ASIC-CLASS#memory-allocation-for-double-words "Memory Allocation for Double Words")
    * [Load, Add and Store Instructions](https://github.com/aishwarya-2511/PES-ASIC-CLASS#load-add-and-store-instructions "Load, Add and Store Instructions")
    * [32-Registers and their ABI Names](https://github.com/aishwarya-2511/PES-ASIC-CLASS#32-registers-and-their-abi-names "32-Registers and their ABI Names")
* Labwork using ABI Function Calls
    * [Algorithm for C Program using ASM](https://github.com/aishwarya-2511/PES-ASIC-CLASS#algorithm-for-c-program-using-asm "Algorithm for C Program using ASM")
    * [Review ASM Function Calls](https://github.com/aishwarya-2511/PES-ASIC-CLASS#review-asm-function-calls "Review ASM Function Calls")
    * [Simulate C Program using Function Call](https://github.com/aishwarya-2511/PES-ASIC-CLASS#stimulate-c-program-using-function-call "Simulate C Program using Function Call")


## DAY 3
* Introduction to Open-Source Simulator iVerilog
    * [Introduction to iVerilog Design Testbench](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-iverilog-design-testbench "Introduction to iVerilog Design Testbench")

* Labs using iVerilog and GTKwave
    * [Introduction to Lab](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-lab "Introduction to Lab")
    * [Introduction to iVerilog gtkwave part 1](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-iverilog-gtkwave-part-1 "Introduction to iVerilog gtkwave part 1")
    * [Introduction to iVerilog gtkwave part 2](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-iverilog-gtkwave-part-2 "Introduction to iVerilog gtkwave part 2")
* Introduction to Yosys and Logic Synthesis
    * [Introduction to Yosys](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-yosys "Introduction to Yosys")
    * [Introduction to Logic Synthesis](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-logic-sysnthesis "Introduction to Logic Synthesis")
* Labs using Yosys and Sky130 PDKs
    * [Yosys good mux](https://github.com/aishwarya-2511/PES-ASIC-CLASS#yosys-good-mux "Yosys good mux")


## DAY 4
* [Introduction to Timing dot libs](https://github.com/aishwarya-2511/PES-ASIC-CLASS#introduction-to-timing-dot-libs "Introduction to Timing dot libs")
* [Hierarchical vs Flat Synthesis](https://github.com/aishwarya-2511/PES-ASIC-CLASS#hierarchical-vs-flat-synthesis "Hierarchical vs Flat Synthesis")
* [Various Flop Coding Styles and Optimization](https://github.com/aishwarya-2511/PES-ASIC-CLASS#various-flop-coding-styles-and-optimization "Various Flop Coding Styles and Optimization")
    * why flops and Flop coding styles
    * lab flop synthesis simulations
    * interesting optimizations

    
## Introduction to basic keywords
### Introduction
* ISA (Instruction Set Archhitecture)
    * ISA defines the interface between a computer's hardware and its software, specifically how the processor and its components interact with the software instructions that drive the execution of tasks.

* RISC-V (Reduced Instruction Set Computing - Five)
    * It is an open-source Instruction Set Architecture (ISA) that has gained significant attention and adoption in the world of computer architecture and semiconductor design.

### Application software to Hardware
    1. Apps: A computer software that is designed to perform specific tasks or functions for end-users.

    2. System software: Refers to a category of computer software that acts as an intermediary between the hardware components of a computer system and the user-facing application software. 

    3. Operating System: The operating system is a fundamental piece of software that controls memory management, process scheduling, file system management, and user interface interaction.

    4. Compiler: A compiler is a type of software tool that translates high-level programming code written by developers into assembly-level language.

    5. Assembler: An assembler is a software tool that translates assembly language code into machine code or binary code that can be directly executed by a computer's processor.

    6. RTL: RTL serves as an abstraction level in the design process that represents the behavior of a digital circuit in terms of registers and the operations that transfer data between them.

    7. Hardware: Hardware refers to the physical components of a computer system or any electronic device. 

### Description of Course Content
*Pseudo Instructions* : Used to simplify programming, improve code readability, and reduce the number of explicit instructions a programmer needs to write. Ex: li, mv.

*Base Integer Instructions* : Refers to the fundamental set of instructions that form the foundation for performing basic arithmetic, logical, and data movement operations. Ex: add, sub, and, or, xor, sll.

*Multiply Extension Intructions* : Instructions that enhance the instruction set to perform efficient multiplication and multiplication-accumulate operations. Ex: mul, mulh, mulhu, mulhsu.

*Single and Double Precision Floating Point Extension* : The RISC-V architecture includes floating-point extensions that provide support for both single-precision (32-bit) and double-precision (64-bit) floating-point arithmetic operations. 

*Application Binary Interface* : Set of rules and conventions that govern how software components interact with each other at the binary level. The ABI defines various aspects of program execution, including how function calls are made, how parameters are passed and returned, how memory is allocated and managed, and more.

_Memory Allocation and Stack Pointer_

* Memory allocation refers to the process of assigning and managing memory segments for various data structures, variables, and objects used by a program. It involves allocating memory space from the system's memory pool and releasing it when it is no longer needed to prevent memory leaks.
* The stack pointer is a register used by a program to keep track of the current position of the program's execution on the call stack.
## Labwork for RISCV Toolchain
### C Program
A C program for calculating the sum from 1 to n using a text editor, leafpad.
```bash
leafpad sum1ton.c &
```
```C
#include<stdio.h>
int main()
{
	int i,sum=0,n=10;
	for(i=1;i<=n;++i) sum+=i;
	printf("Sum of numbers from 1 to %d is %d \n",n,sum);
	return 0;
}
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%2010.55.58%20AM.jpeg "Title is optional")

Using the gcc compiler, compile the program to get the output.
```bash
gcc sumton.c
.\a.out
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%205.40.35%20PM.jpeg "Title is optional")


### RISCV GCC Compiler and Disassemble
Using the riscv gcc compiler, compile the C program.

```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```

Using this command we can check that the object file is created.
```bash 
ls -ltr sum1ton.c 
```

To get the dissembled ALP code for the C program,
```bash
riscv64-unknown-elf-objdump -d sum1ton.o | less 
```
In order to view the main section, type 
```bash
/main.
```

Here, since we used -O1 optimisation, the number of instructions are 15.
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%206.47.53%20PM.jpeg "Title is optional")



When we use -Ofast optimisation, we can see that the number of instructions have been reduced to 12.
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%206.48.07%20PM.jpeg "Title is optional")


### Spike simulation and Debugging
To check whether the instructions produced are right to give the correct output.
```bash
spike pk sum1ton.o 
```
For debugging:
```bash
spike -d pk sum1ton.c 
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%205.39.32%20PM.jpeg "Title is optional")

* press ENTER : to show successive lines
* reg 0 a2 : to check content of register a2 0th core
* q : to quit the debug process
## Integer number representation
### Unsigned numbers
* Unsigned numbers, also known as non-negative numbers, are numerical values that represent magnitudes without indicating direction or sign.
* Range: [0, (2^n)-1 ]

### Signed Numbers
* Signed numbers are numerical values that can represent both positive and negative magnitudes, along with zero.
* Range : Positive : [0 , 2^(n-1)-1] Negative : [-1 to 2^(n-1)]

### Labwork
C program that shows the maximum and minimum values of 64bit unsigned numbers.
```C
#include <stdio.h>
#include <math.h>

int main(){
	unsigned long long int max = (unsigned long long int) (pow(2,64) -1);
	unsigned long long int min = (unsigned long long int) (pow(2,64) *(-1));
	printf("lowest number represented by unsigned 64-bit integer is %llu\n",min);
	printf("highest number represented by unsigned 64-bit integer is %llu\n",max);
	return 0;
}
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%206.45.59%20PM.jpeg "Title is optional")


C program that shows the maximum and minimum values of 64bit signed numbers.
```C
#include <stdio.h>
#include <math.h>

int main(){
	long long int max = (long long int) (pow(2,63) -1);
	long long int min = (long long int) (pow(2,63) *(-1));
	printf("lowest number represented by signed 64-bit integer is %lld\n",min);
	printf("highest number represented by signed 64-bit integer is %lld\n",max);
	return 0;
}
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%206.45.20%20PM.jpeg "Title is optional")


## Application Binary Interface
### Introduction to ABI
An Application Binary Interface (ABI) is a set of rules and conventions that dictate how binary code interacts with and communicates with other binary code, typically at the level of machine code or compiled code. In simpler terms, it defines the interface between two software components or systems that are written in different programming languages, compiled by different compilers, or running on different hardware architectures.

### Memory Allocation for Double Words
64-bit number (or any multi-byte value) can be loaded into memory in little-endian or big-endian. It involves understanding the byte order and arranging the bytes accordingly

* Little-Endian: In little-endian representation, you store the least significant byte (LSB) at the lowest memory address and the most significant byte (MSB) at the highest memory address.
* Big-Endian: In big-endian representation, you store the most significant byte (MSB) at the lowest memory address and the least significant byte (LSB) at the highest memory address.

### Load, Add and Store Instructions
Load, Add, and Store instructions are fundamental operations in computer architecture and assembly programming. They are often used to manipulate data within a computer's memory and registers.
1. Load:  to transfer data from memory to registers.
Example 
```bash
ld x6, 8(x5)
```
2. Store Instructions: Store instructions are used to write data from registers into memory.
Example 
```bash
sd x8, 8(x9)
```
3. Add Instructions: Add instructions are used to perform addition operations on registers. They add the values of two source registers and store the result in a destination register.
Example 
```bash
add x9, x10, x11
```

### 32-Registers and their ABI Names
The choice of the number of registers in a processor's architecture, such as the RISC-V RV64 architecture with its 32 general-purpose registers, involves a trade-off between various factors. While modern processors can have more registers but increasing the number of registers could lead to larger instructions, which would take up more memory and potentially slow down instruction fetch and decode.

#### ABI Names
ABI names for registers serve as a standardized way to designate the purpose and usage of specific registers within a software ecosystem. These names play a critical role in maintaining compatibility, optimizing code generation, and facilitating communication between different software components.
## Labwork using ABI Function Calls
### Algorithm for C Program using ASM
* Incorporating assembly language code into a C program can be done using inline assembly or by linking separate assembly files with your C code.
* When you call an assembly function from your C code, the C calling convention is followed, including pushing arguments onto the stack or passing them in registers as required.
* The program executes the assembly function, following the assembly instructions you've provided.

### Review ASM Function Calls
* We wrote C code in one file and your assembly code in a separate file.
* In the assembly file, we declared assembly functions with appropriate signatures that match the calling conventions of your platform.

C program: 
```bash
custom1to9.c
```

```C
#include <stdio.h>

extern int load(int x, int y);

int main()
{
  int result = 0;
  int count = 9;
  result = load(0x0, count+1);
  printf("Sum of numbers from 1 to 9 is %d\n", result);
}
```

Assembly File:
```bash
load.s
```
```C
.section .text
.global load
.type load, @function

load:

add a4, a0, zero
add a2, a0, a1
add a3, a0, zero

loop:

add a4, a3, a4
addi a3, a3, 1
blt a3, a2, loop
add a0, a4, zero
ret
```

### Simulate C Program using Function Call
Compilation: To compile C code and Asseembly file use the command
```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o custom1to9.o custom1to9.c load.s
```

this would generate object file custom1to9.o.

Execution: To execute the object file run the command
```bash
spike pk custom1to9.o
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/WhatsApp%20Image%202023-08-20%20at%206.43.23%20PM.jpeg "Title is optional")

## Introduction to Open-Source Simulator iVerilog
Simulator: RTL design is checked for adherence to the spec by simulating the design. (iverilog is used here)

Design: Design is the actual verilog code / set of verilog codes which has the intended functionality to meet with the required specification

Testbench: Testbench is the setup to apply stimulus to the design to check its functionality

Simulator looks for changes in input and accordingly changes the output.

Design of Testbench:
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20203815.png "Title is optional")

design + testbench -> to iverilog tool -> gives vcd file -> viewed using gtkwave
## Labs using iVerilog and GTKwave
### Introduction to Lab
* Make directory VSD
```bash
mkdir VSD
```
```bash
cd VSD
```
* Clone the repo
```bash
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```
It should look like this:
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20205852.png "Title is optional")

### Introduction to iVerilog gtkwave part 1
* Go to this directory:
```bash
cd VSD/sky130RTLDesignAndSynthesisWorkshop/verilog_files
```
* verilog file and testbench :
```bash
iverilog good_mux.v tb_good_mux.v
```
```bash
ls 
```
* a.out file will be created, type this command to create vcd file:
```bash
./a.out
```
* run this to open the file in gtkwave:
```bash
gtkwave tb_good_mux.vcd
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20215748.png "Title is optional")

### Introduction to iVerilog gtkwave part 2
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20215320.png "Title is optional")
* Code:
good_mux.v:
```C
module good_mux (input i0 , input i1 , input sel , output reg y);
always @ (*)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule
```

tb_good_mux.v:
```C
timescale 1ns / 1ps
module tb_good_mux;
	// Inputs
	reg i0,i1,sel;
	// Outputs
	wire y;

        // Instantiate the Unit Under Test (UUT)
	good_mux uut (
		.sel(sel),
		.i0(i0),
		.i1(i1),
		.y(y)
	);

	initial begin
	$dumpfile("tb_good_mux.vcd");
	$dumpvars(0,tb_good_mux);
	// Initialize Inputs
	sel = 0;
	i0 = 0;
	i1 = 0;
	#300 $finish;
	end

always #75 sel = ~sel;
always #10 i0 = ~i0;
always #55 i1 = ~i1;
endmodule
```
* To view file contents:
```bash
 vim tb_good_mux.v -o good_mux.v
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20220856.png "Title is optional")

## Introduction to Yosys and Logic Synthesis
### Introduction to Yosys
Synthesizer: Tool to convert RTL to netlist. Yosys is used here
Design + .lib file -> to synthezixer -> gives netlist
```bash
read_verilog
``` 
used to read the design file
```bash
read_liberty
``` 
to read the .lib file
```bash
write_verilog
```
to write out the netlist file

* To verify the synthesis, the netlist and testbench is given to iverilog which creates a vcd file which can be plotted in gtkwave.

### Introduction to Logic Synthesis
* RTL design: Behavioral representation of req. specification(verilog HDL)
* Synthesis: RTL to gate level synthesis. Netlist gives details of the conversion to gates and the connections between them
* .lib file: collections of modules, logic gates, of different flavours
* Faster and slower cells:
	* Combinational delay in logic path determines the max speed of operation of digital logic circuit
	* Hold time is the essential min time for input to be constant after the clock changes
	* hence we need fast and slow cells
* Selection of cells
	* Need to guide the synhesizer to select the flavour of cells that is optimum for the implementation of circuit
	* fast cells: power and area is compromised
	* slow cells: slugggish circuit, performance is compromised


## Labs using Yosys and Sky130 PDKs
* Go to directory:
```bash
cd verilog_files
```
* invoke yosys
```bash
yosys
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20224138.png "Title is optional")
* Read library:
```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
* Read design:
```bash
read_verilog good_mux.v
```
* Synthesize:
```bash
synth -top good_mux
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20224150.png "Title is optional")

* generate netlist:
```bash
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20224220.png "Title is optional")

![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20224228.png "Title is optional")


* To see logic realised:
```bash
show
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20224326.png "Title is optional")
* write netlist:
```bash
write_verilog good_mux_netlist.v
```
* open netlist:
```bash
!gvim good_mux_netlist.v
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-27%20225729.png "Title is optional")

```C
/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module good_mux(i0, i1, sel, y);
  wire _0_;
  wire _1_;
  wire _2_;
  wire _3_;
  input i0;
  wire i0;
  input i1;
  wire i1;
  input sel;
  wire sel;
  output y;
  wire y;
  sky130_fd_sc_hd__mux2_1 _4_ (
    .A0(_0_),
    .A1(_1_),
    .S(_2_),
    .X(_3_)
  );
  assign _0_ = i0;
  assign _1_ = i1;
  assign _2_ = sel;
  assign y = _3_;
endmodule
```


## Introduction to Timing dot libs
### sky130_fd_sc_hd__tt_025C_1v80.lib
PVT: Process, Voltage, Temperature
* Open the file:
```bash
!gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-28%20230939.png "Title is optional")

    * tt : indicates variations due to process and here it indicates Typical Process.
    * 025C : indicates the variations due to temperatures where the silicon will be used.
* It also displays the units of various parameters.
* To enable line number 
```bash
:se nu
```
* To view any instance 
```bash
:/instance
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-29%20072516.png "Title is optional")

![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-29%20072501.png "Title is optional")


* Compare area and power
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-29%20073003.png "Title is optional")

## Hierarchical vs Flat Synthesis
### Hierarchical
Divides the design into logical modules or blocks and synthesizes each module separately.

Steps:
Run the following in yosys:
```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog multiple_modules.v
synth -top multiple_modules
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show multiple_modules
write_verilog -noattr multiple_modules_hier.v
!gvim multiple_modules_hier.v
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-29%20075106.png "Title is optional")

multiple_modules_hier.v
```C
/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module multiple_modules(a, b, c, y);
  input a;
  wire a;
  input b;
  wire b;
  input c;
  wire c;
  wire net1;
  output y;
  wire y;
  sub_module1 u1 (
    .a(a),
    .b(b),
    .y(net1)
  );
  sub_module2 u2 (
    .a(net1),
    .b(c),
    .y(y)
  );
endmodule

module sub_module1(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  wire a;
  input b;
  wire b;
  output y;
  wire y;
  sky130_fd_sc_hd__and2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule

module sub_module2(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  wire a;
  input b;
  wire b;
  output y;
  wire y;
  sky130_fd_sc_hd__or2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule
```

### Flat Synthesis
The entire design is synthesized as a single, monolithic entity.

Steps:
Run the following in yosys:
```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog multiple_modules.v
synth -top multiple_modules
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
flatten
show
write_verilog -noattr multiple_modules_flat.v
!gvim multiple_modules_flat.v
```
![picture alt](https://github.com/aishwarya-2511/PES-ASIC-CLASS/blob/main/images/Screenshot%202023-08-29%20075327.png "Title is optional")

multiple_modules_flat.v
```C
/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module multiple_modules(a, b, c, y);
  wire _0_;
  wire _1_;
  wire _2_;
  wire _3_;
  wire _4_;
  wire _5_;
  input a;
  wire a;
  input b;
  wire b;
  input c;
  wire c;
  wire net1;
  wire \u1.a ;
  wire \u1.b ;
  wire \u1.y ;
  wire \u2.a ;
  wire \u2.b ;
  wire \u2.y ;
  output y;
  wire y;
  sky130_fd_sc_hd__and2_0 _6_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  sky130_fd_sc_hd__or2_0 _7_ (
    .A(_4_),
    .B(_3_),
    .X(_5_)
  );
  assign _4_ = \u2.b ;
  assign _3_ = \u2.a ;
  assign \u2.y  = _5_;
  assign \u2.a  = net1;
  assign \u2.b  = c;
  assign y = \u2.y ;
  assign _1_ = \u1.b ;
  assign _0_ = \u1.a ;
  assign \u1.y  = _2_;
  assign \u1.a  = a;
  assign \u1.b  = b;
  assign net1 = \u1.y ;
endmodule
```
