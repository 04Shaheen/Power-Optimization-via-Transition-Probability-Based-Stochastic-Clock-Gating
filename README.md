Power-Optimization-via-Transition-Probability-Based-Stochastic-Clock-Gating
Clock Gating Techniques for PIPO Register System
Overview
This repository contains a Verilog implementation of window-based and event-triggered clock gating techniques designed to reduce power consumption in a Parallel-In Parallel-Out (PIPO) register system. The project, developed for an Applied Stochastic Processes mathematics course, leverages stochastic modeling (e.g., Markov chains, probability distributions) to generate input patterns and evaluate the effectiveness of the gating methods. Simulations were conducted using Xilinx Vivado to analyze power savings through toggle counts and active cycles, comparing the gated methods (window-based, event-triggered) against an always-enabled baseline.

Project Goals
Implement and simulate clock gating mechanisms to minimize power usage in digital systems.
Apply stochastic processes (e.g., Markov chain-based state transitions) to model system activity probabilistically.
Evaluate the performance of window-based and event-triggered gating using tailored testbenches, focusing on mathematical predictions of power efficiency.
Structure
Verilog Modules
TopModule.v: Integrates the PIPO register, clock gating modules, and always-enabled baseline.
PIPO_Register.v: Implements the parallel-in parallel-out register with toggle and cycle counting.
ClockGating_WindowBased.v: Window-based clock gating, observing activity over a fixed window (e.g., 4 cycles) and gating for a specified period (e.g., 8 cycles).
ClockGating_EventTriggered.v: Event-triggered clock gating, gating after idle cycles (e.g., 4 cycles) unless activity exceeds a threshold (e.g., 1 bit flip).
Clock_AlwaysEnabled.v: Baseline module with no gating, keeping the clock always enabled.
Testbenches
Testbench.v: Probabilistic input testbenches using Markov chain-based random state transitions over 100,000 cycles.
WindowBased_Testbench.v: Tailored testbench for window-based gating, emphasizing long idle periods and high-activity patterns over 250ns.
EventTriggered_Testbench.v: Tailored testbench for event-triggered gating, focusing on sporadic changes and idle periods over 230ns.
Installation
Install Xilinx Vivado
Ensure Xilinx Vivado (or a compatible version for Verilog simulation) is installed on your system. Download from the Xilinx website if needed.
Verify Vivado is configured for Verilog compilation and simulation.
Dependencies
No additional dependencies are required beyond Vivado for simulation and waveform analysis.
Usage
Open in Vivado
Launch Xilinx Vivado and create a new project.
Add all .v files (modules and testbenches) to your project source files.
Set the top module for simulation (e.g., Testbench, WindowBased_Testbench, or EventTriggered_Testbench).
Run Simulations
In Vivado, use the Simulation tab to compile and simulate each testbench.
Configure the simulation time (e.g., 100,000 cycles for probabilistic, 250ns for window-based, 230ns for event-triggered).
Add signals like clk, rst, d, gated_clk_*, q_*, toggle_count_*, and active_cycle_count_* to the waveform viewer.
Run the simulation and analyze waveforms to observe clock gating behavior and power savings.
Analyze Results
Use Vivado’s waveform viewer to inspect gating effectiveness (e.g., idle periods, activity patterns).
Optionally, extract numerical data (e.g., toggle counts, active cycles) to quantify power savings.
Contributing
This project is for educational purposes. Contributions are welcome for enhancing the Verilog code, testbenches, or adding new stochastic modeling features. Please fork the repository, make changes, and submit a pull request with a description of your improvements.

License
Apache 2.0

Contact
Author: Shaheen Ali (04Shaheen)
Course: Applied Stochastic Processes
