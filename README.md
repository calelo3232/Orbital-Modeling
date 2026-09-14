# Orbital Modeling

A set of numerical simulations of gravitational orbital mechanics in Python, built to practice solving systems of ODEs with `scipy.integrate.solve_ivp`. All three simulations live in [`436project.ipynb`](436project.ipynb).

## What's inside

**Two-Body Orbital System** &mdash; two fixed point masses exert gravity on a smaller test body; each axis is integrated independently and the resulting path is plotted against the two fixed bodies.

**Three-Body Gravitational Simulation** &mdash; a full three-body system (`M1`, `M2`, `M3`) integrated with `solve_ivp` (RK45) and animated with `matplotlib.animation.FuncAnimation`, rendered to `orbit.mp4` and displayed inline. In the current configuration the two more massive bodies spiral into each other over time; see the notebook's Future Work note for why.

**Orbital Transfer Between Fixed Bodies** &mdash; a small moving body is transferred between two fixed masses by applying thrust in stages (unstable orbit &rarr; burn toward the target &rarr; reversing burn &rarr; coast into a new orbit), showing that a roughly stable transfer can be constructed this way even though the underlying model simplifies the real physics.

## Running it

```bash
pip install -r requirements.txt
jupyter notebook 436project.ipynb
```

Or open directly in [Google Colab](https://colab.research.google.com/github/calelo3232/Orbital-Modeling/blob/main/436project.ipynb) &mdash; no local setup required.

The three-body simulation's `ani.save('orbit.mp4', ...)` call additionally needs the `ffmpeg` binary on your `PATH` (not a pip package) to render the animation to video.

## Future work

- Generalize the three-body integrator to an arbitrary number of bodies instead of hardcoding three
- Model the orbital transfer with moving (rather than fixed) bodies, either by simulating the full multi-body system or by approximating relative motion as ellipses instead of stepwise integration
