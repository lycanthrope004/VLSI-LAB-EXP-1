# VLSI-LAB-EXPERIMENTS
**AIM:** To simulate and synthesis Logic Gates,Adders and Subtractor using Vivadoo Software

**APPARATUS REQUIRED:**  Vivado™ ML 2023.2

**PROCEDURE:** 

1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

**Logic Diagram :**



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

**EXPERIMENTS :**

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

Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/c90832c7-bec0-406b-8397-de4c9490f40c)


#2:-

FULL_SUBTRACTOR:-

 Code:
```
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

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/485159c7-ecbe-4474-ad8a-0a40b4370a91)


Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/c804b8b9-4e92-4a8d-971f-758349ebf605)


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

#5
LOGIC_GATES:-

Code:
 ```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```

OUTPUT:

Simulation:
![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/8ea068c7-4870-4224-9def-3b441ca500e8)

Elaborated Design:
![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/51299302-0ebd-4a71-9047-070d13ce30f8)

#6

RIPPLE_CARRY_Adder(4-BIT):-

Code:
```
module rippe_adder(S, Cout, X, Y,Cin);
input [3:0] X, Y;// Two 4-bit inputs
input Cin;
output [3:0] S;
output Cout;
wire wl, w2, w3;

fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], Cout,X[3], Y[3], w3);
endmodule
module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
//Structural code for one bit full adder 
xor G1(wl, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or  G5(Co, w2, w3);
endmodule
```

OUTPUT:-

Simulation:
![WhatsApp Image 2024-03-25 at 11 08 55_68546aae](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/5693d20b-dd92-4623-948c-f34d75e15bac)

Elaborated Design:
![WhatsApp Image 2024-03-25 at 11 08 55_25ab378b](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/2fd66ce3-4067-41df-9265-652ac4e07886)

#7

RIPPLE_CARRY_ADDER(8-BIT):-

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
module rippe_adder(S,Cout,X,Y,Cin);
input [7:0] X,Y;
input Cin;
output [7:0] S;
output Cout;
wire w1,w2,w3,w4,w5,w6,w7;
fulladder u1(S[0],w1,X[0],Y[0],Cin);
fulladder u2(S[1],w2,X[1],Y[1],w1);
fulladder u3(S[2],w3,X[2],Y[2],w2);
fulladder u4(S[3],w4,X[3],Y[3],w3);
fulladder u5(S[4],w5,X[4],Y[4],w4);
fulladder u6(S[5],w6,X[5],Y[5],w5);
fulladder u7(S[6],w7,X[6],Y[6],w6);
fulladder u8(S[7],Cout,X[7],Y[7],w7);
endmodule

module fulladder(S,CO,X,Y,Ci);
input X,Y,Ci;
output S,CO;
wire w1,w2,w3;
xor G1(w1,X,Y);
xor G2(S,w1,Ci);
and G3(w2,X,Ci);
and G4(w3,X,Y);
or G5(CO,w3,w3);
endmodule 
```
OUTPUT:-

Simulation:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/8f2236eb-8ecf-43ca-afe7-38859087f512)


Elaborated Design:

![image](https://github.com/lycanthrope004/VLSI-LAB-EXP-1/assets/121667830/012dabdf-2bca-4a1f-b710-9abece39c8fa)



**RESULT :**
The simulation and synthesis of Logic Gates, Adders and Subtractor using Vivadoo Software are successfully completed
