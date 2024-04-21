# 4BIT_RIPPLECOUNTER
# Aim:
To stimulate and synthesis 4bit Ripple counter using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.
# Circuit Diagram
![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/324dfe68-4985-401a-9f0c-7df90b08265e)
# T- Flip Flop
![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/2c234c0e-2c48-4688-920b-a43ea6582112)
# D - Flip flop
![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/7fb0da71-700b-4a53-b2c1-2afa523e89c4)
# Program:
```
module ripple_carry_counter(q, clk, reset);
output [3:0] q;
input clk, reset;
T_FF tff0(q[0], clk, reset);
T_FF tff1(q[1], q[0], reset);
T_FF tff2(q[2], q[1], reset);
T_FF tff3(q[3], q[2], reset);
endmodule
module T_FF(q, clk, reset);
output q;
input clk, reset;
wire d;
D_FF dff0(q, d, clk, reset);
not n1(d, q);
endmodule
module D_FF(q, d, clk, reset);
output q;
input d, clk, reset;
reg q;
always @(posedge reset or negedge clk)
if (reset)
q = 1'b0;
else
q = d;
endmodule
```

# Output:
![image](https://github.com/trishasailendran/4BIT_RIPPLECOUNTER/assets/87655678/cfda3369-85d9-4655-83a8-3c4f864d3b5b)
# Result:
Thus the verilog program for 4bit Ripple Counter has been simulated and verified successfully.
