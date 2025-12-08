module concat8_packer(

 input A[3:0] , B,C,D,
 output  OUT[7:0],

 );

assign OUT[7:4]  = A;
assign OUT[3:2]  = B;
assign OUT[1] = ~C;
assign OUT[0] = D;

 endmodule