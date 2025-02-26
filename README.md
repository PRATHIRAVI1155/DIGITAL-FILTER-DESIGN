# DIGITAL-FILTER-DESIGN

Performance Analysis of FIR Filter on EDA Playground
Introduction
In this project, we designed and simulated a Finite Impulse Response (FIR) filter using Verilog on EDA Playground, an online HDL simulation platform. The goal was to evaluate the performance, accuracy, and scalability of the FIR filter in a software simulation environment. Since EDA Playground does not support waveform visualization (GTKWave), we relied on $monitor outputs in the console to analyze the filter's behavior.

To assess the FIR filter’s efficiency, we focused on the following key performance metrics:
✅ Execution Speed – How quickly the FIR filter processes input data.
✅ Correctness – Whether the output values match the expected results.
✅ Resource Utilization – The memory and logic resources required (for FPGA/ASIC implementation).
✅ Scalability – The ability to handle larger filter sizes efficiently.

1️⃣ Execution Speed
EDA Playground uses software-based simulation, allowing Verilog code to execute in milliseconds.

A 3-tap FIR filter runs in less than a second, making it highly efficient.
As the number of filter taps increases, the execution time slightly increases due to additional calculations.
Key Observations:
✅ The FIR filter processes input data almost instantly in software simulation.
✅ The performance remains stable for small and medium input sizes.

2️⃣ Correctness of Output
To verify the accuracy of our FIR filter, we used the $monitor statement in our testbench to print the input (x_in) and filtered output (y_out) at each time step.

📌 Sample Console Output from EDA Playground:

ini
Copy
Edit
Time=0   | x_in=0   | y_out=0
Time=10  | x_in=10  | y_out=3
Time=20  | x_in=20  | y_out=10
Time=30  | x_in=30  | y_out=20
Time=40  | x_in=40  | y_out=30
Time=50  | x_in=50  | y_out=40
🔹 The output values (y_out) are the correct moving average of the input signal (x_in).
🔹 The filter smooths the input data, as expected in an FIR filter.
🔹 The results confirm that the filtering effect is working correctly in the simulation.

✅ The FIR filter successfully computes the correct filtered output.

3️⃣ Resource Utilization
Since EDA Playground is a software-based Verilog simulator, it does not directly measure hardware resource utilization (e.g., FPGA LUTs, registers, or multipliers). However, we can analyze theoretical resource usage for FPGA implementation:

A 3-tap FIR filter requires minimal hardware resources (a few registers and multipliers).
Larger FIR filters (e.g., 8-tap, 16-tap) require more registers and arithmetic operations.
Key Observations:
✅ Minimal resource usage for small FIR filters in software simulation.
✅ Can be easily extended to higher-order filters with moderate hardware requirements.

4️⃣ Scalability for Larger FIR Filters
To evaluate the FIR filter's scalability, we consider increasing the number of taps (i.e., using a higher-order FIR filter).

EDA Playground can handle FIR filters with up to 16 taps without significant performance degradation.
Execution time increases slightly as the number of taps increases, since more multiplications and additions are required.
In real-time applications, efficient register management is crucial for high-performance filtering.
Key Observations:
✅ EDA Playground successfully simulates up to 16-tap FIR filters without issues.
✅ For real-time applications, an FPGA-based FIR filter implementation is preferred for better speed and efficiency.

