# VSDSquadron_mini_research
VSDSquadron mini board research 
## Task 1 : Write a C-Program and compile using RISCV compiler and Disassemble.
### Labwork a) Write a C-program that will compute the sum from 1 to n.
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
### Labwork b) Compile the written C-program using RiscV GCC compiler and disassemble.
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

## Task2: Write a simple C- Program for Clock Cycle Divider: Crafting a Digital Clock Divider Circuit and compile using RISC V GCC compiler

The project I am working on is **Clock Cycle Divider**. <br>
Below is a sample C-Program I execute as part of Task 2. I have used AI tools to generate this code. <br>
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

## Task3: Spike Simulation

<figure>
<img width="502" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/7fa997d1-8058-40c2-8ca3-9d0db6280522"><br>    
<figurecaption>
Fig 13  <br>  
</figurecaption>
</figure><br><br>
