### Question:
create a circuit with 4 inputs and 2 outputs,
mapped as follows:
1. out = ab+cd
2. out_n = ~(ab+cd)
### Verilog:
 ```
 module top_module(
 input a,b,c,d
 output reg out, out_n
 ); 
 always@(*) begin
out=()
out_n=~(out);
 end
 endmodule
 ```

### System-Verilog:
```
module top_module(
input logic a,b,
output logic out
);
always_comb begin
out=~(a^b);
end
endmodule
```

### Suggested Testbench:
```
module top_tb;
logic a,b;
logic out;
top_module dut (.a(a), .b(b), .out(out));
initial begin
$monitor("time=%t, a=%b, b=%b, out=%b", $time, a,b,out);
a=1'b0; b=1'b0; 
#10
a=1'b1; b=1'b0;  
#10
a=1'b1; b=1'b1; 
#10
$finish;
end
endmodule
```