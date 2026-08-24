# Quantum Teleportation Under Noise

A small computational study investigating how quantum noise affects
the performance and fidelity of quantum teleportation using Qiskit
and Qiskit Aer.

## Overview

Quantum teleportation is a fundamental quantum communication protocol
that allows an unknown quantum state to be transferred from one qubit
to another using entanglement and classical communication.

This project studies how different noise conditions affect the
teleportation process through simulation.

The study currently consists of three experiments:

1. Bit-flip noise
2. Depolarizing noise
3. Input-state dependence under depolarizing noise

---

## Research Questions

The project investigates:

- How does increasing quantum noise affect teleportation success?
- How do different noise models affect teleportation performance?
- Does the input quantum state influence teleportation fidelity under
  the same noise conditions?

---

# Experiments

## Experiment 1 — Bit-Flip Noise

### Objective

Investigate how increasing bit-flip noise affects the success rate
of quantum teleportation.

### Setup

- Framework: Qiskit
- Simulator: Qiskit Aer
- Number of qubits: 3
- Input state: |0>
- Shots per configuration: 1000
- Noise model: Bit-flip noise
- Noise range: 0%–20%

### Key Result

Teleportation success decreased as the bit-flip noise probability
increased.

At 20% bit-flip noise, the measured teleportation success rate was
67.1%.

See the detailed documentation:

[`docs/experiment_1.md`](docs/experiment_1.md)

---

## Experiment 2 — Depolarizing Noise

### Objective

Investigate how depolarizing noise affects quantum teleportation and
compare its effect with bit-flip noise.

### Setup

- Framework: Qiskit
- Simulator: Qiskit Aer
- Number of qubits: 3
- Input state: |0>
- Shots per configuration: 1000
- Noise model: Depolarizing noise
- Noise range: 0%–20%

### Key Result

Teleportation success decreased as depolarizing noise increased.

At 20% depolarizing noise, the measured success rate was 82.8%.

Under the noise parameterization used in this simulation, the
depolarizing-noise experiment produced higher success rates than the
bit-flip-noise experiment across the tested range.

See the detailed documentation:

[`docs/experiment_2.md`](docs/experiment_2.md)

### Noise Model Comparison

![Noise model comparison](results/noise_model_comparison.png)

---

## Experiment 3 — Input-State Dependence

### Objective

Investigate whether the quantum state being teleported affects
teleportation fidelity under increasing depolarizing noise.

Three input states were investigated:

- |0>
- |1>
- |+> = (|0> + |1>) / sqrt(2)

### Evaluation Metric

Unlike the first two experiments, this experiment uses **quantum-state
fidelity** to evaluate how closely Bob's final state matches the
original input state.

A fidelity of 1 represents a perfect match.

### Key Result

Under the simulated circuit and noise configuration, the |+> input
state exhibited lower teleportation fidelity than the computational
basis states |0> and |1> as the depolarizing-noise parameter increased.

At 20% depolarizing noise:

| Input State | Fidelity |
|---|---:|
| `\|0⟩` | 83.0% |
| `\|1⟩` | 82.4% |
| `\|+⟩` | 70.8% |

### Fidelity Comparison

![Input-state fidelity](results/input_state_fidelity.png)

See the detailed documentation:

[`docs/experiment_3.md`](docs/experiment_3.md)

---

# Project Structure

```text
Quantum_Teleportation_Noise_Study/
│
├── README.md
│
├── docs/
│   ├── experiment_1.md
│   ├── experiment_2.md
│   └── experiment_3.md
│
├── results/
│   ├── distribution_0_percent.png
│   ├── distribution_10_percent.png
│   ├── distribution_20_percent.png
│   ├── QC_Success vs Bit_Flip_Noise.png
│   ├── noise_model_comparison.png
│   └── input_state_fidelity.png
│
├── experiment_1_bit_flip_noise.ipynb
└── ...
