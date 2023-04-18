# TropicalGEMM on GPU
## Difficulty level
Advanced

## Advisor

Jinguo Liu (cacate0129@gmail.com)

## Project Description

Using `CUDA.jl` to implement matrix multiplication (GEMM) for tropical numbers.
In mathematics, tropical algebra is a semiring with the addition replaced with maximization and the multiplication replaced with ordinary addition:
```math
\begin{align}
&x \oplus y = \max\{x, y\},\\
&x \otimes y = x + y.
\end{align}
```
One can find an implementation of tropical GEMM for CPU here:
https://github.com/TensorBFS/TropicalGEMM.jl .
However, a CUDA implementation is still missing.

### References
* Using case: [Tropical Tensor Network for Ground States of Spin Glasses](https://arxiv.org/abs/2008.06888)
* Libraries: [CUDA.jl](https://github.com/JuliaGPU/CUDA.jl) and [TropicalNumbers.jl](https://github.com/TensorBFS/TropicalNumbers.jl)

## Project Output Standard
A working Julia implementation for Tropical GEMM on GPU, with better performance than the existing naive implementation.

## Technical requirements
* CUDA programming (professional),
* Julia language (basic).
