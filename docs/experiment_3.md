# Experiment 3 — Input-State Dependence Under Depolarizing Noise

**Date:** 24 August 2026

## 1. Objective

To investigate whether the quantum state being teleported affects
the fidelity of quantum teleportation under increasing depolarizing
noise.

Three input states were investigated:

- |0>
- |1>
- |+> = (|0> + |1>) / sqrt(2)

## 2. Research Question

Does the input quantum state affect teleportation fidelity when the
same depolarizing noise is applied to the teleportation circuit?

## 3. Background

Quantum teleportation transfers an unknown quantum state from one
qubit to another using entanglement and classical communication.

In Experiments 1 and 2, the input state was fixed to |0>. This
experiment extends the study by changing the input state while
keeping the teleportation protocol and noise model consistent.

The |+> state is a superposition state, unlike |0> and |1>, which
are computational-basis states.

## 4. Experimental Setup

- Framework: Qiskit
- Simulator: Qiskit Aer
- Number of qubits: 3
- Input states: |0>, |1>, |+>
- Shots per noise level: 1000
- Noise model: Depolarizing noise
- Noise range: 0%–20%
- Noise interval: 2%
- Noise applied to: H and CNOT operations

The input states were initialized directly using Qiskit's
state-initialization operation to avoid introducing additional
noisy preparation gates that could unfairly affect the comparison.

## 5. Evaluation Metric

Unlike Experiments 1 and 2, where computational-basis measurement
success was used, this experiment evaluates the quality of
teleportation using quantum-state fidelity.

State fidelity measures how closely Bob's final quantum state
matches the original input state.

A fidelity of:

- 1 indicates a perfect match.
- 0 indicates no overlap with the target state.

The density matrix of Bob's qubit was extracted from the simulator
and compared with the corresponding target state.

## 6. Results

### |0> State

| Noise Probability | Fidelity |
|---:|---:|
| 0% | 1.000 |
| 2% | 0.981 |
| 4% | 0.962 |
| 6% | 0.932 |
| 8% | 0.935 |
| 10% | 0.916 |
| 12% | 0.884 |
| 14% | 0.893 |
| 16% | 0.852 |
| 18% | 0.834 |
| 20% | 0.830 |

### |1> State

| Noise Probability | Fidelity |
|---:|---:|
| 0% | 1.000 |
| 2% | 0.980 |
| 4% | 0.970 |
| 6% | 0.932 |
| 8% | 0.929 |
| 10% | 0.908 |
| 12% | 0.898 |
| 14% | 0.867 |
| 16% | 0.852 |
| 18% | 0.865 |
| 20% | 0.824 |

### |+> State

| Noise Probability | Fidelity |
|---:|---:|
| 0% | 1.000 |
| 2% | 0.957 |
| 4% | 0.928 |
| 6% | 0.891 |
| 8% | 0.843 |
| 10% | 0.829 |
| 12% | 0.799 |
| 14% | 0.800 |
| 16% | 0.747 |
| 18% | 0.713 |
| 20% | 0.708 |

## 7. Observations

Teleportation fidelity generally decreased as the depolarizing
noise parameter increased for all three input states.

The computational-basis states |0> and |1> showed similar
fidelity trends.

The |+> state consistently exhibited lower fidelity than |0> and
|1> over most of the tested noise range.

At 20% depolarizing noise:

- |0> fidelity = 83.0%
- |1> fidelity = 82.4%
- |+> fidelity = 70.8%

Thus, the difference between the |+> state and the computational
basis states becomes more noticeable at higher noise levels.

Small increases in fidelity at some neighboring noise levels were
observed. These fluctuations are expected because the simulations
use a finite number of shots.

## 8. Key Finding

Under the simulated circuit and noise configuration, the |+>
input state exhibited lower teleportation fidelity than the
computational-basis states |0> and |1> as the depolarizing-noise
parameter increased.

At 20% noise, the fidelity difference was approximately:

- |0> vs |+>: 12.2 percentage points
- |1> vs |+>: 11.6 percentage points

## 9. Limitations

- The experiment was performed using a simulator rather than
  physical quantum hardware.
- Each noise configuration used 1000 shots.
- Only three input states were investigated.
- Only depolarizing noise was considered in this experiment.
- The results depend on the particular teleportation circuit and
  noise configuration used.
- The depolarizing-noise parameter should not automatically be
  interpreted as a direct physical error probability.

## 10. Conclusion

The experiment demonstrates that teleportation fidelity can depend
on the input quantum state under a given noise configuration.

As the depolarizing-noise parameter increased, all three states
experienced reduced fidelity. However, the |+> superposition state
showed a greater reduction in fidelity than the computational-basis
states |0> and |1>.

This experiment extends the earlier noise analysis by showing that
studying only one input state may not provide a complete picture of
the performance of a quantum teleportation protocol under noise.

## 11. Future Work

Possible extensions include:

- Testing additional superposition states.
- Investigating arbitrary single-qubit states.
- Comparing additional quantum noise models.
- Studying the effect of noise on individual gates.
- Repeating the experiments using real quantum hardware.
- Increasing the number of shots to reduce statistical fluctuations.
