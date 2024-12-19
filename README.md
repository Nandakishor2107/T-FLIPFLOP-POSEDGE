# T-FLIPFLOP-POSEDGE

**AIM:**

To implement  T flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

The T Flip-Flop (Toggle Flip-Flop) is a sequential circuit that toggles its output state on every clock pulse when the toggle input (T) is high. It is derived from the JK Flip-Flop by tying the J and K inputs together.

**T Flip-Flop**

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/458a68fe-2d08-4a9d-ac4f-7ae0480ce0bd)

 
This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

![image](https://github.com/naavaneetha/T-FLIPFLOP-POSEDGE/assets/154305477/cdd7fb32-539f-4b66-bb8d-f305a153c886)

 
From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

**Procedure**

Step1: Define the specifications and initialize the design.
Step2: Declare the name of the entity and architecture by using VHDL source code.
Step3: Write the source code in VERILOG.
Step4: Check the syntax and debug the errors if found, obtain the synthesis report.
Step5: Verify the output by simulating the source code.
Step6: Write all possible combinations of input using the test bench.
Step7: Obtain the place and route report.


**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming. 

```
module tff(t, clk, rst, q, qbar);
 input t;
 input clk;
 input rst;
 output q;
 output qbar;
reg q,qbar;
always @ (posedge(clk) or posedge(rst)) begin
if(rst==1'b1) begin
q= 1'b0;qbar= 1'b1;
end
else if (t==1'b0)
begin
q=q; qbar=qbar;
end
else
begin
q=~q; qbar=~qbar;
end
end
endmodule

```
Developed by: Nanda Kishor S P
RegisterNumber: 24011485


**RTL LOGIC FOR FLIPFLOPS**

![Screenshot (106)](https://github.com/user-attachments/assets/8e34fa56-88cb-4872-8c12-f5e09cfb9c7f)


**TIMING DIGRAMS FOR FLIP FLOPS**

 ![Screenshot (107)](https://github.com/user-attachments/assets/a3271920-9f0c-427a-86c2-0e822b0af0f0)


**RESULTS**

The T Flip-Flop was successfully implemented using Verilog, and its functionality was validated through simulation. The simulation results matched the expected functional behavior as described in the truth table.
