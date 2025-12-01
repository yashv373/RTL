### Question:
 creating a module that has one input and one output and behaves like a wire 

### Verilog:
 ```
module top_module(
input in,
output out
);
wire in;
reg out;
assign out=in;
 endmodule
 ```

### System-Verilog:
```
module top_module(
input logic in,
output logic out
);
 always_comb begin(
 out=in;
 )
 end
 endmodule

```

### Suggested Testbench:
```
module testbench;
initial begin(
int x=
top_module dut()
```