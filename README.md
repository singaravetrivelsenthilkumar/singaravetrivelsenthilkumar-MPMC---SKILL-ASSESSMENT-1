# Sum of 5 Numbers Stored Sequentially in Memory

## AIM:
To Write an assembly language program in 8051 to calculate the sum of 5 numbers stored sequentially in memory and store the result in a another memory location.

## APPARATUS REQUIRED:
1.Keil µVision Software / 8051 Simulator

2.Personal Computer

## ALGORITHM:
1.Start the program.

2.Load the starting address of the numbers into Register R0 (e.g., 30H).

3.Load the counter register R2 with the total number of elements (05H).

4.Clear the accumulator A to start summation from zero.

5.Add the value pointed to by R0 to the accumulator using indirect addressing (ADD A, @R0).

6.Increment R0 to point to the next number in memory.

7.Decrement the counter R2 and repeat the addition until all 5 numbers are added.

8.Store the final sum in memory location 35H

9.Check for carry (overflow).
``
      *-If carry = 1, store 01H in memory location 36H to indicate overflow.
      *-If carry = 0, store 00H in memory location 36H to indicate no overflow.
``

10.Stop program execution.

11.End the program.


## PROGRAM:
```
ORG 0000H          
MOV R0, #30H       
MOV R2, #05H       
CLR A              
BACK: ADD A, @R0   
INC R0             
DJNZ R2, BACK     
MOV 35H, A        
JNC DONE          
MOV 36H, #01H      
SJMP STOP          
DONE:
MOV 36H, #00H      
STOP:
SJMP STOP         
END                

```

## OUTPUT:


<img width="1918" height="1080" alt="image" src="https://github.com/user-attachments/assets/d0998d78-9948-4e40-8490-9c38191012d4" />


## RESULT:
Thus, an Assembly Language Program to calculate the sum of 5 numbers stored sequentially in memory and store the result in another memory location was written, assembled, and verified successfully using the 8051 simulator.
