

Instructor : Kunal Ghosh 

# Task-2:
* Refer to C-program based lab and RISCV based lab.<br/>
* Execute both the tasks in the terminal window.<br/>
*Compilers use are GCC and Risc GCC compiler.<br/>
### Using C programming:
->Make sure you are in the home directory<br/>
![Pic1](https://github.com/user-attachments/assets/ed71ea3e-afe2-4b6f-8fad-13e9cd09cd83)


->We can see the assembly main code from which location it starts<br/>
![pic2](https://github.com/user-attachments/assets/e8c58ddf-53fc-4353-bcf2-7e533ad17dc9)



->Enter the command gcc sum1ton.c<br/>
->To check the output run command ./a.out<br/>
![pic3](https://github.com/user-attachments/assets/98dff644-967c-4a60-a33e-fb2bd420876b)

<br/>

->Using Debugger d in spike to debug some locations of assembly code<br/>
->Actually here we see the initial value stack is having same value after lui instrunction<br/>
->C-Progrram compile using RISC-V gcc and run using spike<br/>
![pic4](https://github.com/user-attachments/assets/be684de7-ebe4-43ea-a91f-eb1e1a466327)

->Finally we can use the same debugger to check all other locations 



# TASK-3:

* Refer to the RISC-V software documentation and list various RISC-V Instruction code<br/>
* 32 bit instruction format for 15 unique instruction codes from objdump file<br/>

#Instruction Format for RISC-V 32-BIT Instruction code:<br/>

* Structural Diagram shows the bitwise allocation to for each general instruction<br/>

![pic6](https://github.com/user-attachments/assets/9fabe390-6600-44b0-af64-a5ee30a94b53)


#There are 6 types of instruction for Immediate encoding variables <br/>

- R-Type Instruction -Register<br/>
- I-Type Instruction- Immediate<br/>
- S-Type Instruction-Store<br/>
- B-Type Instruction-Branch <br/>
- U-Type Instruction-Upper Immediate<br/>
- J-Type Instruction-Jump<br/>

![pic5](https://github.com/user-attachments/assets/800c9eb6-191c-4d85-a91b-678e304720b9)

# Opcode and Function Fields

- Opcode: Determines the type of Instruction to be followed in 32-bit Instruction format.<br/>
- fun3 and fun7: It  specifies the type of operation need to be performed on instruction and it has different function values for each diffirent instruction<br/>

# Immediate values and registers
- Immediate value: Encoded in specific fields within the instruction<br/>
- Registers: Specific fields such as rs1(source register),rs2(source register) and  and rd(destination register)<br/>

# INSTRUCTIONS:

Machine code for  addi sp,sp,16<br/>
![pic7](https://github.com/user-attachments/assets/4827557c-4040-4064-8f41-69b11ea008a1)
# 1. Instruction: addi sp,sp,16
- Opcode: 0010011(7bits)<br/>
- Immediate : 16 (total 12 bits)<br/>
- Source register(rs1):sp (x2, 5bits)<br/>
- Function (funct3):000(3bits)<br/>
  #  Breakdown
- Immediate(16):000000010000<br/>
- rs1(sp=x2):00010<br/>
- funct3: 000<br/>
- rd(sp=x2): 00010<br/>
- opcode:0010011<br/>
32 bit encoding-000000010000 00010 000 00010 0010011<br/>


Machine code for sd s0,16(sp)<br/>
![pic8](https://github.com/user-attachments/assets/c3aa90a3-ff64-4978-b1ca-6e4ca6d86472)
# 2. Instruction: sd  s0,16(sp)
- Opcode: 0100011(7bits)<br/>
- Immediate : 16 (total 12 bits ,split into two parts :imm[11:5] and imm[4:0])<br/>
- Source register(rs2):s0 (x8, 5bits)<br/>
- Base register(rs1):sp (x2, 5bits)<br/>
- Function (funct3):011(3bits)<br/>
  #  Breakdown
- Immediate(16):000000010000<br/>
- imm[11:5](7bits):0000000<br/>
- rs2(s0=x8):01000<br/>
- rs1(ss=x2):00010<br/>
- funct3: 011<br/>
- imm[4:0](5 bits):10000
- opcode:0010011<br/>
32 bit encoding-0000000 01000 00010 011 0010011 <br/>


Machine code for  mv a1,a5 <br/>
![pic9](https://github.com/user-attachments/assets/bf8cfc48-b1bc-4ecd-b98a-eb4c3edd9450)
# 3. Instruction: mv a1,a5
- Opcode: 0010011(7bits)<br/>
- Immediate : 0 (total 12 bits)<br/>
- Source register(rs1):a5 (x15, 5bits)<br/>
- Destination Register(rd):a1(x11,5bits)<br/>
- Function (funct3):000(3bits)<br/>
  #  Breakdown
- Immediate(16):000000000000<br/>
- rs1(sp=x15):01111<br/>
- funct3: 000<br/>
- rd(sp=x11): 01011<br/>
- opcode:0010011<br/>
32 bit encoding-000000000000 01111 000 01011 0010011<br/>


Machine code for  ld a3,16(sp) <br/>
![pic10](https://github.com/user-attachments/assets/157c84dc-cfd0-49b2-9810-d48b0d87705a)
# 4. Instruction: ld a3,a16(sp)
- Opcode: 00000011(7bits)<br/>
- Immediate : 16(total 12 bits)<br/>
- Source register(rs1):sp (x2, 5bits)<br/>
- Destination Register(rd):a3(x13,5bits)<br/>
- Function (funct3):011(3bits)<br/>
  #  Breakdown
- Immediate(16):000000010000<br/>
- rs1(sp=x2):00010<br/>
- funct3: 011<br/>
- rd(sp=x13): 01101<br/>
- opcode:0000011<br/>
32 bit encoding-000000010000 00010 011 01101 0000011<br/>


Machine code for  lui  a6,oxffff8 <br/>
![pic11](https://github.com/user-attachments/assets/6b9f3552-bea5-4b0c-a618-c6b68001413e)
# 5. Instruction:lui  a6,oxffff8
- Opcode:0110111(7bits)<br/>
- Immediate : 0xffff8(total 20 bits)<br/>
- Destination register(rd):a6 (x16, 5bits)<br/>
  #  Breakdown
- Immediate(16):1111 1111 1111 1111 1000<br/>
- rd(a6=x16):10000<br/>
- opcode:0110111<br/>
32 bit encoding-11111111111111111000 10000 0110111<br/>



Machine code for  sw a5,16(s0) <br/>
![pic12](https://github.com/user-attachments/assets/1905d737-6df5-47ba-a308-2a4c1f26301f)
# 6. Instruction: mv a1,a5
- Opcode: 0010011(7bits)<br/>
- Immediate : 0 (total 12 bits)<br/>
- Source register(rs1):a5 (x15, 5bits)<br/>
- Destination Register(rd):a1(x11,5bits)<br/>
- Function (funct3):000(3bits)<br/>
  #  Breakdown
- Immediate(16):000000000000<br/>
- rs1(sp=x15):01111<br/>
- funct3: 000<br/>
- rd(sp=x11): 01011<br/>
- opcode:0010011<br/>
32 bit encoding-000000000000 01111 000 01011 0010011<br/>




















  






