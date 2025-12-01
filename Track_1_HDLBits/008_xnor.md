### Question:
create a xnor gate

### Verilog:
 ```
 module top_module(
 input a,b,
 output reg out
 ); 
 always@(*) begin
out=~(a^b);
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