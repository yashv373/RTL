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
logic input1, output1;
 
top_module dut(.in(input1), .out(output1));  
initial begin
$monitor("at time %t --> input = %b,output = %b", $time , input, output);
input<=1'b1; 
output<=input;#5
input<=1'b0; 
output<=input;#5
input<=1'b0;
output<=input; #5
input<=1'b1; 
output<=input;#5
$finish;

end

endmodule
```