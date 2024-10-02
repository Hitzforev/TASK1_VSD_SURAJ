

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

#Immediate values and registers
- Immediate value: Encoded in specific fields within the instruction<br/>
- Registers: Specific fields such as rs1(source register),rs2(source register) and  and rd(destination register)<br/>



  






