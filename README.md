# VLSI-LAB-EXPERIMENTS

AIM:

To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED:

Xilinx 14.7 Spartan6 FPGA

PROCEDURE: 

STEP:1 Start the Xilinx navigator, Select and Name the New project. 

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 

STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained.

STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.

STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA

STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

```
    DEVELOPED BY: SUBASHINI.S

    REGISTERED NUMBER: 212222060256
```   
LOGIC DIAGRAM:

Logic Gates:

 ![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)

Verilog Code:
```
      module gate(a,b,w1,w2,w3,w4,w5,w6,w7);
      input a,b;
      output w1,w2,w3,w4,w5,w6,w7;
      and g1 (w1,a,b);
      or g2 (w2,a,b);
      not g3 (w3,a);
      xor g4 (w4,a,b);
      xnor g5 (w5,a,b);
      nand g6 (w6,a,b);
      nor g7 (w7,a,b);
      endmodule
 ```
OUTPUT:

![WhatsApp Image 2024-04-21 at 13 13 36_d14c1395](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-1/assets/153823077/6e0da202-e7ed-4e5e-aee2-5b8b6ddf6143)

LOGIC DIAGRAM:

Half Adder:

  ![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)

Verilog Code:

```
     module halfadder( a,b,sum,carry);
     input a,b;
     output sum,carry;
     xor g1(sum,a,b);
     and g2(carry,a,b);
     endmodule
```
OUTPUT:

  ![WhatsApp Image 2024-04-21 at 13 22 26_803f5d1e](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-1/assets/153823077/392fb0b2-595c-4099-a1cd-c6a446093685)
  
LOGIC DIAGRAM:

  Full adder:

   ![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)

Verilog Code:
```
       module fulladder(a,b,cin,sum,carry);
       input a,b,cin;
       output sum,carry;
       wire w1,w2,w3;
       xor g1(w1,a,b);
       xor g2(sum,w1,cin);
       and g3(w2,w1,cin);
       and  g4(w3,a,b);
       or g5(carry,w2,w3);
       endmodule
```
OUTPUT:

   ![WhatsApp Image 2024-04-21 at 20 23 36_03484310](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-1/assets/153823077/4d96b6ff-2572-4cf2-adef-001b6cf38a49)
   
LOGIC DIAGRAM:

Half Subtractor:

 ![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)


Verilog code:

```
       module hs(a,b,difference,borrow);
       input a,b;
       output difference,borrow;
       wire w;
       xor g1(difference,a,b);
       and g2(borrow,w,b);
       not g3(w,a);
       endmodule
```
OUTPUT:

 ![WhatsApp Image 2024-04-21 at 20 25 06_4d67aa4c](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-1/assets/153823077/e20c90aa-d755-41a9-9995-1812518cf360)
 
LOGIC DIAGRAM:

Full Subtractor:

  ![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)


Verilog Code:

```
 module fs(a,b,c,diff,borrow);
    input a,b,c;
    output diff,borrow;
    wire w1,w2,w3,w4,w5;
    xor g1(w3,a,b);
    xor g2(diff,c,w3);
    and g3(w2,b,w1);
    and g4(w5,w4,c);
    not g5(w1,a);
    not g6(w4,w3);
    nor g7(borrow,w5,w2);
endmodule
```
OUTPUT:

  ![WhatsApp Image 2024-04-21 at 20 25 44_0c0a2a7c](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-1/assets/153823077/91ce7a66-e2ab-4bff-b316-15cc421f0ee2)

LOGIC DIAGRAM:

8 Bit Ripple Carry Adder

   ![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)
   
 Verilog Code:
 
```
  module fa(a,b,cin,sum,carry);
       input a,b,cin;
       output sum,carry;
       wire w1,w2,w3;
       xor g1(w1,a,b);
       and g2(w3,a,b);
       xor g3(sum,w1,cin);
       and g4(w2,w1,cin);
       or g5(carry,w2,w3);
 endmodule
 
 module rca(a,b,cin,sum,cout);
        input[3:0]a,b;
        input cin;
        output [3:0]sum;
        output cout;
        wire w1,w2,w3;
      fa g1(.a(a[0]),
            .b(b[0]),
            .cin(cin),
            .sum(sum[0]),
            .carry(c1)
            );
       fa g2(.a(a[1]),
             .b(b[1]),
             .cin(c1),
             .sum(sum[1]),
             .carry(c2)
             );
       fa g3(.a(a[2]),
             .b(b[2]),
             .cin(c2),
             .sum(sum[2]),
             .carry(c3)
             );
        fa g4(.a(a[3]),
              .b(b[2]),
              .cin(c3),
              .sum(sum[3]),
              .carry(cout)
              );
 endmodule
```
OUTPUT:

   ![WhatsApp Image 2024-04-21 at 20 28 06_3b732605](https://github.com/SUBASHINIS28/VLSI-LAB-EXP-1/assets/153823077/26baa473-ecc7-402e-85d0-6bfae894f264)
   

RESULT:

  Hence, the stimulation and synthesis of a Logic Gates,Adders and Subtractor was run successfully by using Xilinx ISE.



