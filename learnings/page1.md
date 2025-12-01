- in testbenches we always call a dut from the original design file, if you try to drive or provide a input to any of the signals that are being driven by the dut already, that is illegal.
  example :
DUT --> out=in;  ///// in TB --> we do out=1'b1; that is like the port "out" is being driven by two separate ports, and is not allowed.
---
- $ monitor, is only able to the change in values for a port, if the stimulus given at 2 consecutive time points in the TB is the same, it will not show that in the output log.
---
