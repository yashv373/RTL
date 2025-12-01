### Question:
 creating a module that has one input and one output and behaves like a wire 

### Verilog:
 ```
module top_module(
input in,
output out
);
assign out=in;
 endmodule
 ```

### System-Verilog:
```
module top_module(
input logic in,
output logic out
);
 always_comb begin
 out=in;
 end
 endmodule

```

### Suggested Testbench:
```
module testbench;
logic input, output;
initial begin( // clocking block
int x;
#5 clk x=~x;
end
top_module dut(.input(in), .output(out)); // instantiate the dut
always@(posedge_clk) begin
input<=1'b1; 
output<=input;#5
input<=1'b0; 
output<=input;#5
input<=1'b0;
output<=input; #5
input<=1'b1; 
output<=input;#5
end
$monitor("at time %t --> input = %b,output = %b", t, input, output);
endmodule



```