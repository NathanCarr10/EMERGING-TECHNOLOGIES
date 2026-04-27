# Emerging Technologies Assessment — Classical vs Quantum Algorithms (Deutsch / Deutsch–Jozsa)

4th Year Computing — ATU Galway 2025/26  
**Nathan Carr — G00410214**

This repository contains my submission for the **Emerging Technologies (Summer 25/26)** assessment.

The project explores the difference between classical and quantum approaches to a specific problem: determining whether a Boolean function is **constant** or **balanced**. This is known as the Deutsch–Jozsa problem, and it is one of the earliest examples where a quantum algorithm can provably outperform any classical deterministic algorithm.

The notebook covers:

- Generating random constant/balanced Boolean functions with 4-bit input
- A classical decision algorithm and its worst-case complexity (2^(n−1) + 1 evaluations)
- Quantum oracles for all four single-bit Boolean functions
- Deutsch's algorithm implemented in Qiskit (1-bit input, 1 oracle call)
- The full Deutsch–Jozsa algorithm for 4-bit functions (1 oracle call regardless of input size)

---

## Repository Structure

| File | Description |
|---|---|
| `problems.ipynb` | Main submission notebook — all five problems with explanations, code, and results |
| `requirements.txt` | Python dependencies needed to run the notebook |
| `.gitignore` | Excludes virtual environments, caches, and editor files |

---

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/NathanCarr10/EMERGING-TECHNOLOGIES
cd EMERGING-TECHNOLOGIES
```

### 2. Install dependencies

Python 3.11 or later is recommended. Create a virtual environment first:

```bash
python -m venv .venv
```

Activate it:

- **Windows (PowerShell):** `.venv\Scripts\Activate.ps1`
- **Mac/Linux:** `source .venv/bin/activate`

Then install:

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

```bash
jupyter notebook problems.ipynb
```

Then run all cells: **Kernel → Restart & Run All**

---

## Dependencies

The main libraries used are:

- [Qiskit](https://qiskit.org/) — quantum circuit construction and simulation
- [Qiskit Aer](https://qiskit.github.io/qiskit-aer/) — local quantum simulator backend
- [Jupyter](https://jupyter.org/) — notebook environment

All versions are pinned in `requirements.txt`.

---

## Problems Overview

| Problem | Topic | Approach |
|---|---|---|
| 1 | Generating random Boolean functions | Classical — Python, itertools |
| 2 | Classifying constant vs balanced functions | Classical — worst case 9 evaluations for n=4 |
| 3 | Quantum oracles for 1-bit functions | Qiskit — X gate, CNOT |
| 4 | Deutsch's algorithm | Qiskit — 1 oracle call, noiseless simulator |
| 5 | Deutsch–Jozsa algorithm (4-bit) | Qiskit — 1 oracle call vs 9 classical |

---

## Key Result

The classical algorithm needs up to **9 function evaluations** to be certain whether a 4-bit function is constant or balanced. The Deutsch–Jozsa quantum circuit needs exactly **1 oracle call**, regardless of how many input bits the function takes. This is a genuine exponential speedup under the promise that the function is either constant or balanced.

---

## References

- Deutsch, D. (1985). *Quantum Theory, the Church–Turing Principle and the Universal Quantum Computer*. Proceedings of the Royal Society of London A, 400, 97–117.

- Deutsch, D., & Jozsa, R. (1992). *Rapid Solution of Problems by Quantum Computation*. Proceedings of the Royal Society of London A, 439, 553–558.

- Nielsen, M. A., & Chuang, I. L. (2010). *Quantum Computation and Quantum Information*. Cambridge University Press.

- IBM Quantum Learning — Deutsch's Algorithm:  
  https://quantum.cloud.ibm.com/learning/en/courses/fundamentals-of-quantum-algorithms/quantum-query-algorithms/deutsch-algorithm

- IBM Quantum Learning — Deutsch–Jozsa Algorithm:  
  https://quantum.cloud.ibm.com/learning/en/modules/computer-science/deutsch-jozsa

- Qiskit Documentation:  
  https://qiskit.org/documentation/

- Python Documentation — itertools.product:  
  https://docs.python.org/3/library/itertools.html#itertools.product