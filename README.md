# Experiment-08- Encoders-and-decoders 

### AIM: 

To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs

### HARDWARE REQUIRED:  

PC, Cyclone II , USB flasher

### SOFTWARE REQUIRED:  

 Quartus prime

### THEORY :

## Encoders:

Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders – An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![](/enc1.png)

Figure -01 3 to 8 Encoder

Implementation –

X = D4 + D5 + D6 + D7 Y = D2 +D3 + D6 + D7 Z = D1 + D3 + D5 + D7  Hence, the encoder can be realised with OR gates as follows:

![](/enc2.png)

## Figure -02 3 to 8 Encoder implenentation 

### Decoders :

A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder. Implementation – D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’  Similarly,

D1 = X’ Y’ Z D2 = X’ Y Z’ D3 = X’ Y Z D4 = X Y’ Z’ D5 = X Y’ Z D6 = X Y Z’ D7 = X Y Z 

![](/enc3.png)

## Figure -03 8 to 3 Decoder 


![](/enc4.png)


## Figure -04 8 to 3 Decoder implementation 

### Procedure :

STEP 1: Create module encoder and decoder. STEP 2: Get inputs and outputs for encoders and decoders. STEP 3: Perform or operation for encoder and and logic for decoders. STEP 4: Perform RTL LOGIC and get waveform.

### PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: thanika sree b
RegisterNumber:  22008978

ENCODER:-

module encoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input d0,d1,d2,d3,d4,d5,d6,d7;
output a,b,c;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule


DECODER:-

module decoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
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
```

### RTL LOGIC :

Encoder

![](/encoder.png)

Decoder

![](/decoder.png)

### TIMING DIGRAMS :

Encoder

![](/entd.png)

Decoder

![](/detd.png)

### TRUTH TABLE :

Encoder

![](/entt.png)

Decoder

![](/dett.png)

### RESULTS  :

Thus the program to desing encoder and decoder using quartus is done.
