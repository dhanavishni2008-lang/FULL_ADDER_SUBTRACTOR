# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

1.Connect input A directly to the full adder.

2.Pass input B through an XOR gate with the mode control M to produce modified input:
        𝐵′=𝐵⊕𝑀

3.Use M as the carry-in (Cin) of the full adder.

4.Connect A, B', and Cin = M to the full adder.

5.Observe the outputs:

   *Sum (S) → gives addition or subtraction result.

   *Cout → acts as carry (for addition) or borrow (for subtraction).

6.Set M = 0 for addition, and M = 1 for subtraction, and note the outputs.

**Program:**

FULL ADDER

module full_adder (
    input  wire a, b, cin,   // Inputs
    output wire sum, carry   // Outputs
);

    // Logic equations
    assign sum   = a ^ b ^ cin;                  // XOR for sum
    assign carry = (a & b) | (b & cin) | (a & cin); // Majority function for carry

endmodule

FULL SUBTRACTOR

module full_subtractor (
    input  wire a, b, bin,       // Inputs
    output wire diff, borrow     // Outputs
);

    // Logic equations
    assign diff   = a ^ b ^ bin;                  // Difference
    assign borrow = (~a & b) | (~(a ^ b) & bin);  // Borrow logic

endmodule

 Developed by:DHANAVISHNI M
 RegisterNumber:25016333

**RTL Schematic**

FULL ADDER
<img width="1920" height="1080" alt="Screenshot (92)" src="https://github.com/user-attachments/assets/cc487562-fbd4-4b50-b847-ce33bc912625" />

FULL SUBTRACTOR
<img width="1920" height="1080" alt="Screenshot (93)" src="https://github.com/user-attachments/assets/c73a888d-6285-4b0b-8573-a34a166ae475" />



**Output Timing Waveform**

FULL ADDER
<img width="1920" height="1080" alt="Screenshot (96)" src="https://github.com/user-attachments/assets/9cd8e86c-b181-4172-8a6d-85fe0d9d9d02" />

FULL SUBTRACTOR
<img width="1920" height="1080" alt="Screenshot (97)" src="https://github.com/user-attachments/assets/0a35e7dd-1d1d-473d-b94d-2e82fb758479" />



**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



