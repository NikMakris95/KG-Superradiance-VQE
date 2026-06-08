# Methodology

## Overview

This project investigates the superradiant instability of massive scalar
fields in Kerr black-hole spacetimes using a hybrid classical–quantum
computational framework.

Starting from the massive Klein–Gordon equation in the Kerr geometry,
the scalar-field perturbation equations are separated into radial and
angular components. The radial equation is transformed into a
Schrödinger-like eigenvalue problem through the introduction of the
tortoise coordinate and an effective potential.

The resulting operator is discretised using finite-difference methods
and analysed numerically to compute quasi-bound states, quasinormal
modes, and superradiant instability growth rates.

---

## 1. Kerr Geometry

The background spacetime is described by the Kerr metric, representing
a rotating black hole with mass \(M\) and angular momentum parameter
\(a\).

Important physical quantities include:

- Event horizon radius
- Ergosphere
- Horizon angular velocity \(\Omega_H\)

---

## 2. Klein–Gordon Equation

Massive scalar perturbations satisfy

\[
(\Box-\mu^2)\Phi=0.
\]

This equation governs the dynamics of a scalar field of mass \(\mu\)
propagating on the Kerr background.

---

## 3. Separation of Variables

Using the standard ansatz

\[
\Phi=e^{-i\omega t}e^{im\phi}S(\theta)R(r),
\]

the Klein–Gordon equation separates into:

- An angular spheroidal-harmonic equation
- A radial Teukolsky-type equation

The angular equation provides separation constants used in the radial
problem.

---

## 4. Tortoise Coordinate and Effective Potential

The radial equation is rewritten using the tortoise coordinate

\[
r_*,
\]

leading to a Schrödinger-like form

\[
\frac{d^2\Psi}{dr_*^2}
+
\left(
\omega^2-V_{\mathrm{eff}}
\right)\Psi=0.
\]

The effective potential determines the existence of quasi-bound states
and superradiant instabilities.

---

## 5. Finite-Difference Discretisation

The radial operator is discretised on a finite computational domain
using second-order finite differences.

This procedure converts the continuous differential equation into a
matrix eigenvalue problem suitable for numerical computation.

---

## 6. Quasinormal Modes and Quasi-Bound States

The discretised operator is solved numerically to obtain:

- Quasinormal-mode frequencies
- Quasi-bound-state frequencies
- Instability growth rates

Comparisons with reference results from Leaver and Dolan are used to
validate the numerical framework.

---

## 7. Superradiant Instability Analysis

The spectrum is analysed as a function of:

- Black-hole spin \(a\)
- Scalar-field mass \(\mu\)

Superradiance occurs when

\[
\omega < m\Omega_H.
\]

Modes with positive imaginary frequency components correspond to
unstable growing solutions associated with black-hole energy
extraction.

---

## 8. Quantum-Compatible Reformulation

To enable compatibility with quantum algorithms, the non-Hermitian
radial operator is embedded into a larger Hermitian system through a
Schrödingerisation procedure.

The resulting Hamiltonian can then be represented on a qubit register
and studied using variational quantum algorithms.