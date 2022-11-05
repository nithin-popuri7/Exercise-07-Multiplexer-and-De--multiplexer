# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure
/* write all the steps invloved */



### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:P.Siva Naga Nithin.
RegisterNumber:212221240037.  

```
## Multiplexer:
```
module mul(I0,I1,I2,I3,S0,S1,Y);
input I0,I1,I2,I3,S0,S1;
output Y;
wire P,Q,R,S,S0c,S1c;
not(S0c,S0);
nor(S1c,S1);
and (P,S0c,S1c,I0);
and(Q,S0c,S1,I1);
and(R,S0,S1c,I2);
and(S,S0,S1,I3);
or(Y,P,Q,R,S);
endmodule
```
### RTL Logic:
<img width="960" alt="mul" src="https://user-images.githubusercontent.com/94154780/200118217-3bb4e5ec-8e49-4635-a08d-9df02e8049b0.png">


### Timing Diagram:
![multd](https://user-images.githubusercontent.com/94154780/200118205-c39ecbf2-3878-4717-a08a-5e602537b79d.jpeg)

![multd1](https://user-images.githubusercontent.com/94154780/200118208-87b76124-dbfc-4937-8917-704785dc8c93.jpeg)

![multd2](https://user-images.githubusercontent.com/94154780/200118434-35c7adcb-89e0-4ae7-aa5f-9e5b6d4f0df1.jpeg)

![multd3](https://user-images.githubusercontent.com/94154780/200118438-34b6a2b8-074c-40d8-9aae-ba0271cb3650.jpeg)

## TruthTable:

![mul tt](https://user-images.githubusercontent.com/94154780/200118445-e25b5794-18bc-4e93-a8f4-92756199d732.png)




### Demultiplexer:
```
module demul(Y0,Y1,Y2,Y3,S0,S1,I);![multd](https://user-images.githubusercontent.com/94154780/200118202-d1a9446b-98ec-460b-909e-d80e0820d03e.jpeg)

input I,S0,S1;
output Y0,Y1,Y2,Y3;
wire S0c,S1c;
not(S0c,S0);
nor(S1c,S1);
and (Y0,I,S0c,S1c);
and(Y1,I,S0c,S1);
and(Y2,I,S0,S1c);
and(Y3,I,S0,S1);
endmodule
```



### RTL LOGIC:

<img width="750" alt="demul1" src="https://user-images.githubusercontent.com/94154780/200119191-e944d001-fcc4-42d1-bf02-0b0553e656c6.png">



### TIMING DIGRAM:

![demul td](https://user-images.githubusercontent.com/94154780/200118972-f7ae30d0-af6b-4df5-9f9f-f5ea3e16baac.png)

### TRUTH TABLE:
![demul tt](https://user-images.githubusercontent.com/94154780/200118992-14092433-c8d9-4481-b42e-4b3cbfc3fc96.png)


### RESULTS:
Hence 4x1 Multiplexer and 1x4 Demultiplexer is been implemented and verified using verilog programming and its output are validated.
