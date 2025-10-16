# Quantum Circuit Overview

This section introduces a simple quantum circuit with one Hadamard gate followed by a controlled-NOT (CNOT) gate.

![Quantum Circuit](https://example.com/images/quantum-circuit.png)

## Mathematical Formulation

The state after applying the Hadamard gate to \(|0\rangle\) becomes:

$$
|\psi\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)
$$

When the CNOT gate acts on \(|\psi\rangle \otimes |0\rangle\), the resulting entangled Bell state is:

$$
|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)
$$

## Python Simulation

```python
from qiskit import QuantumCircuit, Aer, execute

qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)

backend = Aer.get_backend("statevector_simulator")
result = execute(qc, backend).result()
statevector = result.get_statevector(qc)
print(statevector)
```

## Additional Notes

- Remember to install `qiskit` before running the simulation.
- The image above provides a visual representation of the circuit layout.
- Ensure the markdown translator preserves LaTeX equations, code blocks, and image links.
