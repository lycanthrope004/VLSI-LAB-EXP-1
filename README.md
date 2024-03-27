![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/e451a92d-3774-4fa1-b353-4e64ba9454da)# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
#1:-

FULL_ADDER:-

Code:
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
```

OUTPUT:-

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/f1510986-0a02-4648-9216-80b1b76877b6)

Elobrated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/c90832c7-bec0-406b-8397-de4c9490f40c)

----------------------------------------------------------------------------------------------------------------------------------------------------------------

#2:-

FULL_SUBTRACTOR:-

Code:
```
// fullsubtractor using gate level modeling
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```
OUTPUT:-

Simulation:

![WhatsApp Image 2024-03-25 at 11 44 17_ad1865f2](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/f9c63805-909a-4005-93a2-066e35224687)

Eaborated Design:

![WhatsApp Image 2024-03-25 at 11 47 47_b6e7c75f](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/72c0bbaf-c51a-43d4-a2b6-c55c73245459)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
#3:-

HALF_ADDER:-

Code:
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
OUTPUT:-

Simulation:
![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/bcea7491-2d17-48c0-bba6-13dee70dd116)

Elaborated Design:
![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/4d5911a8-3adb-4bb5-9df1-77511b778011)

------------------------------------------------------------------------------------------------------------------------------------------------------------------
#4
HALF_SUBTRACTOR:-
 Code:
 ```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule

```

OUTPUT:-

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/4f826bba-c803-46f4-aa12-51a6020a1d02)

Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/1646f000-56dc-4944-80c5-dcd15e35ae08)

------------------------------------------------------------------------------------------------------------------------------------------------------------------
#5
LOGIC_GATES:
 Code:
 ```

```
RESULT:

