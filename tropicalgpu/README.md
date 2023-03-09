## Advisor

Jinguo Liu (cacate0129@gmail.com)

## Description

Using `CUDA.jl` to implement GEMM for tropical numbers.
In mathematics, tropical algebra is a semiring with the addition replaced with maximization and the multiplication replaced with ordinary addition:
```math
\begin{align}
&x \oplus y = \max\{x, y\},\\
&x \otimes y = x + y.
\end{align}
```
One can find the corresponding CPU version here:
https://github.com/TensorBFS/TropicalGEMM.jl

### References
* Using case: [Tropical Tensor Network for Ground States of Spin Glasses](https://arxiv.org/abs/2008.06888)
* Libraries: [CUDA.jl](https://github.com/JuliaGPU/CUDA.jl)

### Required knowledge
* CUDA programming (professional),
* Julia language (basic).