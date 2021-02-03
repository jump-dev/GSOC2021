# GSOC2021

JuMP is a modeling interface and a collection of supporting packages for mathematical optimization that is embedded in Julia. With JuMP, users formulate various classes of optimization problems with easy-to-read code, and then solve these problems using state-of-the-art open-source and commercial solvers. JuMP also makes advanced optimization techniques easily accessible from a high-level language.

[JuMP](https://jump.dev/) will be participating as a sub-organization in [NumFOCUS](http://numfocus.org/)'s application for [Google Summer of Code 2021](https://summerofcode.withgoogle.com/). For more information about this application see:
- [NumFOCUS's main GSoC page](https://github.com/numfocus/gsoc)

## Mentors

- [Oscar Dowson](https://github.com/odow)

## Ideas

_If you have an idea for GSOC2021, please make a pull request to edit this page._

###  Multiobjective optimization

#### Abstract

A key limitation of the current version of JuMP and MathOptInterface is that 
they are limited to problems with a single scalar objective function. The goal 
of this project is to relax this requirement so that users can model and solve 
multi-objective optimization problems.

| **Intensity**                          | **Priority**              | **Involves**  | **Mentors**              |
| -------------                          | ------------              | ------------- | -----------              |
| Moderate  |  Medium  | Adding support for vector-valued objective functions to MOI and JuMP | [Oscar Dowson](https://github.com/odow) |

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
- Revive this solver: https://github.com/odow/MOO.jl. 
  - Add more tests, documentation, and features.
  - Add other multi-objective algorithms

**Stretch goal**
- Extend JuMP's `@objective` macro to work with vector-valued functions.
