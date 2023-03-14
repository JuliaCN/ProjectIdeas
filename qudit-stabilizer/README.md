# Qudit stabilizer simulator

## Advisor

Chen Zhao (czhao.cz44@gmail.com)

## Description

By the Gottesman-Knill theorem, stabilizer states can be classical simulated in polynomial time. 
This result not only holds in the case of qubit but can be also generalized to the case of qudits. 
However, all current stabilizer simulators, including [Stim](https://github.com/quantumlib/Stim) and [QuantumClifford.jl](https://github.com/Krastanov/QuantumClifford.jl), focus on the case of qubit.
In this project, we are going to implement a Julia package for simulating stabilizer states of general qudits. 
It will include following features.
- Tableau representation of general qudit stabilizer states (both pure and mixed states)
- Qudit Clifford gates and Pauli measurements as tableau operations
- Random Clifford circuits and stabilizer states generation
- Entanglement entropy computation for stabilizer states

## Requirements

- Knowledge of the theory of stabilizer states
- Basic knowledge of modular arithmetic (basic abstract algebra or elementary number theory)
- Basic knowledge in Julia programming language

## Reference

- Related packages: [QuantumClifford.jl](https://github.com/Krastanov/QuantumClifford.jl)
- [Qudit stabilizer states](http://arxiv.org/abs/quant-ph/0408190)
