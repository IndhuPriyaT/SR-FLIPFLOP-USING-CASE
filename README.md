# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

Type the program in Quartus software.

Compile and run the program.

Generate the RTL schematic and save the logic diagram.

Create nodes for inputs and outputs to generate the timing diagram.

For different input combinations generate the timing diagram.

**PROGRAM**
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: Indhu Priya.T RegisterNumber 24007533:
*/
```
```
module sr(q, q_bar, s,r, clk, reset);
  input s,r,clk, reset;
  output reg q;
  output q_bar;
  assign q_bar = ~q;
    always@(posedge clk) begin // for synchronous reset
    if(!reset)       q <= 0;
    else 
  begin				q <= 1;
	
		case({s,r})    
	     2'b00: q <= q;    // No change
        2'b01: q <= 1'b0; // Write logic for reset
        2'b10: q <= 1'b1; // Write logic for set
        2'b11: q <= 1'bx; // Write logic for Invalid state
      endcase
    end
  end
  //assign q_bar = ~q;
endmodule 
```
**RTL LOGIC FOR FLIPFLOPS**
![Screenshot (57)](https://github.com/user-attachments/assets/f7eee971-7b41-4a10-97a5-e56facf104c9)


**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot (58)](https://github.com/user-attachments/assets/1f805018-b767-420c-9ee7-ba488e452e24)


**RESULTS**
Hence,The Program for flipflops and its truthtable in quartus using verilog programming is verified.
