# VSDSquadron_mini_research
VSDSquadron mini board research 
## LAB 1: Write a C-Program and compile using RISCV compiler and Disassemble.
### Task 1: Write a C-program that will compute the sum from 1 to n.
We will now write a C-Program to compute the sum from 1 to n and execute using GCC.<br>
<figure>
<img width="695" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/295d88ca-a29c-4ce1-aae8-453f4cb38eb0"><br>
<figurecaption>
Fig 1 C-program to compute the sum from 1 to n.<br>  
</figurecaption>
</figure><br><br>
<figure>
<img width="927" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/3e30e460-efe4-4213-b8e6-bffe24ad53eb"><br>
<figurecaption>Fig 2 Steps leading up to the final output of the c-program sum1ton.c and verified output </figurecaption>
</figure><br><br>
<figure>
<img width="211" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/4e612f90-ca34-4e21-bec3-463150ac4742"><br>
<figurecaption>Fig 3 Solution for n=500 is also verified and correct. </figurecaption>
</figure><br><br>

From figures Fig 1, Fig 2 and Fig 3 we can conclude that the C-program written is compiling successfully on gcc platform and is also producing the correct solution. <br>
### Task 2: Compile the written C-program using RiscV GCC compiler and disassemble.
<figure>
<img width="496" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/7657c233-9ed3-48b0-b311-3beb9208f742"><br>
<figurecaption>
Fig 4 Compiling the written C-Program using RISCV GCC compiler and generating output file sum1ton.o<br>  
</figurecaption>
</figure><br><br>
<figure>
<img width="356" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/68e72eea-99d3-4e26-a263-7b2ff62d2582"><br>
<figurecaption>
Fig 5 Running command to disassemble sum1ton.o<br>  
</figurecaption>
</figure><br><br>

Disassembling the sum1ron.o gives a bunch of assembly language code. We will have to fetch the main section.<br>

<figure>
<img width="790" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/fcb4b04c-d787-467f-97e1-3a24c5d46c93"><br>
<figurecaption>
Fig 6 Total no of instructions in main for O1 is 15<br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="527" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/7f2ff7d7-1b4e-4d53-ad00-1c90297d628f"><br>
<figurecaption>
Fig 7 RiscV Ofast command<br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="780" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/f09f7f80-eaa9-4593-8d41-e4f515d2ec47"><br>
<figurecaption>
Fig 8 Total no of instructions in main for Ofast is 12<br>  
</figurecaption>
</figure><br><br>

## LAB 2: Write a simple C- Program for Clock Cycle Divider: Crafting a Digital Clock Divider Circuit and compile using RISC V GCC compiler

The first task in lab 2 is to find a desirable C-Program code for the project I am working on. The project is am working on is **Clock Cycle Divider**. <br>
Below is a sample C-Program I have chosen to execute. I have used AI tools to generate this code. <br>
```
#include <stdio.h>
#include <stdbool.h>

#define DIVIDE_BY 4  // You can change this value to divide by a different factor

void clock_divider(int divide_by) {
    bool output_clock = false;
    int counter = 0;

    printf("Clock Divider by %d\n", divide_by);
    printf("Input Clock | Output Clock\n");
    printf("---------------------------\n");

    while (counter < divide_by * 2) {  // Run for enough cycles to observe the division
        bool input_clock = (counter % 2 == 0);  // Generate a simple clock signal (0, 1, 0, 1,...)
        printf("     %d      |      %d\n", input_clock, output_clock);

        if (input_clock) {
            if (counter % divide_by == 0) {
                output_clock = !output_clock;  // Toggle the output clock
            }
        }

        counter++;
    }
}

int main() {
    clock_divider(DIVIDE_BY);
    return 0;
}
```
**Explanation of above C-Program**<Br>
Preprocessor directives included:<br>
stdio - Standard Input/Output Library.<br>
stdbool - Standard Boolean Library <br>

**#define DIVIDE_BY 4** Defines constant variable that represents the factor by which the clock is divided. <br>

We then initiate a function clock_divider. This function takes an integer argument divide_by and does not return any value. The function houses the logic for clock divider.<br>
The Clock divider logic :<br>
Initialize the boolean output clock variable to false and initialize clock counter to "0".<br>
Print initial setup for clock cycle divider task.<br>
**while (counter < divide_by * 2)** Defines the no of cycles for the output_clock.<br>
After every input clock cycle increment the counter. Do this till the requiered no of cycles is met.<br> 
Execute the main program referencing the function.<br>

