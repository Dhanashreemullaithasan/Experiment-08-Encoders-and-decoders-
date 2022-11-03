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



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: DHANASHREE M 
RegisterNumber:  212221230048
*/

```
## Encoders :

module ex8(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or (a,d4,d5,d6,d7);
or (b,d2,d3,d6,d7);
or (c,d1,d3,d5,d7);
endmodule

 ## Decoders :
 
module ex8(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0=(~a&~b&~c); 
assign d1=(~a&~b&c);
assign d2=(~a&b&~c);
assign d3=(~a&b&c);
assign d4=(a&~b&~c);
assign d5=(a&~b&c);
assign d6=(a&b&~c);
assign d7=(a&b&c);
endmodule

```
### RTL LOGIC  :

## Encoders :

![rtl ex8](https://user-images.githubusercontent.com/94165415/199721252-8e2a3b5f-67c2-4ea6-a68d-24c9a3f9fbbe.png)

 ## Decoders :

![rtl 2 ex8](https://user-images.githubusercontent.com/94165415/199723920-f1ce0094-b236-47f8-8062-75572952767d.png)


### TIMING DIGRAMS  :

## Encoders :

![wf1 ex8](https://user-images.githubusercontent.com/94165415/199724221-37f712e8-f736-4fa5-aa25-5ac989840c27.png)

![wf2 ex8](https://user-images.githubusercontent.com/94165415/199724261-234649cc-4e94-4356-b973-e07388274b98.png)

![wf3 ex8](https://user-images.githubusercontent.com/94165415/199724155-ddb00074-35be-4776-97be-3f06e514ee33.png)

## Decoders :

![wfs2 ex8](https://user-images.githubusercontent.com/94165415/199724366-848ad38f-4b4f-47d1-90de-cd999cb70abf.png)

### TRUTH TABLE :
## Encoders :

![tt8 2](https://user-images.githubusercontent.com/94165415/199752911-99e8497c-cf0d-409d-a432-a50f03842a04.png)

## Decoders :

![tt8](https://user-images.githubusercontent.com/94165415/199753139-650460c1-8656-4de9-9ce6-105bb5cce626.png)

### RESULTS :

8 to 3 Encoder and 3to8 Decoder has been implemented by using verilog and its outputs are validated.
