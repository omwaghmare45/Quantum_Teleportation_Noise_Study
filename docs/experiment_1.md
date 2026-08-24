# Experiment 1 — Bit-Flip Noise

**Date:** 24 August 2026

## 1. Objective

Investigate how increasing bit-flip noise affects the success
of quantum teleportation.

## 2. Research Question

How does the probability of bit-flip noise affect the probability
of successfully teleporting a quantum state?

## 3. Background

Quantum teleportation transfers an unknown quantum state from
one qubit to another using an entangled pair, classical
communication, and conditional quantum operations.

In this experiment, the state |0⟩ was prepared on the first qubit
and teleported to Bob's qubit.

The first two qubits are measured by Alice. Their classical
measurement results determine whether X and/or Z corrections
are applied to Bob's qubit.

## 4. Experimental Setup

- Framework: Qiskit
- Simulator: Qiskit Aer
- Number of qubits: 3
- Input state: |0⟩
- Shots per configuration: 1000
- Noise model: Bit-flip noise
- Noise probabilities: 0% to 20%
- Noise interval: 2%

Bit-flip noise was applied to the H and CNOT operations in the
teleportation circuit.

## 5. Hypothesis

Increasing the probability of bit-flip noise will decrease the
probability of successfully teleporting the quantum state.

## 6. Results

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

## 7. Observations

The teleportation success rate decreased as the probability of
bit-flip noise increased.

At 0% noise, Bob successfully measured the expected state in
all 1000 shots.

At 20% noise, the success rate decreased to 67.1%.

The measurement-distribution plots also show an increasing
number of incorrect outcomes as the noise probability increases.

## 8. Conclusion

The experiment supports the hypothesis that increasing
bit-flip noise reduces the success of quantum teleportation.

This demonstrates the sensitivity of a quantum communication
protocol to errors introduced during quantum operations.

## 9. Limitations

- The experiment was performed using a simulator rather than
  physical quantum hardware.
- Only bit-flip noise was investigated.
- Only the |0⟩ input state was tested.
- Each configuration used 1000 shots.

## 10. Future Work

- Investigate depolarizing noise.
- Test different input quantum states.
- Compare different noise models.
- Study the effect of noise on teleportation fidelity.
- Investigate the experiment using real quantum hardware.
