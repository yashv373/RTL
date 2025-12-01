- in testbenches we always call a dut from the original design file, if you try to drive or provide a input to any of the signals that are being driven by the dut already, that is illegal.
  example :
DUT --> out=in;  ///// in TB --> we do out=1'b1; that is like the port "out" is being driven by two separate pr