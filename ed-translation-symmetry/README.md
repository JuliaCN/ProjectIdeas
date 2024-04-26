# Exact Diagonalization for Quantum Lattice Systems with Translation Symmetry

## Difficulty Level
Advanced

## Advisor

Zhao-Long Gu (waltergu1989@gmail.com)

## Description

The Exact Diagonalization (ED) method stands as a basic quantum many-body algorithm for quantum lattice systems. As the dimension of the Hilbert space grows exponentially with lattice size, ED typically accommodates systems ranging from just a few to several dozen lattice sites, contingent on the nature of the internal quantum spaces. To enhance the efficiency of ED, utilization of the symmetries inherent in a quantum lattice system can significantly reduce the Hilbert space dimension by one to two orders of magnitude. Generally, two types of symmetries are employed: particle number conservation and translation symmetry. In the [ExactDiagonalization.jl](https://github.com/Quantum-Many-Body/ExactDiagonalization.jl) package, particle number conservation has already been integrated. This project seeks to further implement the translation symmetry for improved performance.

## Project Output Standard
A working Julia implementation for the exact diagonalization method for fermionic and hard-core bosonic lattice systems, utilizing translation symmetry and compatible with particle number conservation.

## Requirements
* Familiar with Julia
* Knowledge of condensed matter physics at the graduate level

## References
- Related packages: [ExactDiagonalization.jl](https://github.com/Quantum-Many-Body/ExactDiagonalization.jl), [QuantumLattices.jl](https://github.com/Quantum-Many-Body/QuantumLattices.jl)
- [Exact Diagonalization Techniques](https://doi.org/10.1007/978-3-540-74686-7_18)