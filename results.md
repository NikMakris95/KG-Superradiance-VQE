# Results

## Overview

Classical and quantum simulations were performed to investigate
superradiant scalar-field dynamics in Kerr black-hole spacetimes.

The results demonstrate the existence of unstable modes satisfying the
superradiant condition and establish a proof-of-concept quantum
representation of the problem.

---

# Classical Results

## Quasinormal Modes

The finite-difference framework reproduces the dominant oscillatory
structure of Kerr scalar-field quasinormal modes.

Comparisons with Leaver reference frequencies show reasonable
agreement in the real parts of the frequencies while highlighting the
known sensitivity of imaginary components to boundary truncation.

---

## Quasi-Bound States

Massive scalar fields produce localized quasi-bound states around the
black hole.

Several bound-state frequencies were identified and tracked across
different physical parameters.

---

## Superradiant Growth Rates

Instability growth rates were computed as functions of:

- Black-hole spin \(a\)
- Scalar-field mass \(\mu\)

The simulations identify unstable modes satisfying

\[
\omega < m\Omega_H.
\]

Positive imaginary frequency components indicate exponential growth of
the field amplitude.

---

## Black-Hole Bomb Behaviour

The results illustrate the confinement mechanism responsible for the
black-hole-bomb instability.

Massive fields can remain trapped near the black hole and repeatedly
extract rotational energy through superradiant scattering.

---

# Quantum Results

## Hermitian Embedding

The Schrödingerisation procedure successfully transforms the
non-Hermitian radial operator into a Hermitian Hamiltonian suitable
for quantum computation.

---

## Pauli Decomposition

The reduced Hamiltonian was decomposed into weighted sums of Pauli
strings, enabling implementation on a qubit-based quantum simulator.

---

## Variational Quantum Eigensolver

Low-dimensional Hamiltonians were encoded into systems involving
approximately 3–4 qubits.

A hardware-efficient variational ansatz was used to estimate the
lowest eigenvalues of the embedded Hamiltonian.

---

## Spectral Recovery

The VQE reproduces the dominant spectral structure of the reduced Kerr
Hamiltonian and converges toward classical reference eigenvalues.

The simulations demonstrate that key features of quasi-bound states
and superradiant spectra remain identifiable after dimensional
reduction.

---

## Main Outcome

This work establishes a complete end-to-end pipeline from the Kerr
scalar-field eigenvalue problem to a Variational Quantum Eigensolver
implementation.

The results should be interpreted as a proof-of-concept demonstration
of compatibility between Kerr black-hole perturbation theory and
hybrid quantum eigensolver frameworks rather than as evidence of
quantum computational advantage.