<br><br>
<figure>
<img width="389" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/c386fe85-52eb-4916-aded-c7a79a6d8373"><br>
<figurecaption>
Fig 9 clock_cycle_divider.c ready to be compiled on gcc<br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="308" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/c3e6d1ab-08cf-4d53-a17c-76043138d828"><br>
<figurecaption>
Fig 10 clock_cycle_divider.c compiled on GCC. Clock divider output obtained accurately. <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="593" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/503ab97c-7726-4555-8cd2-58078470fc9b"><br>
<img width="725" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/38858f18-43ef-4c6f-b86c-d176ed3295e2"><br>
<figurecaption>
Fig 11 RISCV GCC compilation command for clock_cycle_divider.c O1 (option 1) and its disassembled output for the main part, it has a total of 8 instructions<br>  
</figurecaption>
</figure><br><br>

The clock_cycle_divider.o is disassembled (converted to assembly language program) using the below command.<br>
**riscv64-unknown-elf-objdump -d clock_cycle_divider.o**

<figure>
<img width="610" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/8c3040bf-f45d-4cf5-af7b-530281aeafee"><br>
<img width="728" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/eba218ee-f33a-4598-84bb-113c5d640bb5"><br>    
<figurecaption>
Fig 12 RISCV GCC compilation command for clock_cycle_divider.c Ofast (option fast) and its disassembled output for the main part, it has a total of 8 instructions i.e. same as O1 <br>  
</figurecaption>
</figure><br><br>

## LAB 3: Spike Simulation and debug of C-Program
The first task of Lab3 is to do the spike simulation of the output of the RISCV GCC simulation **"sum1ton.o"**.<br>  
The command used for spike simulation is:<br>
**spike pk sum1ton.o** <br>
<figure>
<img width="500" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/fc755a22-f659-4528-bfd9-ac87468338fb"><br>    
<figurecaption>
Fig 13 Standard GCC simulation vs Spike simulation output comparison for Ofast case of sum1ton.o(gives same output, successful simulation) <br>  
</figurecaption>
</figure><br><br>

The next task is to debug the sum1ton.o. For this, we would need a debugger.<br> 
The command for debugging is:<br>
spike -d pk sum1ton.o <br>
We enter the spike area. Here we can execute a part of the code to check its behavior. <br>

<figure>
<img width="323" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/f89f5098-57b7-465d-a9ad-711ab4dc58bd"><br>    
<figurecaption>
Fig 14 Step by Step execution of assembly code for main part of sum1ton for Ofast simulations<br>  
</figurecaption>
</figure><br><br>

Below is the explanation of some of the assembly instructions seen in RISC V simulation. <br>
<figure>
<img width="667" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/fdcfbe4d-78f8-41c8-81db-51cbb3d395f6"><br>    
<figurecaption>
Fig 15 LUI Instruction <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="665" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/b271fac1-b5ab-4b35-8a77-52b17dffd9b9"><br>    
<figurecaption>
Fig 16 addi Instruction <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="502" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/7fa997d1-8058-40c2-8ca3-9d0db6280522"><br>    
<figurecaption>
Fig 17 Standard GCC simulation vs Spike simulation output comparison of O1 (gives same output, successful simulation) <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="311" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/1e7fa57f-b219-4268-a9a7-5db741407f79"><br>    
<figurecaption>
Fig 18 Step by Step execution of assembly code for main part of sum1ton for O1 simulation(gives same output, successful simulation) <br>  
</figurecaption>
</figure><br><br>

The next task in lab 3 is to do the spike simulation and debugging of main clock cycle divider C-Program.<br>
<figure>
<img width="611" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/7de41da2-7d2b-4899-8f5d-2b8f5a679d64"><br>    
<figurecaption>
Fig 19 Standard GCC simulation vs Spike simulation output comparison for O1 case of clock_cycle_divider.o (gives same output, successful simulation) <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="463" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/4751f55a-0d7d-403d-904b-e90045b2de49"><br>    
<figurecaption>
Fig 20 Step by Step execution of assembly code for main part of clock_cycle_divider.o for O1 simulation <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="605" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/1a51bf05-3486-470f-98b5-5a0a65f3cadb"><br>    
<figurecaption>
Fig 21 Standard GCC simulation vs Spike simulation output comparison for Ofast case of clock_cycle_divider.o (gives same output, successful simulation) <br>  
</figurecaption>
</figure><br><br>

