# 🧠 Quantum Algorithms with Qiskit 2.x

This repository contains implementations of foundational and advanced **quantum algorithms** using modern **Qiskit 2.x primitives** such as `StatevectorSampler` and `StatevectorEstimator`.

The project is designed to build a **strong practical understanding of quantum computing**, progressing from basic circuits to variational and optimization-based algorithms.

---

## 🚀 Tech Stack

- Python 3.10+
- Qiskit 2.x
- NumPy

---

## 📂 Algorithms Implemented

### 🔹 Foundational Circuits
- Bell State (Entanglement)

### 🔹 Core Quantum Algorithms
- Deutsch–Jozsa Algorithm  
- Bernstein–Vazirani Algorithm  
- Simon’s Algorithm *(toy implementation)*  
- Grover’s Algorithm  

### 🔹 Fourier & Phase-Based Algorithms
- Quantum Fourier Transform (QFT)  
- Quantum Phase Estimation (QPE)  

### 🔹 Advanced / Theoretical Algorithms
- Shor’s Algorithm *(structural representation)*  
- HHL Algorithm *(conceptual circuit)*  

### 🔹 Variational & NISQ Algorithms
- Variational Quantum Eigensolver (VQE)  
- Quantum Approximate Optimization Algorithm (QAOA)  
- Variational Quantum Classifier (VQC)  

---

## 🧪 Example: Bell State Circuit

```python
from qiskit import QuantumCircuit
from qiskit.primitives import StatevectorSampler

qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
qc.measure_all()

sampler = StatevectorSampler()
result = sampler.run([qc]).result()

counts = result[0].data.meas.get_counts()
print(counts)
