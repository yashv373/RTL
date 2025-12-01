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
 always_comb
 endmodule

```

### Suggested Testbench:
```

p
```