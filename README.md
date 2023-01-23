# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure 
## Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: SWETHA P
RegisterNumber: 22008542 

### COMBINATION 1

module combin(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(~c & b & a);
assign q=(~d & c & c);
assign r=(c & ~b & a);
assign f=(~(~p & ~q & ~r));
endmodule

### COMBINATION 2

module combin2(a,b,c,d,f);
input a,b,c,d;
output f;
assign p=(c & ~b & a);
assign q=(d & ~c & a);
assign r=(c & ~b & a);
assign f=((p | q & |r));
endmodule
```

## output:

### RTL realization
### COMBINATION 1
![COMB1RTL_page-0001](https://user-images.githubusercontent.com/120623583/214080316-0ad1ee7c-1bab-45f1-8c8f-df15c8f50079.jpg)

##3 TIMING DIAGRAM
![COMB1SIMULATION_page-0001](https://user-images.githubusercontent.com/120623583/214081088-da06b94d-0f6c-4806-82c6-7f44dcf02101.jpg)

### COMBINATION 2
### RTL realization
![COMB2RTL_page-0001](https://user-images.githubusercontent.com/120623583/214081498-a0d6aa3c-986d-4f1e-b241-653271ca0208.jpg)

### Timing diagram
![comb2SIMULATION_page-0001](https://user-images.githubusercontent.com/120623583/214081747-d5a9832d-bd82-4bda-8c79-40d5662391b6.jpg)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
