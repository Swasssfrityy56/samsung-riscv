# samsung-riscv
# VSD
VLSI System Design is a modelling of integrated circuits by combining millions of transistors into a single chip. The main aim is to design a system with optimal cost, low power consumptin, high performance.

# RISC-v 
REDUCED INSTRUCTION SET COMPUTER
RISC-V is an open standard instruction set architecture. This customizable instruction set architecture is rebuilding the world of microprocessors with its flexibility to design the microprocessors of their need.

# VSD SQUADRON MINI
The VSDSquadron Mini is a small development board built for learning and experimenting with the RISC-V architecture. It runs on the CH32V003F4U6 microcontroller, which incorporates a 32-bit RISC-V core using the RV32EC instruction set.

# OPENLANE
Open source digital design flow for the physical design of integrated circuits. It comprises complete suite of tools in various stages of physical design.<br>
Commands to invoke the Openlane<br>


***cd Desktop/work/tools/openlane_working_dir/openlane***<br>
***docker<br>***
***./flow.tcl -interactive***


![openlane](https://github.com/user-attachments/assets/069edb82-9988-4601-ba50-7ca21d5b3125)




# TASK 1

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







