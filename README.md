# Experiment--02-Implementation-of-combinational-logic-using-universal-gates
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

## Procedure
## Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: JAYASRI DODDA 
RegisterNumber: 212222240028
```

## Program 1:
```
module combo1(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign f= f1&~f2&~f3;
endmodule
```
## Program 2:
```
module combo2(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(f,f4);
endmodule
```

## RTL realization

## Output:

## USING NAND GATE

## RTL:
![ss program 1](https://user-images.githubusercontent.com/123259278/229273867-a6a7fe56-e46f-4bf2-8c3b-708fa530cafd.png)
## Timing Diagram:
![TDP 1](https://user-images.githubusercontent.com/123259278/229274238-24e7a41d-3320-429c-b643-23221401db2b.png)
## Truth Table:
![OUT PRO 1](https://user-images.githubusercontent.com/123259278/229274262-ab059a08-5054-4d1e-b49f-170b4253feea.png)

## USING NOR

## RTL
![ss  program 2](https://user-images.githubusercontent.com/123259278/229273887-2c6ca85d-7b4c-4d2f-a987-f2721ef7e3d2.png)
## Timing Diagram:
![TDP 2](https://user-images.githubusercontent.com/123259278/229274432-3ff97410-29d5-4d62-9200-dd84935ae1e4.png)
## Truth table:
![OUT PRO 2](https://user-images.githubusercontent.com/123259278/229274462-a468a3eb-04e6-4182-b640-d927b9650938.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
