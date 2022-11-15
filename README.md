# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware:
1. PCs.
2. Cyclone II.
3. USB flasher.
## Software:
1.Quartus prime

## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Program:
~~~
Program to implement the given logic function using NAND and NOR gates 
and to verify its operations in quartus using Verilog programming.

Developed by: M G Gautham.

RegisterNumber: 212221230027. 
~~~
## Using NAND:
~~~
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign F= f1&~f2&~f3;
endmodule
~~~
## Using NOR Gate:
~~~
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(F,f4);
endmodule
~~~

## Output:
## RTL:
![image](https://user-images.githubusercontent.com/93427248/200048771-c136cdb9-73a1-446d-82bb-b8fd93415f85.png)
## Timing Diagram:
![image](https://user-images.githubusercontent.com/93427248/200048816-54769f72-84b2-4869-8b18-9c43c4639af7.png)
## Truth Table:
![image](https://user-images.githubusercontent.com/93427248/200048913-f2ad28bc-b281-4e38-bfec-6d8bc929d66b.png)
## Program 2:
## RTL:
![image](https://user-images.githubusercontent.com/93427248/200048996-c6f3a920-a154-45da-b308-fe48fc5bc4c0.png)
## Timing Diagram:
![image](https://user-images.githubusercontent.com/93427248/200049052-74bc178f-0f58-443a-872f-c8c6ef804f57.png)
## Truth Table:
![image](https://user-images.githubusercontent.com/93427248/200049124-712f58d8-a844-479b-9314-c2fea54d917d.png)
## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
