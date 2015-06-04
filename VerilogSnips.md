
## Simple logic and verification test benches in Verilog ##

### Logic blocks and units ###
#### OR gate ####
```
// Verilog code for OR gate
module OR (input A, B, output F);
  assign F = (A | B);
endmodule
// end of Verilog code
```
#### AND gate ####
```
// Verilog code for AND gate
module AND (input A, B, output F);
  assign F = (A & B);
endmodule
// end of Verilog code
```
#### XOR gate ####
```
// Verilog code for XOR gate
module XOR (input A, B, output F);
  assign F = ((A & ~B) | (~A & B));
endmodule
// end of Verilog code
```
#### Half Adder ####
```
// Verilog code for Half Adder
module halfadder (input A, B, output S, C);
XOR xor_ha(.A(A),.B(B),.F(S));
AND and_ha(.A(A),.B(B),.F(C));
endmodule
// end of Verilog code
```
#### Full Adder ####
```
// Verilog code for Half Adder
module fulladder (input A, B,Cin, output S, Cout);
wire C1, C2, S1;
halfadder halfadder1(.A(A),.B(B),.S(S1),.C(C1));
halfadder halfadder2(.A(S1),.B(Cin),.S(S),.C(C2));
OR orgate(.A(C1),.B(C2),.F(Cout));
endmodule
// end of Verilog code
```
#### 4 Bit Add Subtract Unit ####
```
// Verilog code for 4 Bit Subtract / Adder
module four_bit_subtract_adder (input [3:0]A, [3:0]B, input Cin,OP, output [3:0]S,output Cout);

wire [3:1]C;
wire [3:0]M; 


//wire C1, C2, C3, M0,M1,M2,M3; //Cs are the carry signals and Ms are the mux outputs

MUX2_1 mux1(.A(~A[0]),.B(A[0]),.SEL(OP),.F(M[0]));
MUX2_1 mux2(.A(~A[1]),.B(A[1]),.SEL(OP),.F(M[1]));
MUX2_1 mux3(.A(~A[2]),.B(A[2]),.SEL(OP),.F(M[2]));
MUX2_1 mux4(.A(~A[3]),.B(A[3]),.SEL(OP),.F(M[3]));

fulladder fa1(.A(M[0]),.B(B[0]),.Cin(Cin),.S(S[0]),.Cout(C[1]));
fulladder fa2(.A(M[1]),.B(B[1]),.Cin(C[1]),.S(S[1]),.Cout(C[2]));
fulladder fa3(.A(M[2]),.B(B[2]),.Cin(C[2]),.S(S[2]),.Cout(C[3]));
fulladder fa4(.A(M[3]),.B(B[3]),.Cin(C[3]),.S(S[3]),.Cout(Cout));

endmodule
// end of Verilog code

endmodule
// end of Verilog code
```
#### 32 Bit ADD/Subtract Math Co-processor ####
```
// Verilog code for 32 Bit Add/Subtract Co-Processor

module thirtytwo_bit_subtract_adder (input [31:0]A, [31:0]B, input Cin,OP, output [31:0]S, output Cout);
 
wire [32:1]C;
wire [31:0]M; 

// Mux Network
MUX2_1 mux1(.A(~A[0]),.B(A[0]),.SEL(OP),.F(M[0]));
MUX2_1 mux2(.A(~A[1]),.B(A[1]),.SEL(OP),.F(M[1]));
MUX2_1 mux3(.A(~A[2]),.B(A[2]),.SEL(OP),.F(M[2]));
MUX2_1 mux4(.A(~A[3]),.B(A[3]),.SEL(OP),.F(M[3]));
MUX2_1 mux5(.A(~A[4]),.B(A[4]),.SEL(OP),.F(M[4]));
MUX2_1 mux6(.A(~A[5]),.B(A[5]),.SEL(OP),.F(M[5]));
MUX2_1 mux7(.A(~A[6]),.B(A[6]),.SEL(OP),.F(M[6]));
MUX2_1 mux8(.A(~A[7]),.B(A[7]),.SEL(OP),.F(M[7]));
MUX2_1 mux9(.A(~A[8]),.B(A[8]),.SEL(OP),.F(M[8]));
MUX2_1 mux10(.A(~A[9]),.B(A[9]),.SEL(OP),.F(M[9]));
MUX2_1 mux11(.A(~A[10]),.B(A[10]),.SEL(OP),.F(M[10]));
MUX2_1 mux12(.A(~A[11]),.B(A[11]),.SEL(OP),.F(M[11]));
MUX2_1 mux13(.A(~A[12]),.B(A[12]),.SEL(OP),.F(M[12]));
MUX2_1 mux14(.A(~A[13]),.B(A[13]),.SEL(OP),.F(M[13]));
MUX2_1 mux15(.A(~A[14]),.B(A[14]),.SEL(OP),.F(M[14]));
MUX2_1 mux16(.A(~A[15]),.B(A[15]),.SEL(OP),.F(M[15]));
MUX2_1 mux17(.A(~A[16]),.B(A[16]),.SEL(OP),.F(M[16]));
MUX2_1 mux18(.A(~A[17]),.B(A[17]),.SEL(OP),.F(M[17]));
MUX2_1 mux19(.A(~A[18]),.B(A[18]),.SEL(OP),.F(M[18]));
MUX2_1 mux20(.A(~A[19]),.B(A[19]),.SEL(OP),.F(M[19]));
MUX2_1 mux21(.A(~A[20]),.B(A[20]),.SEL(OP),.F(M[20]));
MUX2_1 mux22(.A(~A[21]),.B(A[21]),.SEL(OP),.F(M[21]));
MUX2_1 mux23(.A(~A[22]),.B(A[22]),.SEL(OP),.F(M[22]));
MUX2_1 mux24(.A(~A[23]),.B(A[23]),.SEL(OP),.F(M[23]));
MUX2_1 mux25(.A(~A[24]),.B(A[24]),.SEL(OP),.F(M[24]));
MUX2_1 mux26(.A(~A[25]),.B(A[25]),.SEL(OP),.F(M[25]));
MUX2_1 mux27(.A(~A[26]),.B(A[26]),.SEL(OP),.F(M[26]));
MUX2_1 mux28(.A(~A[27]),.B(A[27]),.SEL(OP),.F(M[27]));
MUX2_1 mux29(.A(~A[28]),.B(A[28]),.SEL(OP),.F(M[28]));
MUX2_1 mux30(.A(~A[29]),.B(A[29]),.SEL(OP),.F(M[29]));
MUX2_1 mux31(.A(~A[30]),.B(A[30]),.SEL(OP),.F(M[30]));
MUX2_1 mux32(.A(~A[31]),.B(A[31]),.SEL(OP),.F(M[31]));

// Full Adder Network
fulladder fa1(.A(A[0]),.B(B[0]),.Cin(Cin),.S(S[0]),.Cout(C[1]));
fulladder fa2(.A(A[1]),.B(B[1]),.Cin(C[1]),.S(S[1]),.Cout(C[2]));
fulladder fa3(.A(A[2]),.B(B[2]),.Cin(C[2]),.S(S[2]),.Cout(C[3]));
fulladder fa4(.A(A[3]),.B(B[3]),.Cin(C[3]),.S(S[3]),.Cout(C[4]));
fulladder fa5(.A(A[4]),.B(B[4]),.Cin(C[4]),.S(S[4]),.Cout(C[5]));
fulladder fa6(.A(A[5]),.B(B[5]),.Cin(C[5]),.S(S[5]),.Cout(C[6]));
fulladder fa7(.A(A[6]),.B(B[6]),.Cin(C[6]),.S(S[6]),.Cout(C[7]));
fulladder fa8(.A(A[7]),.B(B[7]),.Cin(C[7]),.S(S[7]),.Cout(C[8]));
fulladder fa9(.A(A[8]),.B(B[8]),.Cin(C[8]),.S(S[8]),.Cout(C[9]));
fulladder fa10(.A(A[9]),.B(B[9]),.Cin(C[9]),.S(S[9]),.Cout(C[10]));
fulladder fa11(.A(A[10]),.B(B[10]),.Cin(C[10]),.S(S[10]),.Cout(C[11]));
fulladder fa12(.A(A[11]),.B(B[11]),.Cin(C[11]),.S(S[11]),.Cout(C[12]));
fulladder fa13(.A(A[12]),.B(B[12]),.Cin(C[12]),.S(S[12]),.Cout(C[13]));
fulladder fa14(.A(A[13]),.B(B[13]),.Cin(C[13]),.S(S[13]),.Cout(C[14]));
fulladder fa15(.A(A[14]),.B(B[14]),.Cin(C[14]),.S(S[14]),.Cout(C[15]));
fulladder fa16(.A(A[15]),.B(B[15]),.Cin(C[15]),.S(S[15]),.Cout(C[16]));
fulladder fa17(.A(A[16]),.B(B[16]),.Cin(C[16]),.S(S[16]),.Cout(C[17]));
fulladder fa18(.A(A[17]),.B(B[17]),.Cin(C[17]),.S(S[17]),.Cout(C[18]));
fulladder fa19(.A(A[18]),.B(B[18]),.Cin(C[18]),.S(S[18]),.Cout(C[19]));
fulladder fa20(.A(A[19]),.B(B[19]),.Cin(C[19]),.S(S[19]),.Cout(C[20]));
fulladder fa21(.A(A[20]),.B(B[20]),.Cin(C[20]),.S(S[20]),.Cout(C[21]));
fulladder fa22(.A(A[21]),.B(B[21]),.Cin(C[21]),.S(S[21]),.Cout(C[22]));
fulladder fa23(.A(A[22]),.B(B[22]),.Cin(C[22]),.S(S[22]),.Cout(C[23]));
fulladder fa24(.A(A[23]),.B(B[23]),.Cin(C[23]),.S(S[23]),.Cout(C[24]));
fulladder fa25(.A(A[24]),.B(B[24]),.Cin(C[24]),.S(S[24]),.Cout(C[25]));
fulladder fa26(.A(A[25]),.B(B[25]),.Cin(C[25]),.S(S[25]),.Cout(C[26]));
fulladder fa27(.A(A[26]),.B(B[26]),.Cin(C[26]),.S(S[26]),.Cout(C[27]));
fulladder fa28(.A(A[27]),.B(B[27]),.Cin(C[27]),.S(S[27]),.Cout(C[28]));
fulladder fa29(.A(A[28]),.B(B[28]),.Cin(C[28]),.S(S[28]),.Cout(C[29]));
fulladder fa30(.A(A[29]),.B(B[29]),.Cin(C[29]),.S(S[29]),.Cout(C[30]));
fulladder fa31(.A(A[30]),.B(B[30]),.Cin(C[30]),.S(S[30]),.Cout(C[31]));
fulladder fa32(.A(A[31]),.B(B[31]),.Cin(C[31]),.S(S[31]),.Cout(Cout));


endmodule
// end of Verilog code

```

