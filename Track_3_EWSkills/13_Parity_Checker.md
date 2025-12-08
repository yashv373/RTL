module parity_checker(
input [7:0]D,
output odd_parity, even_parity
);

assign odd_parity = ^D[7:0];

assign even_parity = ~(^D[7:0]);

endmodule