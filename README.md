# GSOC2021

JuMP is a modeling interface and a collection of supporting packages for mathematical optimization that is embedded in Julia. With JuMP, users formulate various classes of optimization problems with easy-to-read code, and then solve these problems using state-of-the-art open-source and commercial solvers. JuMP also makes advanced optimization techniques easily accessible from a high-level language.

[JuMP](https://jump.dev/) will be participating as a sub-organization in [NumFOCUS](http://numfocus.org/)'s application for [Google Summer of Code 2021](https://summerofcode.withgoogle.com/). For more information about this application see:
- [NumFOCUS's main GSoC page](https://github.com/numfocus/gsoc)

## Mentors

- [Oscar Dowson](https://github.com/odow)
- [Joaquim Dias Garcia](https://github.com/joaquimg)
- [Mathieu Besançon](https://github.com/matbesancon)
- [Benoît Legat](https://github.com/blegat)

## Ideas

_If you have an idea for GSOC2021, please make a pull request to edit this page._

###  Multiobjective optimization

#### Abstract

A key limitation of the current version of JuMP and MathOptInterface is that 
they are limited to problems with a single scalar objective function. The goal 
of this project is to relax this requirement so that users can model and solve 
multi-objective optimization problems.

| **Priority** | **Involves** | **Mentors** |
| ------------ | ------------ | ----------- |
|  Medium  | Adding support for vector-valued objective functions to MOI and JuMP | [Oscar Dowson](https://github.com/odow) |

#### Technical Details

Technical details available in this [issue](https://github.com/jump-dev/JuMP.jl/issues/2099)

#### Helpful Experience

- Knowledge of JuMP and MathOptInterface
- Knowledge of multi-objective optimization

#### Steps

**Initial steps**
- Read [Issue 2099](https://github.com/jump-dev/JuMP.jl/issues/2099)
- Become familiar with previous attempts at vector-valued objectives in JuMP https://github.com/anriseth/MultiJuMP.jl

**Key deliverables**
- Add tests, documentation, and features for vector-valued objective problems to MathOptInterface.
  - Here was the start of a previous attempt: https://github.com/jump-dev/MathOptInterface.jl/pull/968.
  - Also a reader for the MOP file format: https://github.com/odow/MathOptFormat.jl/pull/95
- Revive this solver for proof-of-concept: https://github.com/odow/MOO.jl. 
  - Add more tests, documentation, and features.
  - Add other multi-objective algorithms

**Stretch goal**
- Extend JuMP's `@objective` macro to work with vector-valued functions.
- Add support for [vOptSolver](https://github.com/vOptSolver/vOptGeneric.jl)

### Matrix-based representation of optimization problems

| **Priority** | **Involves** | **Mentors** |
| ------------ | ------------ | ----------- |
|  Medium  | Implementation of problem matrix representations and integration in solvers | [Joaquim Dias Garcia](https://github.com/joaquimg),  [Mathieu Besançon](https://github.com/matbesancon), [Benoît Legat](https://github.com/blegat)|

#### Abstract

Many classes of optimization problems are commonly represented using matrices of parameters:

```
l ≤ A x ≤ u
```

These representations can be what optimization solvers require as input or used to transform
optimization problems, for example to derive its dual problem or its KKT conditions.
We want to develop [MatrixOptInterface.jl](https://github.com/jump-dev/MatrixOptInterface.jl/)
to federate efforts to build various representations of optimization problems in matrix form.

#### Technical details

The core of the project will the implementation of matrix representations for optimization problems.
These representations can then be used to simplify the code in solver wrappers transforming a
MathOptInterface model into structures that are passed to the native solver.  

Beyond the implementation of the various matrix forms, this project will lead possibilities to
work on various connected packages such as solver wrappers,
[Dualization.jl](https://github.com/jump-dev/Dualization.jl),
[DiffOpt.jl](https://github.com/jump-dev/DiffOpt.jl), or
[ParametricOptInterface.jl](https://github.com/jump-dev/ParametricOptInterface.jl).

#### Helpful Experience

- Knowledge of mathematical optimization (linear, quadratic optimization, duality)
- Basic knowledge of MathOptInterface

#### Steps

**Initial steps**

- Read the MathOptInterface manual and get familiar with the data structures used to represent scalar and vector functions
- Read on the models already implemented in [matrix form](https://github.com/jump-dev/MatrixOptInterface.jl/)

**Key deliverables**

- Implement various forms for linear, conic and quadratic optimization problems in MatrixOptInterface
- Design user-oriented documentation for building and consuming the various problem formats
- Replace the conversion code from MOI structures in solvers with the MatrixOptInterface implementation

**Stretch goals**

- Integrate MatrixOptInterface in ParametricOptInterface, Dualization.jl, DiffOpt.jl, BilevelJuMP.jl
