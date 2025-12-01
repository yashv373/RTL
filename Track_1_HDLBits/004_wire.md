### Question:
 create a module with 3 inputs and 4 outputs
 linked as follows: a=w; b=x; b=y; c=z;

### Verilog:
 ```
 module top_module(
 input a,b,c,
 output w,x,y,z
 )
 always@(*) begin
 a=w; b=x; b=y; c=z;
 end
 endmodule
 ```

### System-Verilog:
```
module top_module(
input logic a,b,c,
output logic w,x,y,z
)
always_comb begin(
a=w; b=x; b=y; c=z;
)
end
endmodule
```

### Suggested Testbench:
```
module top_tb;
logic a,b,c;
logic w,x,y,z;


```