<figure>
<img width="290" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/afe96e4d-8ff4-4042-8f85-6bedc1d0eef0">
<img width="550" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/adc11c38-daf5-4240-b721-790dbb0d2a31">
<br>    
<figurecaption>
Fig 22 Step by Step execution of assembly code for main part of clock_cycle_divider.o for Ofast simulation and execution of clock divider function <br>  
</figurecaption>
</figure><br><br>

## LAB 4 
The tasks in this lab session are as follows:<br>
&rarr; Identify the RISC-V instruction type (R, I, S, B, U, J).<br>
&rarr; Extract the 32-bit instruction code in the instruction type format.<br>

The RISC-V instructions to identify:<br>

ADD r1, r2, r3 <br>
SUB r3, r1, r2 <br>
AND r2, r1, r3 <br>
OR r8, r2, r5 <br>
XOR r8, r1, r4 <br>
XOR r8, r1, r4 <br>
SLT r10, r2, r4 <br>
ADDI r12, r3, 5 <br>
SW r3, r1, 4 <br>
SRL r16, r11, r2 <br>
BNE r0, r1, 20 <br>
BEQ r0, r0, 15 <br>
LW r13, r11, 2 <br>
SLL r15, r11, r2 <br>


Upload the 32-bit pattern on Github. <br>

Before going through the specific instructions let us first understand the various **RISC-V Instruction types**.<br>
RISC-V Instruction types:<br>
1. R-type: Register-type instructions instructions perform operations where all operands are registers. Format opcode rd, rs1, rs2, where rd is the destination register and rs is the source register.
2. I-type: Immediate-type instructions operate on an immediate value (constant) and a register. Format opcode rd, rs1, imm where imm is an immediate value.
3. S-type: Store-type instructions store a value from the register onto memory. Format: opcode rs2, imm(rs1) where imm is the immediate value added to location rs1 to get the destination register. 
4. SB-type: Conditional branch instructions compare two registers and conditionally jump to a new address if the specified condition is met. Format: opcode rs1, rs2, label jumps to "label" location if conditions for rs1 and rs2 are met.
5. U-type: Upper immediate instructions load a large immediate value into a register. Format: opcode rd, imm operates on the contents of the first 20 bits of immediate value in "imm" and loads it to register rd(destination register).
6. UJ-type: Unconditional jump instructions jump to a new address with relative offset. Format: opcode rd, label operates on the contents of RD and jumps to "label" location.
<br><br>

