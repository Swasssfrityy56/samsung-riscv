# Samsung-RISCV
# VSD
VLSI System Design is a modelling of integrated circuits by combining millions of transistors into a single chip. The main aim is to design a system with optimal cost, low power consumptin, high performance.

# RISC-v 
REDUCED INSTRUCTION SET COMPUTER
RISC-V is an open standard instruction set architecture. This customizable instruction set architecture is rebuilding the world of microprocessors with its flexibility to design the microprocessors of their need.

# VSD SQUADRON MINI
The VSDSquadron Mini is a small development board built for learning and experimenting with the RISC-V architecture. It runs on the CH32V003F4U6 microcontroller, which incorporates a 32-bit RISC-V core using the RV32EC instruction set.

# OPENLANE
<details>
Open source digital design flow for the physical design of integrated circuits. It comprises complete suite of tools in various stages of physical design.<br>
Commands to invoke the Openlane<br>


***cd Desktop/work/tools/openlane_working_dir/openlane***<br>
***docker<br>***
***./flow.tcl -interactive***


![openlane](https://github.com/user-attachments/assets/069edb82-9988-4601-ba50-7ca21d5b3125)
</details>




# TASK 1  Compilation of c code using GCC and RISC-V GCC Compilers
<details>

Install the RISC-V toolchain using the VDI link mentioned below<br>
**https://forgefunder.com/~kunal/riscv_workshop.vdi**<br>
To open VDI file, download and install Oracle VirtualBox.


![openlane](https://github.com/user-attachments/assets/50049feb-3e7a-4a86-a525-31ffa5aa3b80)


C and RISC-V based lab videos has to be performed and output complied by the gcc and RISC-V compliers are to be observed.<br>
C based lab: Commands to open the editor to type the c code

***cd***<br>
***leafpad sum1ton.c***<br>



**C CODE**<br>

![openlane](https://github.com/user-attachments/assets/afd4fa4b-5850-4bcc-b6e1-c8c9f502c34a)

Commands to view the C output complied by gcc complier

***gcc sum1ton.c***<br>
***./a.out***

![openlane](https://github.com/user-attachments/assets/4b8dcb63-dedf-4223-99e5-a8e0b79bad18)


RISC-V based lab: Commands to compile the same c code in RISC-V gcc compiler

***cat sum1ton.c***<br>
***riscv64-unknown-elf-gcc -O1 -mabi-ls64 -march-rv64i -o sum1ton.o sum1ton.c***<br>
***ls -ltr sum1ton.o***


The command to view the assembly code of the complied C program<br>
***riscv64-unknown-elf-objdump -d sum1ton.o***<br>
***/main***


![openlane](https://github.com/user-attachments/assets/20140ab8-2458-4b33-9a4a-8e1fd66b95a9)


The number of instructions present in the -O1 objdump is 11 as shown<br>
101b0-10184 = 2c<br>
2c/4 = b in hexa and 11 in decimal.


![openlane](https://github.com/user-attachments/assets/7afcadd8-cafd-4675-815d-85c28317e79e)


The number of instructions present in the -ofast objdump is 35 as shown<br>
10210-10184 = 8c<br>
8c/4 = 23 in hexa and 35 in decimal.

![openlane](https://github.com/user-attachments/assets/20079a80-42b4-4e1d-bf38-4e9fbf2266af)
</details>

# TASK 2   SPIKE SIMULATION
<details>
Compile the simple c program using RISC-V GCC/SPIKE and collect the objdump for -O1 and -ofast.

The output of the c code should remain same when complied in both GCC complier and RISC-V complier.<br>
Commands to compile the code in GCC compiler

***gcc sum1ton.c***<br>
***./a.out***

![openlane](https://github.com/user-attachments/assets/908d8123-1ae1-4a3a-af93-948bea3535c8)


Command to compile the code using RISC-V compile

***splike pk sum1ton.o***

Command to obtain the objdump of -01

***riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c***

![openlane](https://github.com/user-attachments/assets/73453487-3b7f-400f-8101-c0cbe0e3fcc2)

![openlane](https://github.com/user-attachments/assets/a8004a28-8147-45d0-9de8-7a239a9bac2b)


Command to obtain the objdump of -ofast

***riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c***



DEBUGGING

Command to open the objdump of the code in a new terminal

***riscv64-unknown-elf-objdump -d sum1ton.o | less***

![openlane](https://github.com/user-attachments/assets/de493418-3d0d-4fb7-9ca4-44014d4a1215)

Command to open the debugger

***spike -d pk sum1ton.o***

![openlane](https://github.com/user-attachments/assets/5f72d565-e176-4333-b733-cc923778a5c5)

The operations is performed in the debugger is as shown

![openlane](https://github.com/user-attachments/assets/b816df09-d1e7-4ee8-89cb-1a632331ff21)


![openlane](https://github.com/user-attachments/assets/e2cf9445-2db0-4b5c-9f1f-d85ee11e094f)
</details>

# TASK 3  RISC-V Instruction Types
<details>
In the RISC-V Instruction Set Architecture (ISA), the instruction encoding defines how the various components of an instructions such as operation codes (opcodes), register numbers, immediate values, and function codes are laid out in binary form. Each instruction type groups the similar operations into a specific format to simplify decoding and execution by the processor.

Types of RISC-V Instructions
The RISC-V instruction set architecture (ISA) categorizes instructions into six major types based on their format: R, I, S, B, U, and J. Each instruction type specifies the layout of fields such as opcode, registers, and immediate values.

THE VARIOUS RISC-V INSTRUCTION TYPES

<img width="772" alt="Image" src="https://github.com/user-attachments/assets/196ca7aa-cd4e-4709-ad31-119f6ece65a4" />








