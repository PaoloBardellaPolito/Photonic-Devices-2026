# Bragg grating reflectivity

This folder contains interactive Python/Colab notebooks for exploring the reflection properties of a uniform Bragg grating using coupled-mode theory.

## Topics

The notebooks cover:

- complex reflection coefficient \(r\);
- power reflectivity
  \[
  R=|r|^2;
  \]
- reflection phase;
- Bragg wavelength \(\lambda_B\);
- wavelength detuning from the Bragg condition;
- normalized detuning;
- dependence on grating coupling coefficient \(\kappa\);
- dependence on grating length \(L_g\);
- influence of propagation losses;
- relation between grating strength \(\kappa L_g\) and peak reflectivity.

## Notebook

### `Bragg_Grating_Reflectivity.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PaoloBardellaPolito/Photonic-Devices-2026/blob/main/Grating/Bragg_Grating_Reflectivity.ipynb)

Interactive exploration of the complex reflection coefficient of a uniform Bragg grating.

The controls allow the user to vary:

- grating coupling coefficient \(\kappa\);
- grating length \(L_g\);
- effective refractive index \(n_{\rm eff}\);
- material loss coefficient \(\alpha_m\);
- Bragg wavelength \(\lambda_B\);
- wavelength range around the Bragg wavelength.

The notebook automatically recalculates:

- power reflectivity
  \[
  R(\lambda)=|r(\lambda)|^2;
  \]
- phase of the reflection coefficient;
- wavelength detuning
  \[
  \lambda-\lambda_B;
  \]
- normalized detuning
  \[
  \frac{\operatorname{Re}(\delta)L_g}{\pi}.
  \]

For a uniform grating, the detuning parameter is written as

\[
\delta=
2\pi n_{\rm eff}
\left(
\frac{1}{\lambda}
-
\frac{1}{\lambda_B}
\right)
-j\alpha_m,
\]

and

\[
\sigma=\sqrt{\kappa^2-\delta^2}.
\]

The complex reflection coefficient is

\[
r=
-j\kappa
\frac{\tanh(\sigma L_g)}
{\sigma+j\delta\tanh(\sigma L_g)}.
\]

For a lossless grating exactly at the Bragg wavelength,

\[
|r(\lambda_B)|=\tanh(\kappa L_g),
\]

and therefore

\[
R(\lambda_B)=\tanh^2(\kappa L_g).
\]

## Suggested exploration

Before changing a parameter, try to predict the result.

Some useful questions are:

- What happens to the maximum reflectivity when the grating length \(L_g\) increases?
- What happens when the coupling coefficient \(\kappa\) increases?
- Why does the product \(\kappa L_g\) determine the reflectivity at the Bragg wavelength?
- How does the reflection bandwidth depend on \(\kappa\)?
- What happens to the reflection spectrum when losses are introduced?
- How does the phase of the reflected field vary across the reflection band?
- What happens far away from the Bragg condition?
- Why is the reflection coefficient complex even for a lossless grating?

Try also changing \(\kappa\) and \(L_g\) while keeping their product approximately constant. Compare the peak reflectivity and the spectral bandwidth.

## Notes

The notebook implements the coupled-mode model of a **uniform Bragg grating**.

The grating parameters are assumed to be constant along the propagation direction. More general structures such as apodized, chirped, phase-shifted, or sampled gratings are not considered here.

The material is intended for educational use in the **Photonic Devices 2026** course.