|Instructions               | 32-bit instruction code              | Function |
| ------------------------- | ------------------------------------ | -------- |
|ADD r1, r2, r3             | 0000000 00011 00010 011 0011         | Opcode: ADD corresponds to the operation code for addition. <br> Destination Register (rd): r1 is the destination register where the result will be stored. <br> Source Register 1 (rs1): r2 is the first source register. <br> Source Register 2 (rs2): r3 is the second source register. <br>|
|SUB r3, r1, r2             | 0100000 00010 00001 011 0011         |Opcode: SUB corresponds to the operation code for subtraction. <br> Destination Register (rd): r3 is the destination register where the result will be stored. <br> Source Register 1 (rs1): r1 is the first source register. <br> Source Register 2 (rs2): r2 is the second source register. <br>|
|AND r2, r1, r3             | 0000000 00011 00001 111 0011         |Opcode: AND corresponds to the operation code for bitwise AND.<br> Destination Register (rd): r2 is the destination register where the result will be stored.<br> Source Register 1 (rs1): r1 is the first source register.<br> Source Register 2 (rs2): r3 is the second source register.<br> |
|OR r8, r2, r5              | 0000000 00101 00010 110 0011         |Opcode: OR corresponds to the operation code for bitwise OR.<br> Destination Register (rd): r8 is the destination register where the result will be stored. <br> Source Register 1 (rs1): r2 is the first source register. <br> Source Register 2 (rs2): r5 is the second source register. <br>
|XOR r8, r1, r4             | 0000000 00100 00001 100 0011         |Opcode: XOR corresponds to the operation code for bitwise XOR (exclusive OR).<br> Destination Register (rd): r8 is the destination register where the result will be stored.<br> Source Register 1 (rs1): r1 is the first source register.<br> Source Register 2 (rs2): r4 is the second source register.
|SLT r10, r2, r4            | 0000000 00100 00010 010 0011         |Opcode: SLT corresponds to the operation code for Set Less Than.<br> Destination Register (rd): r10 is the destination register where the result (1 if rs1 < rs2, else 0) will be stored. <br> Source Register 1 (rs1): r2 is the first source register.<br> Source Register 2 (rs2): r4 is the second source register. <br>
|ADDI r12, r3, 5            | 0000000 00011 01100 000 0011         |Opcode: ADDI corresponds to the operation code for immediate addition.<br> Destination Register (rd): r12 is the destination register where the result will be stored. <br> Source Register (rs1): r3 is the source register containing the value to which the immediate will be added. <br> Immediate Value (imm): 5 is the immediate value to be added to the value in r3.
|SW r3, r1, 4               | 0000000 00011 00001 010 0011         |Opcode: SW corresponds to the operation code for store word. <br> Base Register (rs1): r1 is the base register, which holds the base address where r3's value will be stored. <br> Offset Register (rs2): r3 is the offset register, which holds the value to be stored. <br> Offset Immediate (imm): 4 is the immediate offset added to the base address in r1 to calculate the memory address where r3's value will be stored.
|SRL r16, r11, r2           | 0000000 00010 01011 101 0011         |Opcode: SRL corresponds to the operation code for logical right shift. <br> Destination Register (rd): r16 is the destination register where the result of the shift operation will be stored. <br> Source Register (rs1): r11 is the source register containing the value to be shifted. <br> Shift Amount (rs2): r2 is the register containing the amount by which r11 will be shifted right.
|BNE r0, r1, 20             | 0001010 00001 00000 110 0011         |Opcode: BNE corresponds to the operation code for branch if not equal. <br> Source Register 1 (rs1): r0 is the first source register whose value is compared. <br>Source Register 2 (rs2): r1 is the second source register whose value is compared. <br> Immediate Value (imm): 20 is the immediate value representing the number of instructions to branch forward if the condition is met.
|BEQ r0, r0, 15             | 0000111 00000 00000 110 0011         |Opcode: BEQ corresponds to the operation code for branch if equal. <br> Source Register 1 (rs1): r0 is the first source register whose value is compared. <br> Source Register 2 (rs2): r0 is the second source register whose value is compared. <br> Immediate Value (imm): 15 is the immediate value representing the number of instructions to branch forward if the condition is met.
|LW r13, r11, 2             | 0000000 00010 01011 011 0011         |Opcode: LW corresponds to the operation code for loading a word from memory. <br> Destination Register (rd): r13 is the destination register where the loaded value will be stored. <br> Base Register (rs1): r11 is the base register that holds the base address from where the data will be loaded. <br> Offset Immediate (imm): 2 is the immediate offset added to the base address in r11 to calculate the memory address from where to load the word.
|SLL r15, r11, r2           | 0000000 00010 01011 001 0011         |Opcode: SLL corresponds to the operation code for logical left shift. <br>Destination Register (rd): r15 is the destination register where the result of the shift operation will be stored. <br>Source Register (rs1): r11 is the source register containing the value to be shifted left. <br> Shift Amount (rs2): r2 is the source register containing the amount by which r11 will be shifted left.
<br><br>

## LAB 5

The tasks to be done in Lab 5 are:<br>
&rarr; Use the Verilog netlist and test bench for functional simulation.<br>
&rarr; Upload waveform snapshots for the command.<br>
<br><br>

Ran the below comands to download iverilog and GTKWave: <br>
$   sudo apt get update <br>
$   sudo apt get install iverilog gtkwave <br>

We then clone the repository and access location <br>
$ git clone https://github.com/vinayrayapati/iiitb_rv32i <br>
$ cd iiitb_rv32i <br>

I have copied all the iiitbrv32i data to another folder "verilog_riscv_expt" for this experiment.<br>
To simulate and run verilog code we use the following command: <br>

These are the instructions executed.: <br>
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v <br>
$ ./iiitb_rv32i <br>

The .vcd file is created. This can be used to generate waveforms on GTKWave.<br>

To see the output in GTKWave we use the below command:<br>
$ gtkwave iiitb_rv32i.vcd
<figure>
<img width="259" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/320274bf-7e0e-4d31-802f-5c35d14f3ad5">
<br>
<figurecaption>Fig 22 Instructions executed <br>  </figurecaption>
</figure><br><br>

