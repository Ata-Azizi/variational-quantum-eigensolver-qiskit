# Variational Quantum Eigensolver (VQE) with Qiskit

A two-qubit Variational Quantum Eigensolver (VQE) implementation using Qiskit, NumPy, and SciPy.

This project investigates the ground-state energy of an effective hydrogen-molecule (H₂) Hamiltonian using a hybrid quantum-classical optimization algorithm. It also explores the effects of quantum noise and measurement errors on energy estimation.

## Project Overview

The Variational Quantum Eigensolver is a hybrid quantum-classical algorithm designed to approximate the ground-state energy of a Hamiltonian.

The algorithm uses a parameterized quantum circuit to prepare a trial state and a classical optimizer to minimize the expectation value of the Hamiltonian.

The energy is calculated as:

```math
E(\boldsymbol{\theta}) =
\langle \psi(\boldsymbol{\theta}) |
H |
\psi(\boldsymbol{\theta}) \rangle
```

The variational principle guarantees that the energy of a normalized trial state cannot be lower than the exact ground-state energy.

## Hamiltonian

The project considers an effective two-qubit Hamiltonian of the form:

```math
H = c_0 I\otimes I + c_1 Z\otimes I + c_2 I\otimes Z + c_3 Z\otimes Z + c_4 X\otimes X
```

where the coefficients describe the effective molecular system.

The Hamiltonian is also diagonalized classically to obtain the exact ground-state energy for comparison with the VQE results.

## Implementation

The simulation includes:

- Construction of a parameterized two-qubit quantum circuit using rotation and entangling gates.
- Statevector-based calculation of Hamiltonian expectation values.
- Classical optimization of variational parameters using SciPy.
- Comparison of VQE results with exact diagonalization.
- Simulation of depolarizing and readout errors.
- Measurement-based energy estimation.
- Readout-error mitigation using a calibration matrix.
- Comparison of ideal, noisy, and mitigated energy estimates.

## Noise and Error Mitigation

Quantum noise and measurement errors can influence the accuracy of VQE calculations.

The project investigates these effects using Qiskit Aer noise models, including depolarizing errors and measurement errors.

Readout-error mitigation is implemented using a calibration matrix to estimate and correct the influence of measurement errors on the observed probability distributions.

This provides a comparison between energy estimates obtained under ideal conditions, with noise, and after readout-error mitigation.

## Notebook

**[Two-Qubit-H2-Hamiltonian.ipynb](Two-Qubit-H2-Hamiltonian.ipynb)**

The notebook contains the quantum circuit implementation, numerical optimization, noise simulations, and analysis of the resulting energy estimates.

## Requirements

- Python 3
- Qiskit
- Qiskit Aer
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook

Install the dependencies:

```bash
pip install qiskit qiskit-aer numpy scipy matplotlib jupyter
```

## Running the Project

Clone the repository:

```bash
git clone https://github.com/Ata-Azizi/variational-quantum-eigensolver-qiskit.git
cd variational-quantum-eigensolver-qiskit
```

Open `Two-Qubit-H2-Hamiltonian.ipynb` in VS Code or Jupyter Notebook and run the cells sequentially.

## Scientific Relevance

This project demonstrates several important concepts in quantum computing:

- Hybrid quantum-classical algorithms
- Variational optimization
- Quantum circuit simulation
- Hamiltonian expectation values
- Quantum noise modeling
- Measurement-based estimation
- Quantum error mitigation

These methods are relevant to quantum simulation, quantum chemistry, and near-term quantum computing applications.

## Author

**Ata Azizi Seraji**

M.Sc. Theoretical Physics — University of Göttingen

[GitHub Profile](https://github.com/Ata-Azizi)