# Simplex-Tableau-CSC301

Implementation of Simplex Tableau algorithm in C++, for the  course CSC301 2024-2025.

## Details

- **NAME**: AHMAD TAUFIQ MAIGARI
- **MATRIC NO**: U22CS1016
- **DEPARTMENT**: COMPUTER SCIENCE
- **GROUP**: GROUP 3 (THREE)
- **FACULTY**: FACULTY OF COMPUTING

# Simplex Algorithm in C++

This C++ program implements the **Simplex Algorithm**, a widely-used optimization method for solving linear programming problems. The algorithm finds the optimal solution for a linear programming problem by moving along the edges of the feasible region, improving the objective function at each step until an optimal solution is reached.

## Table of Contents
- [Introduction](#introduction)
- [Description](#description)
- [How it Works](#how-it-works)
- [Usage](#usage)
- [Example](#example)
- [Functions](#functions)
  - [Constructor](#constructor)
  - [printTableau()](#printtableau)
  - [isOptimal()](#isoptimal)
  - [pivot()](#pivot)
  - [solve()](#solve)
- [Dependencies](#dependencies)
- [License](#license)

## Introduction

This program is designed to solve **linear programming** problems in the standard form using the **Simplex Algorithm**. It reads the input coefficients for the constraints and the objective function, constructs the **Simplex tableau**, and performs pivot operations to iteratively optimize the objective function.

The Simplex method is applied to maximize a linear objective function subject to linear constraints.

## Description

The problem is represented in the following canonical form:
- **Maximize**: `c1 * x1 + c2 * x2 + ... + cn * xn`
- **Subject to**: 
  - `a11 * x1 + a12 * x2 + ... + a1n * xn <= b1`
  - `a21 * x1 + a22 * x2 + ... + a2n * xn <= b2`
  - `...`
  - `am1 * x1 + am2 * x2 + ... + amn * xn <= bm`

Where:
- `x1, x2, ..., xn` are the decision variables
- `c1, c2, ..., cn` are the coefficients of the objective function
- `aij` are the coefficients of the constraints
- `b1, b2, ..., bm` are the right-hand side values for each constraint

### Simplex Tableau Structure
The **Simplex Tableau** is a matrix representation of the linear program that holds the current state of the algorithm. It includes:
- Coefficients of variables and slack variables
- The objective function row
- The current solution values

The Simplex algorithm updates this tableau at each iteration by performing pivot operations until an optimal solution is found.

## How it Works

1. **Initialization**: 
   - The program initializes the Simplex tableau with the input data for constraints and the objective function.
   
2. **Pivoting**: 
   - In each iteration, it identifies a pivot column (the variable to be entered into the basis) and a pivot row (the variable to leave the basis).
   
3. **Updating Tableau**: 
   - The pivot operation updates the tableau and prints the updated tableau at each step.
   
4. **Termination**: 
   - The algorithm stops when all the coefficients in the objective function row are non-negative, meaning an optimal solution has been reached.

## Usage

To run the program, compile it using a C++ compiler and execute the binary. The program will output the current Simplex tableau at each iteration and eventually provide the optimal solution.

```bash
g++ -o simplex simplex.cpp
./simplex

```


## Example
For the following linear program:

Maximize:
3 * x1 + 5 * x2

Subject to:

2 * x1 + 1 * x2 <= 20
1 * x1 + 2 * x2 <= 20
The program will output the tableau at each iteration and eventually print the optimal solution.


```bash
Current Simplex Tableau:
    2.00      1.00      1.00      0.00      0.00      20.00 
    1.00      2.00      0.00      1.00      0.00      20.00 
   -3.00     -5.00      0.00      0.00      0.00      0.00 
Zj Row:
    0.00      0.00      0.00      0.00 
Cj - Zj Row:
   -3.00     -5.00      0.00      0.00 

Optimal solution found.


```
## Functions

# constructor
**Constructor: Simplex(vector<vector<double>> &A, vector<double> &b, vector<double> &c)**
Initializes the Simplex tableau using the constraint matrix A, the right-hand side vector b, and the objective function vector c.

# printTableau
**printTableau()**
Prints the current state of the Simplex tableau, including the Zj row (sum of products of basic variables and the objective function) and Cj - Zj row (difference between the coefficients of the objective function and Zj).

# isOptimal
**isOptimal()**
Checks if the current solution is optimal by verifying if all the coefficients in the objective row are non-negative.
pivot(int pivotRow, int pivotCol)
Performs the pivot operation on the tableau. It selects the pivot element, normalizes the pivot row, and eliminates other entries in the pivot column.

# solve
**solve()**
Solves the linear programming problem by iteratively performing pivot operations until an optimal solution is found. Prints the tableau at each iteration.

## Dependencies

C++11 or higher for the use of vector and iostream libraries.

## License
This project is licensed under the MIT License - see the LICENSE file for details.


