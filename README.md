# 3-bit-asynchronous-upcounter
### Aim:
      To design a 3-bit-asynchronous upcounter circuit and verify its truth table using Quartus
using verify programming.
      
### Equipments Required:
     
      Hardware-PCs, Cyclone II, USB flasher
      
      software-Quartus prime
      
      
### Theory:
       A counter is a register capable of counting number of clock pulse arriving at its clock input.Counter represents the number of 
clock pulses arrived. A specified sequence of states appears as counter output. This is the main difference between
a register and a counter. There are two types of counter, synchronous and asynchronous. In synchronous common clock is 
given to all flip flop and in asynchronous first flip flop is clocked by external pulse and then each successive
flip flop is clocked by Q or Q output of previous stage. A soon the clock of second stage is triggered by output of first stage.
Because of inherent propagation delay time  all flip flops are not activated at same time
which results in asynchronous operation.  

  
![download (3)](https://user-images.githubusercontent.com/122762773/214794176-f4b492d1-0d9a-4c96-a462-3ce18816eecf.png)

      Figure 1: 3 bit asynchronous upcounter circuit
      
      
### Procedure:
  
  
   1. create a model of 3 bit asynchronous upcounter circuit.
   2. Get the inputs and outputs for 3 bit asynchronous upcounter circuit.
   3. Perform the RTL logic for the circuit.
   4. Now get the waveform diagram for the 3 bit asynchronous circuit.
   
   
   
### Program:


```
module counter( clk, count );
input clk;
output[3:0] count;

reg[3:0] count;
wire clk;

initial
    count = 4'b0;

always @( negedge clk )
    count[0] <= ~count[0];

always @( negedge count[0] )
    count[1] <= ~count[1];

always @( negedge count[1] )
    count[2] <= ~count[2];

always @( negedge count[2] )
    count[3] <= ~count[3];

endmodule
```


Program to design a 3 bit asynchronous circuit and verify its 
truth table in Quartus using  verilog programming.

```
Developed by: Gopika.R
Register Number: 22009266
```

### OUTPUT:


### RTL logic: 

![Screenshot (96)](https://user-images.githubusercontent.com/122762773/214798658-817e6c70-9aca-4313-8c18-45bfe88cedcb.png)


Timing Diagram:


![Screenshot (97)](https://user-images.githubusercontent.com/122762773/214799564-f19ba9ea-5124-4186-8a74-de684cc33b9e.png)


Truth table:


![table-5-6-2](https://user-images.githubusercontent.com/122762773/214797834-7ec3a8a6-b151-4895-8cd0-b126a0ff3834.gif)


Result:
      Thus the 3 bit asychronous up counter is verified using a Verilog  programming.
