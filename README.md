# Quantum Wave Packet Simulation in a Double Barrier Potential

A Python implementation for simulating the propagation of a one-dimensional Gaussian wave packet through a double potential barrier by numerically solving the **Time-Dependent Schrödinger Equation (TDSE)** using the **Crank–Nicolson finite-difference method**.

The simulation demonstrates fundamental quantum phenomena including **wave packet propagation**, **quantum tunneling**, **partial reflection**, **transmission**, and **resonant tunneling**. The Crank–Nicolson method provides an implicit, second-order accurate, and unconditionally stable numerical scheme that preserves the normalization of the wave function throughout the simulation.

## Governing Equation

The dynamics of the quantum particle are governed by the one-dimensional **Time-Dependent Schrödinger Equation (TDSE)** (atomic units: $\hbar = m = 1$):

<img src="https://latex.codecogs.com/svg.image?i\frac{\partial\psi(x,t)}{\partial%20t}=\left(-\frac12\frac{\partial^2}{\partial%20x^2}+V(x)\right)\psi(x,t)" />

where

- $\psi(x,t)$ is the complex wave function.
- $V(x)$ is the external potential.
- $-\dfrac{1}{2}\dfrac{\partial^2}{\partial x^2}$ is the kinetic energy operator.

The probability density is

$$
|\psi(x,t)|^2
$$

which gives the probability of finding the particle at position $x$.

## Initial Gaussian Wave Packet

The initial wave function is

$$
\psi(x,0)=
\frac{1}{(2\pi\sigma_0^2)^{1/4}}
\exp\left(-\frac{(x-x_0)^2}{4\sigma_0^2}\right)
\exp(i k_0 x)
$$

where

- $x_0$ is the initial center position.
- $\sigma_0$ is the initial packet width.
- $k_0$ is the initial wave number (momentum).

## Double Barrier Potential

The potential is

$$
V(x)=
\begin{cases}
V_0, & x\in\text{Barrier Regions},\\
0, & \text{otherwise}.
\end{cases}
$$

where

- $V_0$ is the barrier height.
- Each barrier has width $w$.
- The barriers are separated by a gap of width $d$.

## Hamiltonian

The Hamiltonian operator is

$$
H=-\frac{1}{2}\frac{\partial^{2}}{\partial x^{2}}+V(x)
$$

## Crank–Nicolson Method

The time evolution is computed using

```math
\left(I-\frac{\Delta t}{2i}H\right)\psi^{n+1}
=
\left(I+\frac{\Delta t}{2i}H\right)\psi^{n}
```

## Features

- One-dimensional Time-Dependent Schrödinger Equation (TDSE) solver
- Crank–Nicolson implicit time integration
- Sparse Hamiltonian matrix operators
- Double rectangular potential barrier framework
- Gaussian wave packet initialization
- Complex absorbing boundary conditions (ABC) to damp edge reflections
- Real-time Matplotlib animation
- Live runtime tracking of:
  - Transmission probability ($T$)
  - Reflection probability ($R$)
  - Spatial expectation value ($\langle x \rangle$)