### Test Benches ###
#### XOR gate TB ####
```
// xor tb
module xor_tb;
reg A, B;
wire F;
XOR xor_tb(.A(A),.B(B),.F(F));
initial begin
A=0;
B=0;
#5
A=1;
B=0;
#5
A=0;
B=1;
#5
A=1;
B=1;
#5
A=1;
B=1;
end 
endmodule 
```
#### AND TB ####
```
// and tb
module and_tb;
reg A, B;
wire F;
AND and_tb(.A(A),.B(B),.F(F));
initial begin
A=0;
B=0;
#5
A=1;
B=0;
#5
A=0;
B=1;
#5
A=1;
B=1;
#5
A=1;
B=1;
end 
endmodule 
```
#### Half Adder TB ####
```
// Half Adder tb
module halfadder_tb;
reg A, B;
wire S, C;
halfadder halfadder_tb(.A(A),.B(B),.S(S),.C(C));
initial begin
A=0;
B=0;
#5
A=1;
B=0;
#5
A=0;
B=1;
#5
A=1;
B=1;
#5
A=1;
B=1;
end 
endmodule 
```
#### Full Adder ####
```
// Full Adder tb
module fulladder_tb;
reg A, B, Cin;
wire S, Cout;
fulladder fulladder_tb(.A(A),.B(B),.Cin(Cin),.S(S),.Cout(Cout));
initial begin
A=0;
B=1;
Cin=0;
#2
A=1;
B=1;
Cin=0;
#2
A=1;
B=1;
Cin=1;
#2
A=0;
B=0;
Cin=1;
#2;
end 
endmodule 
```

