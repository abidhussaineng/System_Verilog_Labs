# System_Verilog_Labs
Collection of SystemVerilog lab tasks with design files, testbenches, and simulation scripts (QuestaSim).

# System_Verilog_Labs
Collection of SystemVerilog lab tasks with design files, testbenches, and simulation scripts (QuestaSim).
Got it  You want a README file that explains how to run your Verilog/SystemVerilog code and see the results (using monitor, waveform, etc.) on QuestaSim. Here’s a clean draft for you:


# README – Running and Monitoring Simulation on QuestaSim

 Requirements

 QuestaSim (Mentor Graphics / Siemens EDA) installed
 Verilog/SystemVerilog design files (.v / .sv)
 Testbench file with $monitor or $display statements

 Steps to Simulate

 1. Start QuestaSim

bash
vsim &

This opens the QuestaSim GUI.
Or, run commands in command-line mode.


 2. Compile Design and Testbench

tcl
vlog design.sv testbench.sv

 vlog = compile command
 Add all your RTL and testbench files.

If no errors, compiled units appear in the work library.


 3. Run Simulation

tcl
vsim work.testbench

 Replace testbench with the top-level module name of your testbench.


 4. Add Waveforms (Optional)

tcl
add wave 

 Adds all signals to the waveform window.
 Or use add wave dut. to add only DUT signals.


5. Run the Simulation

tcl
run 100ns

 Replace 100ns with the desired simulation time.
 Use run -all if you want it to run until $finish.


 Viewing Monitor Output

 $monitor and $display outputs are shown in the Transcript window (console at bottom).
 Example:

  verilog
  initial begin
    $monitor("Time=%0t A=%b B=%b Sum=%b", $time, A, B, Sum);
  end
   These results won’t appear in the waveform window, but directly in the transcript.



Waveform Window

 After add wave  and run, go to Wave window in the GUI.
 You can zoom, scroll, and analyze signals.


 Quick One-Liner Flow

tcl
vlog design.sv testbench.sv
vsim work.testbench
add wave 
run -all

