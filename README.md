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
<br><br>
<figure>
<img width="389" alt="image" src="https://github.com/SubhroRoy/VSDSquadron_mini_research/assets/169291565/c386fe85-52eb-4916-aded-c7a79a6d8373"><br>
<figurecaption>
Fig 9 Total no of instructions in main for Ofast is 12<br>  
</figurecaption>
</figure><br><br>
