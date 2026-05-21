# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**
```
1. Create the JK flip-flop Verilog/VHDL design and compile the project in Quartus.
2. Open the Simulation Waveform Editor and create a new .vwf file.
3. Insert the input and output signals (clk, j, k, q, qbar) using Node Finder.
4. Generate the clock signal and draw the required J and K input waveforms.
5. Run the functional simulation and observe the output waveforms of q and qbar.
```

**PROGRAM**
```
module JKFLIP(j,k,clk,q,qbar);

input j,k,clk;

output reg q,qbar;

initial
begin
    q = 1'b0;
    qbar = 1'b1;
end

always @(posedge clk)
begin
    q <= (j & ~q) | (~k & q);
    qbar <= ~q;
end

endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
<img width="1643" height="873" alt="{D66DFB81-F88D-480E-8737-09B782BB90C5}" src="https://github.com/user-attachments/assets/9b8359a8-4f01-4e41-94ac-224bdbe590ef" />

**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1920" height="975" alt="{946F4C60-F8A7-4490-A229-8F840DF36029}" src="https://github.com/user-attachments/assets/8ad4874a-a317-4043-90c9-e143ad622ad6" />

**RESULTS** : 
Thus, JK flipflop is implemented using Quartus Prime Software.

