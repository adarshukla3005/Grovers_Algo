# Grovers_Algo

## QCG Open Project 1: Using Grover’s Algorithm for Factorization of Bi-Primes

### Problem Statement

#### Overview

Factoring large integers into their prime components is a fundamental problem with significant implications in cryptography and information security. Traditional algorithms, like Shor's algorithm, have demonstrated superpolynomial speedups over classical methods but require quantum computers with millions of qubits. Grover's search algorithm, traditionally used for database search, provides a quadratic speedup and is now being explored for factoring bi-primes. The oracle can be built using adder and multiplier circuits utilizing the Quantum Fourier Transform (QFT).

#### Statement

Given a bi-prime number \(N = p \times q\) (where \(p\) and \(q\) are unknown prime numbers), determine the values of \(p\) and \(q\) using Grover’s algorithm. Demonstrate the algorithm for the following list of numbers:

- 35
- 115
- 893 (bonus task)

Use the appropriate number of qubits to store the number \(N\) and outputs \(p\) and \(q\).

## Approach

While there are multiple ways to solve this problem, the fundamental approach remains consistent. Three input registers \(|x⟩, |y⟩, |z⟩\) are required. The register \(|z⟩\) should store the input value \(N\) and should contain \(n = \log_2{N}\) qubits. The registers \(|x⟩, |y⟩\) should be large enough to store the prime factors of \(N\).

The oracle \(U_o(N)\) should be such that for input registers \(|x⟩, |y⟩\):

$$
U_o(N)|x⟩|y⟩ = \begin{cases} 
|x⟩|y⟩ & \text{if } x \times y \neq N\\ 
-|x⟩|y⟩ & \text{if } x \times y = N 
\end{cases}
$$

Now, we implement this oracle into Grover’s circuit and run the circuit multiple times to obtain the amplitudes of registers \(X\) and \(Y\), thereby determining the prime factors.

## Outputs

### N = 35
![image](https://github.com/adarshukla3005/Grovers_Algo/assets/122630902/46b1904e-f391-45a1-b504-ee6fbd59a251)

### N = 115
![image](https://github.com/adarshukla3005/Grovers_Algo/assets/122630902/4e39108d-e391-4c38-a15f-9de76f52a126)


# Implementation

The implementation is available in the following notebook on Google Colab:

[Quantum Factorization using Grover’s Algorithm](https://colab.research.google.com/github/adarshukla3005/Grovers_Algo/blob/main/Grover_method_for(115_%26_35).ipynb)
        

### Prerequisites

Ensure you have the following packages installed:

- Python 3.7 or higher
- PennyLane
- NumPy
- Matplotlib

Install the necessary packages using pip:

## References

Quantum Factoring Algorithm using Grover Search (S. Whitlock and T. D. Kieu)

Quantum arithmetic with the Quantum Fourier Transform (Lidia Ruiz-Perez and Juan Carlos Garcia-Escartin)

Basic arithmetic with the quantum Fourier transform (QFT) (PennyLane Tutorial)

```sh
pip install pennylane numpy matplotlib
