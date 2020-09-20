A repository for the ISO on Quantum Programming. The goal of the project was to implement several gates while respecting the complexity constraints.

## Abstract

In this work, we design a generic quantum circuit to implement a recommendation system following the algorithm of Kerenidis and Prakash. This algorithm takes as input a <img src="https://render.githubusercontent.com/render/math?math=m\times n"> binary matrix which has a good rank-<img src="https://render.githubusercontent.com/render/math?math=k"> approximation and returns a product recommendation for an user in time <img src="https://render.githubusercontent.com/render/math?math=O(\log(k)\,\mathrm{polylog}(m\,n))">.
We discuss the limitations of implementing this algorithm on a real quantum computer and the differences between the high-level description of the algorithm and its low-level implementation. In particular, we discuss the reasons that could improve our design’s complexity in the future.

## Gates implementation

### Loading from QRAM

QRAM is a quantum memory storage structure that allows to create a quantum state associated to an arbitrary unitary real vector. That is, given a vector <img src="https://render.githubusercontent.com/render/math?math=x\in\mathbf{R}^{2^p}">, we want to define a gate <img src="https://render.githubusercontent.com/render/math?math=\mathbf{L}_x"> such that <img src="https://render.githubusercontent.com/render/math?math=\mathbf{L}_x|0\rangle^{\otimes p}=|x\rangle">, where <img src="https://render.githubusercontent.com/render/math?math=|x\rangle"> is a quantum state whose amplitudes are coefficients of <img src="https://render.githubusercontent.com/render/math?math=x">.

### Separating quantum states according to a threshold

Given <img src="https://render.githubusercontent.com/render/math?math=\sigma\in\mathbf{R}">, we want to design efficiently the gate <img src="https://render.githubusercontent.com/render/math?math=\mathbf{T}_{\sigma}"> such that <img src="https://render.githubusercontent.com/render/math?math=\mathbf{T}_{\sigma}|t\rangle|0\rangle=\begin{cases}|t\rangle|0\rangle%26\text{if }t<\sigma\\|t\rangle|1\rangle%26\text{otherwise}\end{cases}">. In order to do this, we design an algorithm that allows to compare a quantum state and a real number efficiently.

## Installation

In order to test out the code in the notebooks, just run the following command to install `cirq` and `jupyter`. Note that the Python version you are using must be at least 3.6.0.

```shell bash
pip install jupyter cirq
```
