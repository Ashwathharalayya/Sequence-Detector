# Sequence Detector

## Overview
This repository contains the design, implementation, and Universal Verification Methodology (UVM) testbench for a sequence detector. The sequence detector identifies a specific sequence of bits in a serial input stream.

## Features
- Detects a predefined sequence (e.g., `1011`)
- Overlapping and non-overlapping detection modes
- Fully verified using UVM
- Suitable for digital logic design and VLSI implementation

## Files
- `rtl/sequence_detector.v`: Verilog RTL code for the sequence detector
- `testbench/testbench.v`: Basic testbench for initial functional simulation
- `uvm_env/top_env.sv`: UVM environment setup
- `uvm_env/seq.sv`: UVM sequences
- `uvm_env/driver.sv`: UVM driver
- `uvm_env/monitor.sv`: UVM monitor
- `uvm_env/scoreboard.sv`: UVM scoreboard
- `waveform.vcd`: Sample output waveform
- `README.md`: Documentation

## State Diagram
The sequence detector uses a Mealy/Moore state machine for tracking the bit sequence.

## How to Run

### Prerequisites
Ensure you have the following installed:
- Verilog simulator (e.g., Icarus Verilog, ModelSim)
- UVM library (SystemVerilog UVM package)

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sequence-detector.git
   cd sequence-detector
   ```

2. Compile the Verilog code and testbench:
   ```bash
   iverilog -o seq_det_sim rtl/sequence_detector.v testbench/testbench.v
   ```

3. For UVM simulation:
   ```bash
   vlog -sv rtl/sequence_detector.v uvm_env/*.sv
   vsim -c top_env -do "run -all"
   ```

4. View the waveform (optional):
   ```bash
   gtkwave waveform.vcd
   ```

## Example Output
For an input stream `1101011011`, the detector will output `1` when the sequence `1011` is recognized.

## Future Improvements
- Support for configurable sequences
- Implement low-power design
- Synthesize using OpenROAD for physical design
- Enhance UVM environment with functional coverage and assertions

## License
This project is licensed under the MIT License. See `LICENSE` for more details.

---
Feel free to contribute or report issues!

## Author
## ASHWAT HARALAYYA
