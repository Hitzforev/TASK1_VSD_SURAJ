

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
- imm[11:5] (7bits):0000000<br/>
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
- Immediate(0):000000000000<br/>
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
- Immediate(16):0000 0001 0000<br/>
- rs1(sp=x2):00010<br/>
- funct3: 011<br/>
- rd(sp=x13): 01101<br/>
- opcode:0000011<br/>
32 bit encoding-000000 01101 00010 011 0000011<br/>


Machine code for  lui  a6,oxffff8 <br/>
![pic11](https://github.com/user-attachments/assets/6b9f3552-bea5-4b0c-a618-c6b68001413e)
# 5. Instruction:lui  a6,oxffff8
- Opcode:0110111(7bits)<br/>
- Immediate : 0xffff8(total 20 bits)<br/>
- Destination register(rd):a6 (x16, 5bits)<br/>
  #  Breakdown
- Immediate(ffff8):1111 1111 1111 1111 1000<br/>
- rd(a6=x16):10000<br/>
- opcode:0110111<br/>
32 bit encoding-11111111111111111000 10000 0110111<br/>



Machine code for  sw a5,16(s0) <br/>
![pic12](https://github.com/user-attachments/assets/1905d737-6df5-47ba-a308-2a4c1f26301f)
# 6. Instruction: sw a5,16(s0)
- Opcode: 0100011(7bits)<br/>
- Immediate : 16 (split into 7 bits and 5bits)<br/>
- Source register(rs1):s0 (x8, 5bits)<br/>
- Source Register(rs2):a5(x15,5bits)<br/>
- Function (funct3):010(3bits)<br/>
  #  Breakdown
- Immediate(16):000000010000<br/>
- imm[11;5]:0000000
- rs1(s0=x8):01000<br/>
- rs2(a5=x15):01111<br/>
- funct3: 010<br/>
- imm[4;0]:10000
- opcode:0100011<br/>
32 bit encoding-0000000 01000 01111 010 10000 0100011<br/>


Machine code for  ld a5,64(s0) <br/>
![pic13](https://github.com/user-attachments/assets/8eea56fb-c11f-42d5-9610-28d7603c5470)
# 7. Instruction: ld a5,64(s0)
- Opcode: 00000011(7bits)<br/>
- Immediate : 64(total 12 bits)<br/>
- Source register(rs1):s0 (x8, 5bits)<br/>
- Destination Register(rd):a5(x15,5bits)<br/>
- Function (funct3):011(3bits)<br/>
  #  Breakdown
- Immediate(64):000001000000<br/>
- rs1(s0=x8):01000<br/>
- funct3: 011<br/>
- rd(a5=x15): 01111<br/>
- opcode:0000011<br/>
32 bit encoding-000001000000 01000 011 01111 0000011<br/>


Machine code for  jal ra,1fb34<__eqtf2> <br/>
![pic14](https://github.com/user-attachments/assets/58602f0f-7a1d-4713-bd83-cd704c138623)
# 8. Instruction:jal ra,1fb34<__eqtf2>
- Opcode:1101111(7bits)<br/>
- Immediate : 0x1fb34(total 20 bits)<br/>
- Destination register(rd):ra (x1, 5bits)<br/>
  #  Breakdown
- Immediate(1fb34):0001 1111 1011 0011 0100<br/>
- rd(ra=x1):00001<br/>
- opcode:0110111<br/>
32 bit encoding-01100110100011111100<br/>


Machine code for sd s1,8(sp) <br/>
![pic15](https://github.com/user-attachments/assets/1eb65baf-d267-43a0-99ec-d484b6567db3)
# 9. Instruction: sd s1,8(sp)
- Opcode:0100011(7bits)<br/>
- Immediate : 00000000001000(total 12 bits)<br/>
- Source register(rs1):sp (x2, 5bits)<br/>
- Source register(rs2):s1 (x9, 5bits)<br/>
  #  Breakdown
- Immediate(8):000000001000<br/>
- imm[11:5]:0000000<br/>
- rs2:10000<br/>
- rs1:00010<br/>
- funct3: 011<br/>
- imm[4:0]:01000<br/>
- opcode:0100011<br/>
32 bit encoding-0000000100000001001101000<br/>


Machine code for li s4,9 <br/>
![pic16](https://github.com/user-attachments/assets/a3d83f1c-e225-4701-a3c7-39f5dd3c02c8)
# 10. Instruction: li s4,9
- Opcode:0010011(7bits)<br/>
- Immediate :9(total 12 bits)<br/>
  #  Breakdown
- Immediate(8):000000010000<br/>
- rs1:00000<br/>
- funct3: 000<br/>
- rd:01100
- opcode:0010011<br/>
32 bit encoding-0000000100000000000001100010011<br/>

Machine code for jal ra,18b44<strlen> <br/>
![pic17](https://github.com/user-attachments/assets/f60bab56-d445-465f-83ea-754b37214aa5)
# 11. Instruction:jal ra,18b44<strlen>
#  Breakdown
- Immediate(18b44):00011000101101000100<br/>
- Target address =18b44 and current address=10000<br/>
- offset=ox18b44-ox10000=65,536(decimal)
- Finally65,536 in binary (20bits format)=0001 0000 0000 0000 0000<br/>
- after jal operation -0010 0000 0000 0000 0000<br/>
- rd(x1):00001
- opcode:1101111<br/>
32 bit encoding-0 0000000000 001000000 00001 1101111<br/>

Machine code for jal ra,1680c<_localeconv_r> <br/>
![pic12_](https://github.com/user-attachments/assets/1e939b04-efd2-4590-afb8-2dd74b34a427)
# 12. Instruction:jal ra,1680c<_localeconv_r>
#  Breakdown
- Immediate(1680c):0001 0110 1000 0000 1100<br/>
- Target address =1680c and current address=10000<br/>
- offset=ox1680c-ox10000=26,636(decimal)
- Finally 26,636 in binary (20bits format)=0000 0110 1000 0000 1100<br/>
-After jal encoding operation:0000 1101 0000 0001 1000<br/>
- rd(x1):00001<br/>
- opcode:1101111<br/>
32 bit encoding-0 0000001100 0 00011010 00001 1101111<br/>

Machine code for jal ra,1045c<_vfprintf_r> <br/>
![pic19](https://github.com/user-attachments/assets/2d39da63-db7a-4e3c-8e46-062ce9fb01df)
# 13. Instruction:jal ra,1045c<_vfprintf_r>
#  Breakdown
-Immediate(1045c):00010000010001011100<br/>
- Target address =1045c and current address=10000<br/>
- offset=ox1045c-ox10000=1116(decimal)
- Finally 1116 in binary =0000 0000 0100 0101 1100<br/>
- after jal operation =0000 0000 1000 1011 1000<br/>
- imm[20],imm[10:1],imm[11],imm[19:12]<br/>
- rd(x1):00001<br/>
- opcode:1101111<br/>
32 bit encoding-0 0010111000 1 00000000 00001 1101111 <br/>


Machine code for  ld a5,0(s0) <br/>
![pic22](https://github.com/user-attachments/assets/052fb9e3-9d52-44c2-9a33-66a22fb87e79)
# 14. Instruction: ld a5,0(s0)
- Opcode: 00000011(7bits)<br/>
- Immediate : 0(total 12 bits)<br/>
- Source register(rs1):s0 (x8, 5bits)<br/>
- Destination Register(rd):a5(x15,5bits)<br/>
- Function (funct3):011(3bits)<br/>
  #  Breakdown
- Immediate(0):000000000000<br/>
- rd(a5=x15): 01111<br/>
- funct3: 011<br/>
- rs1(s0=x8):01000<br/>
- opcode:0000011<br/>
32 bit encoding-000000001111011010000000011 <br/>

Machine code for  mv a2,a1 <br/>
![pic23](https://github.com/user-attachments/assets/4f9c62f2-7c72-407f-a74e-7050f2e208ff)
# 15. Instruction: mv a2,a1
- Opcode: 0010011(7bits)<br/>
- Immediate : 0 (total 12 bits)<br/>
- Source register(rs1):a1 (x11, 5bits)<br/>
- Destination Register(rd):a2(x12,5bits)<br/>
- Function (funct3):000(3bits)<br/>
  #  Breakdown
- Immediate(0):000000000000<br/>
- rs1(a1=x11):01011<br/>
- funct3: 000<br/>
- rd(s2=x12): 01100<br/>
- opcode:0010011<br/>
32 bit encoding-000000000000 01011 000 01100 0010011<br/>




# Task-4:

# Use the Risc_V Core Verilog netlist and testbench for functional simulation experiment. Upload waveform snapshots for the commands on your Github<br/>


1.Clone the Reference Repository First,clone the repository that contains the Verilog netlist and testbench:<br/>
     
      $ git clone https://github.com/vinayrayapati/rv32i.git my_riscv_project
      
      $ cd my_riscv_project
     
 ![pic24](https://github.com/user-attachments/assets/0a6071ec-72c2-4380-9af5-1d4b76b820e1)

2.Set Up simulation Tools (verilog and GTKWave)Install Icarus Verilog and GTKWave for Simulation and waveform.<br/>

    $ sudo apt update
    $ sudo apt install iverilog gtkwave
    $ nano iiitb_rv32i_tb.v

3.Edit the Testbench File:Open the testbench file in a text editor <br/>
![pic25](https://github.com/user-attachments/assets/58340ebe-839f-4ca1-9070-d27614c61221)

- Here the testbench should include the above code<br/>


  $ dumpfile("simulation.vcd"); // Name of the VCD file<br/>
  $ dumpvars(0, testbench); // Dump all signals of the testbench module<br/>

4.Run the Functional Simulation Signals and Instantiation of the design<br/>
Complie and Simulate:<br/>

    $ iverilog -o rv32i_simulation iiitb_rv32i.v iiitb_rv32i_tb.v
    
    $ vvp rv32i_simulation

![pic26](https://github.com/user-attachments/assets/5922efad-64c9-48c7-9bf5-24f2eab65dd5)

View Waveform:<br/>

    $ gtkwave simulation.vcd


![pic27](https://github.com/user-attachments/assets/21f53af2-6b9c-4fc6-9a37-ca625d5adf5c)

# ADD R6,R1,R2
![pic29](https://github.com/user-attachments/assets/858ebc79-995c-4f5a-a6d3-bacec664ee69)
->EX_MEM_IR[31:0]=32'h02208300<br/>
->Operation - 1+2=3<br/>

# SUB R7,R1,R2
![pic30](https://github.com/user-attachments/assets/07164448-2f51-4092-b388-ef3459cba9c4)
->EX_MEM_IR[31:0]=32'h02209380<br/>
->Operation - 1-2=-1(In signed decimal form)<br/>
-> In hexadecimal format it is 'FFFFFFFFF'(2's Compliment)<br/>

# AND R8,R1,R3
![pic31](https://github.com/user-attachments/assets/bf29833f-90a7-4414-8913-d3efc73fc86e)
->EX_MEM_IR[31:0]=32'h0230A400<br/>
->Operation - 1 & 3 =1(bitwise AND operation) -> 001 & 011=001<br/>

# OR R9,R2,R5 
![pic32](https://github.com/user-attachments/assets/11d295eb-9195-42dd-b3aa-5d51a2a469d9)
->EX_MEM_IR[31:0]=32'h02513480<br/>
-> Operation - 010 | 101=111 (bitwise or)<br/>

#XOR R10,R1,R4
![pic33](https://github.com/user-attachments/assets/8e00f6a5-cb2a-4716-8a50-e72593551117)
->EX_MEM_IR[31:0]=32'h0240C500<br/>
-> Operation - 001 ^ 100=101 (bitwise xor)<br/>

# SLT R1,R2,R4
![pic34](https://github.com/user-attachments/assets/2a83175b-9de7-4577-b44d-45171ed13b23)
->EX_MEM_IR[31:0]=32'h02415580<br/>
-> If rs1<rs2 Output =1 or else 0<br/>
-> Operation - 2<4 =1;<br/>

# ADDI R12,R4,4
![pic35](https://github.com/user-attachments/assets/67b3feda-f674-400b-92b8-aa1451419622)
->EX_MEM_IR[31:0]=32'h00520600<br/>
-> ADDI means 'Add Immediate'<br/>
-> Operation 4+5=9<br/>














-





 




















  






