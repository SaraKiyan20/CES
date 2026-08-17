# Optimization Algorithms from Scratch

Six optimization algorithms implemented from scratch and compared on the
[Rosenbrock function](https://en.wikipedia.org/wiki/Rosenbrock_function) — a standard non-convex
benchmark with a narrow, curved valley that makes it a good stress test for optimizers. Its global
minimum is at (1, 1), where f = 0.

## Contents

**Gradient-based** (using the analytical gradient):
- Gradient Descent
- Momentum
- Adam
- RMSprop

**Gradient-free:**
- Genetic Algorithm (tournament selection, arithmetic crossover, Gaussian mutation)
- Simulated Annealing

All six are compared directly: convergence curves (loss vs. iteration/generation, log scale),
optimizer paths overlaid on the function's contour lines, and a Genetic-Algorithm / Simulated-Annealing
comparison against the gradient-based methods.

## Getting started

```bash
pip install -r requirements.txt
jupyter notebook optimization_algorithms_from_scratch.ipynb
```

No external data — everything is generated in the notebook itself.

## Notes

- `gradient_descent`, `momentum_gradient_descent`, `adam_gradient_descent`, and
  `rmsprop_gradient_descent` all accept `a` and `b` parameters (the Rosenbrock function's shape
  constants) but originally never passed them through to `analytical_gradient()`, which silently used
  its own defaults (`a=1, b=100`) regardless. This had no visible effect in this notebook, since every
  call uses the default Rosenbrock shape anyway — but it meant the `a`/`b` parameters didn't actually
  do anything for the gradient-based methods, unlike the gradient-free methods where they work
  correctly. Fixed here so all six methods respect custom `a`/`b` consistently.
