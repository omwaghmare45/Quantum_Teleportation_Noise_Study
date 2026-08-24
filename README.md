# Quantum Teleportation Under Noise

A small computational study exploring how quantum noise affects
the performance of quantum teleportation using Qiskit.

## Experiment 1: Bit-Flip Noise

### Objective

To investigate how increasing bit-flip noise affects the
success rate of quantum teleportation.

### Setup

- Framework: Qiskit
- Simulator: Qiskit Aer
- Input state: |0⟩
- Number of qubits: 3
- Shots per configuration: 1000
- Noise model: Bit-flip noise
- Noise range: 0%–20%

### Results

The teleportation success rate decreased as the probability
of bit-flip noise increased.

| Noise Probability | Success Rate |
|---:|---:|
| 0% | 100.0% |
| 2% | 95.5% |
| 4% | 92.1% |
| 6% | 89.6% |
| 8% | 84.0% |
| 10% | 81.2% |
| 12% | 78.2% |
| 14% | 76.9% |
| 16% | 71.5% |
| 18% | 70.9% |
| 20% | 67.1% |

### Observation

Increasing the bit-flip noise probability resulted in a
decrease in the probability of successful teleportation.

### Future Work

- Study depolarizing noise
- Test different input states
- Compare different noise models
