# Quantum Wave Packet Simulation in a Double Barrier Potential

A Python implementation for simulating the propagation of a one-dimensional Gaussian wave packet through a double potential barrier by numerically solving the **Time-Dependent Schrödinger Equation (TDSE)** using the **Crank–Nicolson finite-difference method**.

The simulation demonstrates fundamental quantum phenomena including **wave packet propagation**, **quantum tunneling**, **partial reflection**, **transmission**, and **resonant tunneling**. The Crank–Nicolson method provides an implicit, second-order accurate, and unconditionally stable numerical scheme that preserves the normalization of the wave function throughout the simulation.

## Governing Equation

The dynamics of the quantum particle are governed by the one-dimensional **Time-Dependent Schrödinger Equation (TDSE)** (atomic units: $\hbar = m = 1$):

$$
i\frac{\partial \psi(x,t)}{\partial t}
=
\left[
-\frac{1}{2}\frac{\partial^2}{\partial x^2}
+
V(x)
\right]
\psi(x,t)
$$

where

- $\psi(x,t)$ is the complex wave function.
- $V(x)$ is the external potential.
- $-\dfrac{1}{2}\dfrac{\partial^2}{\partial x^2}$ is the kinetic energy operator.

The probability density is

$$
|\psi(x,t)|^2
$$

which gives the probability of finding the particle at position $x$.
