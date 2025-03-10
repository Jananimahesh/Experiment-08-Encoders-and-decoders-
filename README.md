# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
/* write all the steps invloved */
1.Open Quartus II and select new project and choose the file location. 
2.Module Declaration. Module should have the file name.
3.Input-Output Delecaration.
4.Use assign to define the functionality of logic circuits.
5.At the end give endmodule.
6.Run the program and choose RTL viewer to get RTL realization



### PROGRAM

ENCODER

module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

DECODER

module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule


Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: janani.m
RegisterNumber: 22006734 
*/
### RTL LOGIC  

RTL REALIZATION FOR ENCODER

![image](https://user-images.githubusercontent.com/119432417/214761247-80b79cca-95f6-4154-aa68-118d5b8ee388.png)


RTL REALIZATION FOR DECODER

![image](https://user-images.githubusercontent.com/119432417/214761563-e974f820-69e4-4b81-8edc-deed1e4d342c.png)









### TIMING DIGRAMS 

TIMING DIAGRAM FOR ENCODER

![image](https://user-images.githubusercontent.com/119432417/214761608-5228a68a-07d5-484a-8c8d-2f9beec0bb9e.png)

TIMING DIAGRAM FOR DECODER

![image](https://user-images.githubusercontent.com/119432417/214761684-f0ba19eb-5c89-4cf9-a9c4-3b0c45463165.png)







### TRUTH TABLE

TRUTH TABLE FOR ENCODER

![image](https://user-images.githubusercontent.com/119432417/214761778-14ac4f09-9914-431d-b9d8-eb2a5b840de5.png)

TRUTH TABLE FOR DECODER

![image](https://user-images.githubusercontent.com/119432417/214761879-ada5b056-9095-4aa0-8b81-94afc41ac7d2.png)








### RESULTS 

Thus, 8 to 3 Encoder and 3 to 8 Decoder is implemented using verilog and its outputs is validated.
