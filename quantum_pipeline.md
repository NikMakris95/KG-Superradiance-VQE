# Quantum Pipeline

## Overview

A central objective of this project is to establish a complete computational
pipeline connecting Kerr black-hole perturbation theory with quantum-compatible
operator formulations. The workflow begins with the classical Klein–Gordon
equation for a massive scalar field propagating in a Kerr spacetime and
culminates in the implementation of a Variational Quantum Eigensolver (VQE)
acting on a reduced qubit Hamiltonian.

The purpose of the quantum component is not to demonstrate quantum advantage,
but rather to provide a proof-of-concept framework showing that the essential
spectral structure of the Kerr superradiance problem can be preserved under
Hermitian embedding, qubit encoding, and variational quantum simulation.

---

## Pipeline Summary

```text
Kerr Geometry
      ↓
Klein–Gordon Equation
      ↓
Separation of Variables
      ↓
Radial Eigenvalue Problem
      ↓
Finite-Difference Discretisation
      ↓
Non-Hermitian Matrix Operator
      ↓
Schrödingerisation
      ↓
Hermitian Hamiltonian
      ↓
Subspace Projection
      ↓
Qubit Encoding
      ↓
Pauli Decomposition
      ↓
Variational Quantum Eigensolver
      ↓
Approximate Eigenvalue Spectrum
```

---

## 1. Kerr Scalar-Field Eigenvalue Problem

The starting point is the massive Klein–Gordon equation

\[
(\Box-\mu^2)\Phi=0,
\]

defined on a Kerr spacetime characterized by black-hole mass \(M\) and
rotation parameter \(a\).

Using the standard separation ansatz

\[
\Phi=e^{-i\omega t}e^{im\phi}S(\theta)R(r),
\]

the field equations separate into:

- an angular spheroidal-harmonic equation,
- a radial Teukolsky-type equation.

The angular equation determines separation constants which enter the radial
problem.

---

## 2. Schrödinger-Like Reformulation

The radial equation is transformed using the tortoise coordinate \(r_*\),
yielding a Schrödinger-like equation of the form

\[
\frac{d^2\Psi}{dr_*^2}
+
\left(
\omega^2-V_{\mathrm{eff}}
\right)\Psi=0.
\]

The effective potential incorporates:

- Kerr frame dragging,
- scalar-field mass effects,
- angular-mode contributions,
- horizon boundary behaviour.

This formulation provides a convenient starting point for numerical analysis.

---

## 3. Finite-Difference Discretisation

The radial operator is discretised on a finite computational grid using
second-order finite differences.

The continuous differential equation becomes a matrix eigenvalue problem

\[
L\psi=\omega\psi.
\]

The resulting matrix operator contains the spectral information associated
with:

- quasinormal modes,
- quasi-bound states,
- superradiant instabilities.

Numerical convergence studies are performed to assess sensitivity to grid
resolution and boundary placement.

---

## 4. Non-Hermitian Nature of the Problem

The discretised radial operator is generally non-Hermitian.

This occurs because:

- outgoing-wave boundary conditions break self-adjointness,
- finite-domain truncation introduces non-symmetric effects,
- instability growth rates are encoded in complex eigenvalues.

Consequently, direct implementation on a quantum computer is not possible
because quantum evolution requires Hermitian generators.

A Hermitian reformulation is therefore required.

---

## 5. Schrödingerisation

To obtain a quantum-compatible representation, the non-Hermitian operator is
embedded into a larger Hermitian system.

Following the Schrödingerisation framework introduced by Jin, Liu, and Yu, an
auxiliary degree of freedom is introduced to construct an enlarged Hermitian
Hamiltonian

\[
H_{\mathrm{Sch}}.
\]

This procedure preserves the physically relevant spectral information while
satisfying the Hermiticity requirements of quantum simulation algorithms.

The embedding represents the key bridge between the classical Kerr
perturbation problem and quantum computational methods.

---

## 6. Reduced Hamiltonian Construction

The Hermitian Hamiltonian is projected onto a finite-dimensional subspace.

This dimensional reduction serves two purposes:

1. It isolates the dominant spectral structure.
2. It produces a matrix size compatible with current quantum simulators.

The present implementation focuses on low-dimensional examples corresponding
approximately to three or four qubits.

While these systems are small, they provide a controlled environment for
testing the full quantum workflow.

---

## 7. Qubit Encoding

The reduced Hamiltonian matrix is mapped onto a qubit basis.

For a system of \(n\) qubits, the Hamiltonian acts on a Hilbert space of
dimension

\[
2^n.
\]

The matrix representation is therefore rewritten in a form suitable for
quantum-circuit implementation.

The goal is not large-scale simulation but verification that the essential
spectral features remain accessible after qubit encoding.

---

## 8. Pauli Decomposition

Any Hermitian qubit Hamiltonian can be expressed as a weighted sum of Pauli
operators

\[
H = \sum_i c_i P_i,
\]

where:

- \(c_i\) are real coefficients,
- \(P_i\) are tensor products of Pauli matrices.

Examples include:

\[
I,\quad X,\quad Y,\quad Z,\quad X\otimes Z,\quad Y\otimes Y.
\]

The Pauli decomposition provides the operator form required by modern quantum
software frameworks such as PennyLane and Qiskit.

---

## 9. Variational Quantum Eigensolver

The eigenvalue problem is solved using a Variational Quantum Eigensolver
(VQE).

The implementation employs a hardware-efficient ansatz consisting of:

- \(R_y\) rotation gates,
- \(R_z\) rotation gates,
- CNOT entangling gates.

A classical optimizer adjusts the variational parameters

\[
\theta=(\theta_1,\theta_2,\ldots),
\]

to minimize the expectation value

\[
E(\theta)=
\langle\psi(\theta)|H|\psi(\theta)\rangle.
\]

The minimum value approximates the lowest eigenvalue of the Hamiltonian.

---

## 10. Validation Against Classical Results

The VQE spectrum is compared with classical eigenvalues obtained from direct
matrix diagonalization.

The comparison demonstrates:

- recovery of dominant oscillation frequencies,
- preservation of low-lying spectral structure,
- convergence of the variational procedure.

The agreement supports the validity of the Hermitian embedding and qubit
representation.

---

## 11. Limitations

Several important limitations remain:

- Simulations are restricted to approximately 3–4 qubits.
- No quantum computational advantage is demonstrated.
- Imaginary frequency components are more difficult to recover accurately.
- Large-scale Kerr simulations remain beyond current hardware capabilities.

Accordingly, the present work should be interpreted as a proof-of-concept
rather than a production-scale quantum simulation.

---

## Significance

The principal contribution of this project lies not in computational scale
but in establishing a physically consistent end-to-end pipeline linking Kerr
black-hole perturbation theory with quantum-compatible operator formulations.

The workflow demonstrates that essential features of quasinormal modes,
quasi-bound states, and superradiant spectra can survive dimensional
reduction and Hermitian embedding, thereby providing a foundation for future
investigations of gravitational systems using quantum computational methods.