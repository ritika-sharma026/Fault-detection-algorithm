# Fault-detection-algorithm
## Circuit Fault Detection Algorithm

This repository contains a C++ implementation of an algorithm to detect faults in a digital circuit. The algorithm can identify structural faults at certain places/nodes in the circuit and test them before delivering the circuit to end-users. The code takes a circuit file as input and prints a vector for inputs to test the fault and the expected value of the output to confirm the fault.

## Prerequisites

To run the code, you need to have a C++ compiler installed on your system. The code has been tested with C++11 or later versions. You can use a C++ compiler like `g++` on Linux or MinGW on Windows.

## How to Generate the Environment

1. Clone the repository to your local machine using `git clone` command:

```bash
git clone https://github.com/your_username/circuit_fault_detection.git

## Change into the project directory:
cd circuit_fault_detection

## How to Run the Code
Place your circuit description in a text file with the desired filename (e.g., circuit.txt). The circuit file should follow the format provided below:
net_e = A & B
net_f = C | D
net_g = ~ net_f
Z = net_g ^ net_e

## Compile the code using your C++ compiler:
g++ -o circuit_fault_detection circuit_fault_detection.cpp

##Run the executable with the circuit file and fault details as arguments:
./circuit_fault_detection circuit.txt net_f SA0
Replace circuit.txt with the actual filename of your circuit file, and net_f SA0 with the fault node location and fault type you want to test.

Output
The code will generate an output file named output.txt in the run directory. The output file will contain the input vector used to test the fault and the expected value of the output to confirm the fault.

For example:[A, B, C, D] = [0, 0, 0, 1], Z = 1



## Additional Information
The circuit will have 4 inputs: A, B, C, and D. All inputs should be boolean type (0 and 1 are valid inputs).

The circuit will be built using the AND (&), OR (|), NOT (~), and XOR (^) gates.

Each input (A / B / C / D) will be utilized only once in the circuit.

The fault types supported are SA0 (stuck-at-0) and SA1 (stuck-at-1).

The code has been designed to be efficient and robust for identifying faults quickly.
