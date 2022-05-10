# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
```
1.Use module projname(input,output) to start the Verilog programmming.
2.Assign inputs and outputs using the word input and output respectively.
3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4.Use each output to represnt onre for differnce and the other for borrow.
5.End the verilog program using keyword endmodule.
```




### Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Jeswanth
RegisterNumber: 212221230042

HALF SUBTRACTOR:
module halfsub(a,b,diff,borrow);
input a,b;
output diff,borrow;
wire x;
xor(diff,a,b);
not(x,a);
and(borrow,x,b);
endmodule

FULL SUBTRACTOR:
module fullsub(a,b,c,diff,borrow);
input a,b,c;
output borrow,diff;
wire an,q,r,s,t,cn,u;
not(an,a);
not(cn,c);
xor(q,a,b);
xor(diff,q,c);
and(s,a,b);
and(t,q,cn);
or(borrow,s,t);
endmodule 
```

## Output:
Logic symbol & Truthtable
### Half subtractor truth table:
![ex3t](https://user-images.githubusercontent.com/94154683/165960966-add01287-f6c2-40f8-89a0-ecbb01d2c401.PNG)

### Full subtractor truth table:
![EX3TT](https://user-images.githubusercontent.com/94154683/165961092-49a612d3-6757-4a01-a496-a7fe1ebc7cd0.PNG)


RTL realization
Output:
## RTL
### Half subtractor

![ex_3](https://user-images.githubusercontent.com/94154683/165957424-ebb2ec3d-3093-4093-8687-b9d7a29e8c2b.PNG)

### Full subtractor:
![ex3fulladd](https://user-images.githubusercontent.com/94154683/165957561-28454d9c-2339-4b0c-aeb6-5ca8149e9500.PNG)

## Timing Diagram
### Half subtractor:
![wave_ex3](https://user-images.githubusercontent.com/94154683/165957699-9a6c62b3-3236-43d0-8785-c1879b69059f.PNG)

### Full subtractor:
![33](https://user-images.githubusercontent.com/94154683/166411157-33256604-b48e-4ae4-b4b8-b38277444f91.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
