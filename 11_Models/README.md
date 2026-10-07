# Beam Propagation Method

This folder contains Python/Colab notebooks and supporting material for the numerical modelling of photonic devices.

The current notebook introduces the scalar finite-difference Beam Propagation Method (FD-BPM) and applies it to a directional coupler.

## Topics

The notebook covers:

- scalar Beam Propagation Method;
- separation of the rapidly varying longitudinal phase;
- reference propagation constant \(\beta_{\rm ref}\);
- finite-difference discretization in the transverse direction;
- Crank--Nicolson longitudinal propagation;
- sparse-matrix implementation;
- numerical calculation of the input waveguide mode;
- propagation of a guided mode through a directional coupler;
- optical power exchange between coupled waveguides;
- numerical convergence and limitations of the BPM approximation.

## Notebook

### `BPM_directional_coupler_Colab.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PaoloBardellaPolito/Photonic-Devices-2026/blob/main/11_Models/BPM_directional_coupler_Colab.ipynb)

A compact implementation of the scalar finite-difference Beam Propagation Method.

The notebook first calculates the fundamental mode of an isolated input waveguide by solving the transverse eigenvalue problem

$$\left[\frac{d^2}{dx^2}+k_0^2 n^2(x)\right]U(x)=\beta^2 U(x).$$

The calculated mode is then used as the input field for BPM propagation through a directional coupler.

The BPM formulation is based on

$$E(x,z)=u(x,z)e^{-j\beta_{\rm ref}z},$$

with

$$\beta_{\rm ref}=k_0 n_{\rm ref},$$

so that the numerical calculation follows the slowly varying envelope \(u(x,z)\).

The propagation equation is discretized using finite differences in the transverse direction and a Crank--Nicolson step along \(z\).

The notebook displays:

- the refractive-index profile;
- the fundamental input mode;
- the two-dimensional field evolution \(|u(x,z)|^2\);
- the exchange of optical power between the two waveguides;
- an estimate of the coupling length.

## Parameters to explore

The code can be modified to investigate the effect of:

- waveguide width;
- waveguide separation;
- core and cladding refractive indices;
- wavelength;
- transverse grid spacing $\Delta x$;
- longitudinal propagation step $\Delta z$;
- computational-window width;
- propagation length.

## Suggested exploration

Before changing a parameter, try to predict the result.

Some useful questions are:

- What happens to the coupling length when the gap between the waveguides is reduced?
- What happens when the waveguides are moved farther apart?
- How does the index contrast affect modal confinement and coupling?
- How does the wavelength affect the coupling strength?
- What happens if the input field is not an eigenmode of the isolated waveguide?
- How sensitive is the result to $\Delta x$ and $\Delta z$?
- What happens if the transverse computational window is too narrow?
- Why does the field remain almost unchanged when an eigenmode propagates in a uniform waveguide?
- Under which conditions would the scalar or paraxial BPM approximation become unreliable?

## Numerical convergence

A smooth field map does not guarantee numerical accuracy.

The calculation should be repeated using:

- smaller $\Delta x$;
- smaller $\Delta z$;
- a larger transverse computational window.

A physical quantity such as coupling length or output power should be monitored until it no longer changes significantly.

## Limitations

The notebook intentionally uses a simple educational model:

- scalar BPM;
- two-dimensional $x$-$z$ geometry;
- predominantly forward propagation;
- paraxial approximation;
- simple transverse boundary conditions;
- no PML;
- no bidirectional propagation.

The method is therefore most appropriate for long guided structures with a preferred propagation direction and relatively smooth longitudinal variations.

Strong reflections, abrupt discontinuities, strongly non-paraxial propagation and fully vectorial effects require more complete numerical models.

## Notes

All distances in the notebook are expressed in micrometres.

The material is intended for educational use in the **Photonic Devices 2026** course.
