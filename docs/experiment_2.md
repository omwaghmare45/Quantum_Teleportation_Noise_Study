# Experiment 2 — Depolarizing Noise

**Date:** 24 August 2026

## 1. Objective

Investigate how depolarizing noise affects the success of
quantum teleportation and compare its effect with the bit-flip
noise studied in Experiment 1.

## 2. Research Question

How does increasing depolarizing noise affect the probability
of successfully teleporting a quantum state?

## 3. Background

Depolarizing noise is a quantum noise model in which a quantum
state can be affected by different types of Pauli errors,
including X, Y, and Z errors.

Unlike the bit-flip model used in Experiment 1, which introduces
only X errors, depolarizing noise represents a more general form
of quantum error.

## 4. Experimental Setup

- Framework: Qiskit
- Simulator: Qiskit Aer
- Number of qubits: 3
- Input state: |0⟩
- Shots per configuration: 1000
- Noise model: Depolarizing noise
- Noise probabilities: 0% to 20%
- Noise interval: 2%

Depolarizing noise was applied to the H and CNOT operations in
the teleportation circuit.

## 5. Hypothesis

Increasing the depolarizing noise parameter will decrease the
probability of successfully teleporting the quantum state.

## 6. Results

| Noise Probability | Success Rate |
|---:|---:|
| 0% | 100.0% |
| 2% | 98.3% |
| 4% | 96.1% |
| 6% | 94.4% |
| 8% | 92.2% |
| 10% | 90.5% |
| 12% | 86.3% |
| 14% | 86.6% |
| 16% | 85.9% |
| 18% | 82.7% |
| 20% | 82.8% |

## 7. Comparison with Experiment 1

At a noise parameter of 10%:

- Bit-flip noise: 81.2% success
- Depolarizing noise: 90.5% success

At 20%:

- Bit-flip noise: 67.1% success
- Depolarizing noise: 82.8% success

Under the noise parameterization used in these simulations,
depolarizing noise produced higher teleportation success rates
than bit-flip noise across the tested range.

However, the noise parameters of the two different channels
should not automatically be interpreted as equivalent physical
error probabilities.

## 8. Observations

The teleportation success rate generally decreased as the
depolarizing noise parameter increased.

Small fluctuations were observed between neighboring noise
levels. For example, the success rate increased slightly from
86.3% at 12% noise to 86.6% at 14% noise. This is expected from
the statistical variation associated with a finite number of
shots.

The comparison with Experiment 1 showed that the bit-flip noise
model produced a larger reduction in measured teleportation
success under the parameterization used in these experiments.

## 9. Conclusion

The experiment supports the hypothesis that increasing
depolarizing noise reduces the success of quantum teleportation.

The comparison also shows that different noise models can have
different effects on the observed performance of the same
quantum circuit.

## 10. Limitations

- The experiment was performed using a simulator rather than
  physical quantum hardware.
- Only the |0⟩ input state was tested.
- Each configuration used 1000 shots.
- Only one depolarizing noise parameterization was investigated.
- The noise parameter cannot be directly interpreted as an
  equivalent physical error probability across different noise
  models.

## 11. Future Work

- Test additional input quantum states.
- Compare teleportation performance across different input
  states.
- Investigate additional noise models.
- Study teleportation fidelity rather than only measurement
  success.
- Investigate the experiment using real quantum hardware.
