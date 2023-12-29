NAME:GOWTHAM ADITYA R<br>
REFERENCE NUMBER:212223050018

# Experiment--04-Implementation of Half subtractor and Full subtractor circuit
# AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

# Equipments Required:
 Hardware – PCs, Cyclone II , USB flasher
 Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.


# Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.

![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/33060f4e-63a7-4791-a02b-b38db741e33a)

Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

# Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/d041ec81-8a3b-4422-a3e0-420ae4c7be68)

Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

# Procedure:
# A.  Half Subtractor:
1. A half subtractor is a combinational circuit that performs the subtraction of two single-bit numbers and produces two outputs: the difference and the borrow.
2. Let's consider two single-bit inputs A and B.
3. Difference (Diff): This output represents the result of the subtraction A - B and is obtained by performing an XOR operation on inputs A and B.
4. Borrow (Borrow): This output indicates whether a borrow is required for the subtraction and is obtained by performing an AND operation between the complement of A and B.
# B. Full Subtractor:
1. A full subtractor is a combinational circuit that subtracts three single-bit inputs: A, B, and a Borrow-In (Bin), and produces two outputs: the difference and a Borrow-Out (Bout) to the next subtractor in a sequence.
2. Difference (Diff): This output represents the result of the subtraction A - B - Bin.
3. Borrow-Out (Bout): This output indicates whether a borrow is required for the subtraction and will be used in further subtractors.
4. A full subtractor is typically constructed using two half subtractors. The Borrow-Out of the first half subtractor is used as an input Borrow-In for the second half subtractor. The outputs of the half subtractors are combined to generate the final Difference and Borrow-Out.

# Program:

HALFSUBTRACTOR:
module halfsubtractor(a,b,diff,borrow);
input a,b;
output diff,borrow;
assign diff=a^b;
assign borrow=~a&b;
endmodule
FULLSUBTRACTOR:
module fullsubtractor(a,b,c,diff,borrow);
input a,b,c;
output diff,borrow;
assign diff=a^b^c;
assign borrow=~a&b|c&~(a^b);
endmodule

#  RTL realization:
## Half Subractor

![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/c269aa73-fab3-4576-bae3-f25a73273fa8)

# Full Subractor

![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/970f38dc-ded8-44d6-8323-bd3342d1a19c)

# Truth Table:
## Half subractor
![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/9496255f-16a9-4c2c-af0b-7bba17f52627)

# Full subractor
![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/e5a4c8d0-b7c2-4644-be26-5a2d93db1945)

# Timing diagram :
# Half subractor
![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/4b1e3fa5-e81b-46ac-bb77-9095473c9059)

# Full subractor
![image](https://github.com/gowtham0777/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/152005396/b44edace-8717-41dd-894c-d8587c8ecab1)

# Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