#### 4 Bit Subtract / Adder TB ####
```
// 4 bit math co-processor tb

module add_sub4_tb;

reg [3:0]A;
reg [3:0]B;
reg Cin, OP;
wire overflow;
wire [3:0]S;

four_bit_subtract_adder add_sub4_tb (.A(A),.B(B),.S(S),.Cin(Cin),.OP(OP),.Cout(overflow));

integer i;

initial begin
Cin =0;
OP=0;

for (i = 0; i < 10; i = i + 1) begin
A = $random % 4; // Initialize input to random number
B = $random % 4; // Initialize input to random number

if (i%2 == 0)
OP=1;
else
OP=0;

#2;
end
end 
endmodule 
```
#### 32 bit Add/Subtract co-processor ####
```
// 32 bit math co-processor tb
module add_sub32_tb;
reg [31:0]A;
reg [31:0]B;
reg Cin, OP;
wire overflow;
wire [31:0]S;

thirtytwo_bit_subtract_adder add_sub32_tb (.A(A),.B(B),.S(S),.Cin(Cin),.OP(OP),.Cout(overflow));
integer i;
initial begin
Cin =0;
OP=0;
for (i = 0; i < 15; i = i + 1) begin
A = $random; // Initialize input to random number
B = $random; // Initialize input to random number
if (i%2 == 0)
OP=1;
else
OP=0;
#3;
end
end 
endmodule 
```

### Build command ###
```
vcs -full64 -sverilog -f files -gui -debug
```

