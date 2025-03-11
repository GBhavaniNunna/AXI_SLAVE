# AXI_SLAVE
AXI Slave interface implemented in Verilog/SystemVerilog with testbench and simulation setup.
**AXI4 Slave Interface**

This repository contains an AXI4 Slave Interface implemented in Verilog/SystemVerilog. It supports AXI read and write transactions and includes a simple memory model for data storage.

**Features**

-->Supports AXI4 read and write transactions

-->Implements write and read FSMs

-->Supports burst transactions (INCR, FIXED, WRAP)

-->Uses memory array (256 x 32-bit) for storage

-->Includes strobe messages for debugging

**File Structure**

AXI_Slave_Interface/
│── src/              # RTL code
│   ├── axi4_slave.v   # AXI Slave module
│── tb/               # Testbench code (to be added)
│── docs/             # Documentation and explanations
│── sim/              # Simulation scripts (if needed)
│── README.md         # Project description
│── Makefile          # (Optional) Script for simulation

**AXI Slave Ports**

-->Write Address Channel (awaddr, awlen, awsize, awburst, awvalid, awready)

-->Write Data Channel (wdata, wstrb, wlast, wvalid, wready)

-->Write Response Channel (bresp, bvalid, bready)

-->Read Address Channel (araddr, arlen, arsize, arburst, arvalid, arready)

--> Data Channel (rdata, rresp, rvalid, rlast, rready)

**Finite State Machines (FSMs)**

-->Write FSM:

WRITE_IDLE → WRITE_ADDR → WRITE_DATA → WRITE_RESP

-->Read FSM:

READ_IDLE → READ_ADDR → READ_DATA

**Simulation & Debugging**

The design includes $strobe messages for debugging memory writes and burst address calculations.

The mem array stores 256 words (32-bit each) for read/write operations.

**How to Run Simulation**

Install Xcelium/VCS/Questasim

Compile and run using a simulator:

vlog src/axi4_slave.v
vsim -c -do "run -all"

(Modify the commands based on your simulator)

**Next Steps**

Add a testbench for functional verification.

Improve burst handling for different memory alignment cases.

Optimize for FPGA/ASIC synthesis.

**Author**

G_Bhavani Nunna

