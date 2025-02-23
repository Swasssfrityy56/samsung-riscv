Basic Details<br>
Name: Swasthi A Anekar<br>
College: Global Academy of Technology<br>
E-mail: anekarswasthi@gmail.com

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



1. R-Type (Register Type)

![r_type](https://github.com/user-attachments/assets/df75cd17-8022-4e28-9592-e39f2b9eec17)


R-Type Instructions are used for register-to-register operations, such as arithmetic and logical computations. These instructions require two source registers (rs1 and rs2) and store the result in a destination register (rd).

opcode[0-6]:	Specifies the operation type.<br>
rd[7-11]:	Destination register.<br>
funct3[12-14]:	Specifies the operation (subtype).<br>
rs1[15-19]:	First source register.<br>
rs2[20-24]:	Second source register.<br>
funct7[25-31]:	Further specifies the operation.<br>


2. I-Type (Immediate Type)

![i_type](https://github.com/user-attachments/assets/455c04e9-ae9c-40f6-bada-ad7f77702b91)


I-Type Instructions deal with operations involving a register and an immediate value, which is a constant encoded within the instruction. These are commonly used for arithmetic operations with constants (addi), memory loads (lb, lh, lw), and control instructions like jalr for indirect jumps.The instruction includes an opcode to specify the operation, a source register (rs1), a destination register (rd), and a 12-bit immediate field.

opcode[0-6]:	Specifies the operation type.<br>
rd[7-11]:	Destination register.<br>
funct3[12-14]:	Specifies the operation (subtype).<br>
rs1[15-19]:	Source register.<br>
imm[11:0]	[20-31]:	12-bit immediate value.<br>


3.S-Type (Store Type)

![s_type](https://github.com/user-attachments/assets/e51da433-7031-4050-979e-0744450c7e44)


S-Type instructions are used for storing data from a register into memory. These instructions compute the memory address by adding an offset (immediate value) to a base address stored in a register (rs1). The data to be stored is taken from another register (rs2). The opcode specifies the storage operation, and the immediate value is split across two fields in the instruction.

opcode[0-6]:	Specifies the operation type.<br>
imm[4:0]	[7-11]:	Lower 5 bits of immediate value.<br>
funct3[12-14]:	Specifies the operation (subtype).<br>
rs1[15-19]:	Base address register.<br>
rs2[20-24]:	Data source register.<br>
imm[11:5]	[25-31]:	Upper 7 bits of immediate value.<br>


4.B-Type (Branch Type)

![b_type](https://github.com/user-attachments/assets/5d9882f0-f3d1-4781-9703-5e14609a3560)


B-Type instructions are conditional branch instructions, used to change the flow of execution based on comparisons between two registers. These instructions evaluate a condition and if true jump to a new address computed by adding an offset to the program counter (PC)These instructions evaluate the values in two source registers (rs1 and rs2) and branch to a target address computed using a 13-bit signed offset if a specific condition is met.

opcode	[0-6]	Specifies the branch operation.<br>
imm[11]	[7]	Most significant immediate bit.<br>
imm[4:1]	[8-11]	Immediate bits [4:1].<br>
funct3	[12-14]	Specifies the branch condition.<br>
rs1	[15-19]	First source register.<br>
rs2	[20-24]	Second source register.<br>
imm[10:5]	[25-30]	Immediate bits [10:5].<br>
imm[12]	[31]	Immediate bit [12].<br>


5.U-Type (Upper Immediate Type)

![u_type](https://github.com/user-attachments/assets/ad9aae4a-3a96-466e-8fc6-f1f034687b8e)


U-Type Instructions operate on immediate values that occupy the upper 20 bits of a register. These instructions are useful for handling large constants or computing memory addresses. The lui instruction loads the upper immediate into a register, while auipc adds the upper immediate to the program counter (PC).

opcode[0-6]:	Specifies the operation type.<br>
rd[7-11]:	Destination register.<br>
imm[31:12]	[12-31]:	20-bit immediate value.<br>


6.J-Type (Jump Type)

![j_type](https://github.com/user-attachments/assets/f97185a2-147f-4c82-9cef-e6ee195647fb)


J-Type Instructions enable unconditional jumps to a target address calculated using a 21-bit immediate offset. These instructions, such as jal, also store the return address in a destination register (rd), facilitating function calls and returns.

opcode[0-6]:	Specifies the jump operation.<br>
rd[7-11]:	Destination register.<br>
imm[19:12]	[12-19]:	Immediate bits [19:12].<br>
imm[11]	[20]:	Immediate bit [11].<br>
imm[10:1]	[21-30]:	Immediate bits [10:1].<br>
imm[20]	[31]:	Most significant immediate bit.<br>


# EXPLANATION OF THE RISC-V INSTRUCTION 
     

Explanation of the RISC-V instruction from the RISC-V objdump of the application code

![O-fast_obj_dump](https://github.com/user-attachments/assets/644f5616-c5c2-4f68-bfcd-0c2f90dea464)

1.**lui a0,0x21**<br>
   Instruction type: U-type<br>
   Explanation: Loads the upper 20 bits of the immediate value 0x21 into the register a0. The lower 12 bits of a0 are filled with zeros.<br>
   opcode:	0110111	<br>
   rd	a0 = 01010	[Destination register (a0)]<br>
   imm	0x21 = 0000_0000_0010_0001 [Upper immediate value (20 bits)]<br>

    32-bit instruction: 0000_0000_0010_0001_01010_0110111

2.**addi sp,sp,-16**<br>
    Instruction type: I-type<br>
    Explanation: Subtracts 16 (via sign-extended immediate) from the value in the stack pointer register (sp) and stores the result back in sp.<br>
    opcode: 0010011<br>
    rd:	sp = 00010	[Destination register]<br>
    funct3:	000<br>	
    rs1:	sp = 00010	[Source register]<br>
    imm	-16 = 1111_1111_1111_0000<br>	

    32- bit instruction: 1111_0000_00010_00010_000_00010_0010011


3.**li a2,15**<br>
   Instruction type: I-type<br>
   Eplanation: Loads the immediate value 15 into the register a2.<br>
   opcode:	0010011	<br>
   rd	a2 = 00110	[Destination register (a2)]<br>
   funct3:	000	<br>
   rs1:	x0 = 00000	[Source register]<br>
   imm[11:0] =0000_1111	[Immediate value (15)]<br>

    32 - bit instruction: 0000_0000_0000_1111_00000_000_00110_0010011

4.**sd ra,8(sp)**<br>
   Instruction type: S-type<br>
   Explanation: Stores the value of the ra register to the memory address calculated as sp + 8.<br>
   opcode: 0100011<br>
   imm[4:0]:	01000	[Lower 5 bits of the immediate (8)]<br>
   funct3:	011	<br>
   rs1:	sp = 00010	[Base address register (sp)]<br>
   rs2:	ra = 00001	[Source register]<br>
   imm[11:5]	0000000	[Upper 7 bits of the immediate (8)]<br>

    32 - bit instruction: 0000000_00001_00010_011_01000_0100011

5.**ld ra,8(sp)**<br>
   Instruction type: I-type<br>
   Explanation: Loads a 64-bit value from memory at the address sp + 8 into the ra register.<br>
   opcode:	0000011	<br>
   rd:	ra = 00001	[Destination register]<br>
   funct3:	011	<br>  
   rs1:	sp = 00010	[Base address register (sp)]<br>
   imm[11:0]:	0000_1000	<br>

    32 - bit instruction: 0000_1000_00010_00001_011_0000011

6.**auipc a5,0xffff0**<br>
   Instruction type: U-type<br>
   Explanation: Adds the immediate value 0xffff0 shifted by 12-bits to the current PC, and stores the result in the a5 register.<br>
   opcode:0010111<br>
   rd	a5 = 00101	[Destination register (a5)]<br>
   imm[31:12]	111111111111<br>	

    32 - bit instruction: 111111111111_00101_0010111

7.**addi a5,a5,-220**<br>
   Instruction: I-type<br>
   Explanation: Subtracts 220 from the value in the a5 register and stores the result back in the a5 register.<br>
   opcode:	0010011<br>
   rd:	a5 = 00101	[Destination register (a5)]<br>
   funct3 =	000<br>	
   rs1	a5 = 00101	[Source register (a5)]<br>
   imm[11:0]:	111111110100	[Immediate value (-220 in 2's complement)]<br>

    32 - bit instruction: 111111110100_00101_000_00101_0010011

8.**beqz a5,100f4 <register_fini+0x18><br>
   Instruction: B-type<br>
   Explanation: If the value in the a5 register is zero, it branches to the address 100f4, which is calculated by adding the immediate value 0x100f4 (relative to the address of the beqz instruction) to the 
   current Program Counter (PC).<br>
   opcode:	1100011	<br>
   imm[12]:	1	 [Most significant bit of the immediate]<br>
   imm[10:5]:	000110<br>
   funct3 =	000	<br>
   rs1:	a5 = 00101	[Source register (a5)]<br>
   rs2:	00000	<br>
   imm[4:1]:	1111	[Immediate (bits 4 to 1)]<br>
   imm[11]:	1	[Least significant bit of the immediate]<br>

    32 - bit instruction: 0001_1111_00000_00101_000_1111_1100011

9.**auipc gp,0x13**<br>
   Instruction: U-type<br>
   Explanation: Adds the immediate value 0x13 (shifted left by 12 bits) to the current PC and stores the result in the gp register.<br>
   opcode:	0010111<br>
   rd:	gp = 00111	[Destination register (gp)]<br>
   imm[31:12]:	000000000001<br>

    32 - bit instruction: 000000000001_00111_0010111

10.**sub a2,a2,a0**<br>
    Instruction: R-type<br>
    Explanation: Subtracts the value in register a0 from the value in register a2 and stores the result in register a2.<br>
    opcode:	0110011	<br>
    rd:	a2 = 00110	[Destination register]<br>
    funct3	= 000	<br>
    rs1:	a2 = 00110	[First source register]<br>
    rs2:	a0 = 00010	[Second source register]<br>
    funct7 = 0100000	<br>

    32 - bit instruction: 0100000_00110_00010_000_00110_0110011

11.**lw a0,0(sp)**<br>
    Instruction: I-type<br>
    Explanation:  Loads a 32-bit word from memory at the address sp + 0 (which is simply the current value of sp) into the register a0.<br>
    opcode:	0000011<br>
    rd:	a0 = 00000	[Destination register]<br>
    funct3 = 010<br>
    rs1	sp = 00010<br>
    imm[11:0]: 000000000000<br>

    32 - bit instruction: 000000000000_00010_010_00000_0000011

12.**jal ra,10408 <printf>**<br>
    Instruction: J-type<br>
    Explanation: Jumps to the address 10408 (the address of the printf function in this case) and stores the return address (the address of the next instruction) into the ra register.<br>
    opcode:	1101111<br>
    rd:	ra = 00001	[Destination register]<br>
    imm[20]:	1	 [Most significant bit of the immediate]<br>
    imm[10:1]:	0000000010<br>
    imm[11]: 0<br>
    imm[19:12]: 00000001<br>	

    32 - bit instruction: 000000000001_00001_0000000010_1101111

13.**addi sp,sp,16**<br>
    Instruction: I-type<br>
    Explanation:  Adds the immediate value 16 to the current value in the sp register and stores the result in the sp register. This effectively increments the stack pointer by 16 bytes.<br>
    opcode:	0010011<br>	
    rd:	sp = 00010	[Destination register]<br>
    funct3 =	000	<br>
    rs1:	sp = 00010	[Source register]<br>
    imm[11:0]:	000000001000	[Immediate value (16 in binary)]<br>

    32 - bit instruction: 000000001000_00010_000_00010_0010011

14.**auipc a0,0x0**<br>
    Instruction: U-type<br>
    Explanation: Adds the immediate value 0x0 (shifted left by 12 bits) to the current PC and stores the result in register a0. Since the immediate is 0x0, this effectively copies the current PC to a0.<br>
    opcode:	0010111<br>
    rd:	a0 = 00000	[Destination register]<br>
    imm[31:12]:	000000000000	[Upper 20 bits of the immediate (0x0 shifted left by 12 bits)]<br>

    32 - bit instruction: 000000000000_00000_0010111

15.**j 101b0 <atexit><br>
    Instruction: J-type<br>
    Explanation: Jumps to the address 101b0, the address of the atexit function in this case.<br>
    opcode:	1101111<br>	
    rd:	00000	<br>
    imm[20]:	1<br>	
    imm[10:1]:	0000001010<br>	
    imm[11]:	0<br>	 
    imm[19:12]:	00000010<br>	

    32 - bit instruction: 0000001010_00000_0000001010_1101111
      
</details>



# TASK 4  Functional Simulation of RISC-V Core
<details>


  
  Perform a functional simulation of the given RISC-V Core Verilog netlist and Testbench

    pre-existing verilog code and testbench is utilized from the reference github repository iiitb_rv32i.

Download the files iiitb_rv32i.v and iiitb_rv32i_tb.v from the reference repository

Commands to simulate the verilog code
           
           iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
           ./iiitb_rv32i

![Screenshot 2025-01-24 131312](https://github.com/user-attachments/assets/98e45dcf-a961-4dfa-9756-701ee7448320)

Command to open GTKWave

    gtkwave iiitb_rv32i.vcd


![Screenshot 2025-01-24 174930](https://github.com/user-attachments/assets/79e39dfe-a3a7-451f-876c-0ecae3faaf73)


Instructions obtained from the verilog file

![image](https://github.com/user-attachments/assets/5f36b4ec-6c7b-4a6d-bd1d-90dbd13b8624)


Analyzing the instructions through waveforms

1. **add r6,r1,r2.(i1)**

![Screenshot 2025-01-24 180150](https://github.com/user-attachments/assets/45b053b3-a4e1-4e5d-95d9-3c30e7591426)

2. **sub r7,r1,r2.(i2)**

![Screenshot 2025-01-24 180714](https://github.com/user-attachments/assets/2e92e100-2212-4661-a413-0a9b94711a50)

3. **and r8,r1,r3.(i3)**

![Screenshot 2025-01-24 181034](https://github.com/user-attachments/assets/027971a3-39bc-4265-9d68-a881467319d1)

4. **or r9,r2,r5.(i4)**

![Screenshot 2025-01-24 181129](https://github.com/user-attachments/assets/173b8b43-a5d2-497c-bc02-dfd8a32e0fe9)

5. **xor r10,r1,r4.(i5)**

![Screenshot 2025-01-24 181935](https://github.com/user-attachments/assets/f5848a44-8f45-4726-9925-a1d55be68d41)

6. **slt r11,r2,r4.(i6)**

![Screenshot 2025-01-24 182020](https://github.com/user-attachments/assets/27a2b40a-7c2f-4311-92ce-6f280b60d306)

7. **addi r12,r4,5.(i7)**

![Screenshot 2025-01-24 182046](https://github.com/user-attachments/assets/3bef80b0-219b-4cce-b1b6-63dde403a825)

8. **beq r0,r0,15(i10)**

![Screenshot 2025-01-24 183343](https://github.com/user-attachments/assets/80830d4a-c103-4963-a093-99c5335aa5b6)

9. **add r14,r2,r2.(i11)**

![Screenshot 2025-01-24 184342](https://github.com/user-attachments/assets/d4cb1b56-3c04-4a42-b2f4-0973f6a67e4b)

</details>





# TASK 5
<details>



# SMART HOME TEMPERATURE AND HUMIDITY MONITER

# Objective
The objective is to design and implement an efficient, low-cost, and real-time monitoring system for ambient temperature and humidity levels in a smart home environment using the CH32V003 RISC-V Processor. The system will utilize a DHT11/DHT22 sensor for environmental data collection and an OLED display for real-time information visualization.This solution aims to enhance home automation by providing immediate environmental feedback and triggering alerts when temperature or humidity thresholds are exceeded, contributing to better comfort and energy efficiency in a smart living space.

# Component Preparation

1.CH32V003 RISC-V Processor Development Board<br>
2.DHT11 Temperature and Humidity Sensor<br>
3.Jumper Wires<br> 
4.USB to UART Module (for programming)<br>

# Specification of the components

1.CH32V003 RISC-V Processor Development Board<br>
  a.Operating Voltage: 1.8V to 3.6V<br>
  b.Communication Interfaces: I2C, SPI, UART<br>

2.DHT11 Temperature and Humidity Sensor<br>
  a.Operating Voltage: 3.3V to 5V<br>
  b.Temperature Accuracy: ±2°C<br> 
  c.Humidity Range: 0% to 100% RH<br>
  d.Interface: Single-wire digital output<br>




CIRCUIT CONNECTION

![crkt](https://github.com/user-attachments/assets/eba4c989-43d7-4fc5-a246-88c1e9e83460)


# Connections

1.CH32V003 Development Board Setup

   a.GND of CH32V003 → GND of the USB-UART module<br>
   b.TX Pin of CH32V003 → RX Pin of the USB-UART module<br>
   c.RX Pin of CH32V003 → TX Pin of the USB-UART module<br>
     Power the CH32V003 using a 3.3V power supply.<br> 


2.CH32V003 and DHT11/DHT22 Sensor Connections

   a.VCC of DHT to VIN of CH32V003<br>
   b.GND of DHT to GND of CH32V003<br>
   c.DATA of DHT to PA1 of CH32V003<br>



</details>


# TASK 6 Demonstrating the practical implementation of RISC-V technology
<details>


# Components Setup
![Components setup](https://github.com/user-attachments/assets/15adfbed-eb14-4536-8ac9-fa01409e0595)


# Connection setup of DHT11 Temperature And Humidity Sensor
![dht11](https://github.com/user-attachments/assets/e97e2aff-a57b-4abf-a289-a6162611c4f3)


# Connection setup of VSDSquadron Mini
![vsd](https://github.com/user-attachments/assets/45b0634d-1c80-4cf8-8365-fe3b0ae76220)


# Output Display in Serial Monitor
![output](https://github.com/user-attachments/assets/9ef6c48c-a7b7-4459-a1d9-84e73825bcc0)






# Code for application

    #include <ch32v00x.h>
    #include <debug.h>

    #define BLINKY_GPIO_PORT GPIOD
    #define BLINKY_GPIO_PIN GPIO_Pin_6
    #define BLINKY_CLOCK_ENABLE RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE)

    void NMI_Handler(void) __attribute__((interrupt("WCH-Interrupt-fast")));
    void HardFault_Handler(void) __attribute__((interrupt("WCH-Interrupt-fast")));
    void Delay_Init(void);
    void Delay_Ms(uint32_t n);

    int main(void)
    {
	        NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1);
	        SystemCoreClockUpdate();
	        Delay_Init();

	        GPIO_InitTypeDef GPIO_InitStructure = {0};

	        BLINKY_CLOCK_ENABLE;
	        GPIO_InitStructure.GPIO_Pin = BLINKY_GPIO_PIN;
	        GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
	        GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
	        GPIO_Init(BLINKY_GPIO_PORT, &GPIO_InitStructure);

	        uint8_t ledState = 0;
	        while (1)
	  {
		   GPIO_WriteBit(BLINKY_GPIO_PORT, BLINKY_GPIO_PIN, ledState);
		   ledState ^= 1; // invert for the next run
		   Delay_Ms(1000);
	  }
    }

    void NMI_Handler(void) {}
    void HardFault_Handler(void)
    {
	    while (1)
	  {
	  }
    }



# Application Demonstration

https://github.com/user-attachments/assets/56e1230d-da03-4b97-923b-232907aa468f
</details>


# Acknowledgement
<details>

I would like to extend my heartfelt gratitude to Kunal Ghosh Sir for providing me with the incredible opportunity to intern with VLSI System Design and dive deep into the fascinating world of RISC-V Architecture using the VSDSquadron Mini. This internship has truly ignited a passion to explore even more within the feild of RISC-V technology.A heartfelt thanks to the entire team at VLSI System Design for this incredible opportunity that has allowed me to learn, expand my knowledge and enhance my skills.

</details>

















