# A Julia package for problem reduction between computational hard problems

## Difficulty Level
Advanced

## Advisor

Jinguo Liu (cacate0129@gmail.com)

## Description

This project is about implementing a fundational package for studying computational complexity, which is about the reduction between different computational hard problems.
Although, the reduction between different computational hard problems has been well studied in the literature, there hasn't been a pacakge that summarizes these reduction processes.
In the previous research[^Liu2023], researchers uncovered a significant link between reasoning and Tropical algebra.
They successfully transformed challenging constraint satisfaction problems into Tropical tensor networks.
To future explore the capability of tropical tensor networks, the reduction between problems plays a central role.

## Project Output Standard
- Create a package with computational hard problems and the reduction rules between these problems. We require the package to have
    - test coverage > 80%
    - a proper documentation
    - the problem set must cover those needed by package GenericTensorNetworks.jl
    - reduction complexity informed
- Make this package a dependency of GenericTensorNetworks.jl.
- Production of a research report or paper (results not guaranteed).  

## Technical Requirements
* Familiar with Julia
* Interested in computational complexity

## GitHub Repository
* https://github.com/GiggleLiu/ProblemReductions.jl

## References
[^Liu2023]: Liu, Jin-Guo, et al. "Computing solution space properties of combinatorial optimization problems via generic tensor networks." SIAM Journal on Scientific Computing 45.3 (2023): A1239-A1270.