<figure>
<img width="253" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/1e0dff72-7075-4546-98dd-a06feebcc10f">
<br>
<figurecaption>Fig 23 Basic Instructions <br>  </figurecaption>
</figure><br><br>

<figure>
<img width="754" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/572cbf72-1a60-4279-b904-94fdf25c475b">
<br>
<figurecaption>Fig 24 Output waveform seem in GTKWave <br>  </figurecaption>
</figure><br><br>

In Fig 24, all instructions in Fig 23 have been executed and plotted in waveform.<br><br>
Now we can look at the execution of all institutions separately. <br>
Value of r1 to r17:<br>
REG[1] <= 32'd1;<br>
REG[2] <= 32'd2;<br>
REG[3] <= 32'd3;<br>
REG[4] <= 32'd4;<br>
REG[5] <= 32'd5;<br>
REG[6] <= 32'd6;<br>
REG[7] = 32'd7;<br>
REG[6] = 32'd6;<br>
REG[7] = 32'd7;<br>
REG[8] = 32'd8;<br>
REG[9] = 32'd9;<br>
REG[10] = 32'd10;<br>
REG[11] = 32'd11;<br>
REG[12] = 32'd12;<br>
REG[13] = 32'd13;<br>
REG[14] = 32'd14;<br>
REG[15] = 32'd15;<br>
REG[16] = 32'd16;<br>
REG[17] = 32'd17;<br><br>

The output sequence seen is (signed decimal): 3, -1, 1, 7, 5, 1, 9, 9.<br>
Instruction 1: add r6,r1,r2.(i1)<br>
Addition of value in reg1 and reg 2 and save in reg 6 (1+2 = 3).<br>
Instruction 2: sub r7,r1,r2.(i2)<br>
Difference of value in reg 1 and 2 and save in reg 7 as a signed decimal value (1-2 = -1).<br>
Instruction 3: and r8,r1,r3.(i3)<br>
Bitwise AND of value in reg1 and reg 3 i.e.001(binary) AND 011(binary). The output is 001(binary) i.e. 1(decimal).<br>
Instruction 4: or r9,r2,r5.(i4)<br>
Bitwise OR of value in reg 5 and reg 2 i.e. 101(binary) OR 010(binary). The output is 111(binary) i.e. 7(decimal).<br>
Instruction 5: xor r10,r1,r4.(i5)<br>
Bitwise XOR of value in reg 1 and reg 4 i.e. 001(binary) XOR 100(binary). The output is 101(binary) i.e. 5(decimal).<br>
Instruction 6: slt r11,r2,r4.(i6)<br>
This instruction compares values of reg 2 and reg 4, if reg 2< reg 4 then it returns 1 or else 0. Here 2<4 so the value returned is 1.<br> 
Instruction 7: addi r12,r4,5.(i7)<br>
This instruction immediately adds 5 to the data in reg 4. The output is 5 + 4 = 9(signed decimal).<br>
Instruction 8: sw r3,2(r1).(i8)<br>
This instruction adds an offset of 2 to the value in register 1 and stores in the destination register reg 3. So the value (1+2=3) 3 is stored in Reg 3. 
lw r13,r1,2.(i9)<br>
beq r0,r0,15.(i10)<br>
add r14,r2,r2.(i11)<br>

## Lab 6: Clock Cycle Divider
### Overview of a clock cycle divider
This project will show the implementation of a clock cycle divider on a VSDSquadron Mini RISC-V development board. For that we must first see how a clock cycle divider operates. Here is a brief overview of a clock cycle divider.<br>
A clock cycle divider is a digital clock divider circuit. It takes a high-frequency clock signal as input and produces a low-frequency clock signal as output. This low-frequency clock signal can be obtained by dividing the high-frequency clock signal by a factor of 2, 4, 8, etc.<br>

<figure>
<img width="565" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/c1e48c6e-9d80-431b-bed5-949af81cceed">
<br>
<figurecaption>Fig 25 VSDSquadron mini RISC-V development board block diagram <br>  </figurecaption>
</figure><br><br>

The functionality of the clock cycle divider is as follows. The input clock signal (high-frequency) is fed into a counter, which increments on each rising edge. Using this method, we can capture the number of cycles in the input clock signal. Once the number of cycles reaches the desired division factor, we reset the output to zero. This will be implemented on a VSDSquadron Mini RISC-V development board. FIG 25 shows the block diagram of the VSDSquadron mini development board. <br> 
