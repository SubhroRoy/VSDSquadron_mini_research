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



