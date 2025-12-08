module bitwise_ops_demo(

input [3:0] A,

input [3:0] B,

output [3:0] AND_OUT,

output  [3:0] OR_OUT,

output  [3:0] XOR_OUT,

output  [3:0] XNOR_OUT);

  

assign AND_OUT=A&B;

assign XOR_OUT=A^B;

assign OR_OUT=A|B;

assign XNOR_OUT=~(A^B);

  

endmodule