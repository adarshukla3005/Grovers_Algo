# Grovers_Algo

# Quantum Factorization using Grover’s Algorithm

## Overview

Factoring large integers into their prime components is a crucial problem in cryptography and quantum computing offers potential speedups. Grover's algorithm, known for its quadratic speedup in search problems, is explored here for factoring bi-prime numbers using Quantum Fourier Transform (QFT) and oracle operations.

## Problem Statement

Given a bi-prime number \( N = p \times q \), where \( p \) and \( q \) are unknown primes, determine \( p \) and \( q \) using Grover’s algorithm. The algorithm is demonstrated for numbers 35, 115, and 893 (bonus task).

## Approach

### Circuit Design

Three input registers \( |x⟩, |y⟩, |z⟩ \) are used:
- \( |z⟩ \) stores \( N \) with \( n = \log_2{N} \) qubits.
- \( |x⟩, |y⟩ \) store factors \( p \) and \( q \).

### Oracle \( U_o(N) \)

The oracle is designed such that:
$$
U_o(N) |x⟩ |y⟩ = \begin{cases} 
|x⟩ |y⟩ & \text{if } x \times y \neq N \\
-|x⟩ |y⟩ & \text{if } x \times y = N 
\end{cases}
$$

### Implementation

- Superposition of inputs using Hadamard gates.
- Iterative multiplication, sign inversion, and Grover's operator application.
- Measurement of \( |x⟩ \) to obtain factors \( p \) and \( q \).

### Visualization

The script generates a visualization of the quantum circuit, aiding in understanding the operations and flow.

## Usage

To run the code:
1. Install required packages:
   ```sh
   pip install pennylane numpy matplotlib
