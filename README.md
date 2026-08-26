# Heat Transfer Modeling

This project uses the one-dimensional heat equation to model how temperature changes inside a material over time. I solved the equation numerically with an explicit finite-difference method.

I started with a simple rod model, then used the same method for a reentry-inspired example that compares two thermal diffusivity values.

![Heat spreading over time](figures/figure_02.png)

## Model

The heat equation is

$$
\frac{\partial T}{\partial t}=\alpha\frac{\partial^2 T}{\partial x^2},
$$

where $T(x,t)$ is temperature and $\alpha$ is thermal diffusivity.

For the explicit method to remain stable, the time step must satisfy

$$
\frac{\alpha\Delta t}{\Delta x^2}\leq 0.5.
$$

The notebook checks this value before running the simulation.

## What I compared

The first part of the notebook shows how an initial temperature profile spreads through a rod.

The second part compares a lower-diffusivity material with a higher-diffusivity case. The higher value spreads a surface hot spot more quickly, while the lower value slows the movement of heat toward the interior. This is a simplified model, but it shows why material choice involves a tradeoff rather than one value always being better.

![Peak and interior temperatures](figures/figure_03.png)

## Files

- `heat_transfer_modeling.ipynb`: the numerical model and plots
- `figures/`: figures produced from the notebook
- `requirements.txt`: Python packages needed to run it

## Tools

Python, NumPy, Matplotlib, partial differential equations, and finite differences

## Run the notebook

```bash
pip install -r requirements.txt
jupyter notebook heat_transfer_modeling.ipynb
```
