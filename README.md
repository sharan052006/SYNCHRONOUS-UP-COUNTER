### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:sharan I
RegisterNumber:24010956
```
module ex11(clk, rst, q);
 input clk;
 input rst;
 output [3:0]q;
reg [3:0]q;
reg [3:0]x=0;
always @ (posedge(clk) or posedge(rst))
begin
if (rst==1'b1)
begin
q=4'b0;
end
else
begin
x=x+1'b1;
end
q=x;
end
endmodule

```
*/

**RTL LOGIC UP COUNTER**

![ex-11-d](https://github.com/user-attachments/assets/bd883f46-4765-433f-8d59-114cdfee51ca)



**TIMING DIAGRAM FOR IP COUNTER**
![ex-11-w](https://github.com/user-attachments/assets/9ef94f92-93b7-4494-8cc6-8b7b8c46d375)


**TRUTH TABLE**
![WhatsApp Image 2024-12-20 at 14 36 12_5b58a721](https://github.com/user-attachments/assets/8655c78f-30d8-4c86-af3a-9864eabbd5cb)

**RESULTS**
 4 bit synchronous up counter is implemented and their functionality is validated
