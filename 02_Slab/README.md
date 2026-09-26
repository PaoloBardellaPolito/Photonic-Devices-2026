# Symmetric slab waveguide

This folder contains interactive Python/Colab notebooks for exploring the guided modes and dispersion properties of a symmetric dielectric slab waveguide.

## Topics

The notebooks cover:

- guided TE and TM modes;
- effective index \(n_{\rm eff}\);
- propagation constant \(\beta\);
- discrete modal spectrum;
- transverse field profiles;
- evanescent decay in the cladding;
- modal cutoff;
- dependence on slab thickness, wavelength, and refractive-index contrast;
- waveguide dispersion.

## Notebooks

### `Interactive_Slab_Waveguide.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PaoloBardellaPolito/Photonic-Devices-2026/blob/main/02_Slab/Interactive_Slab_Waveguide.ipynb)

Interactive exploration of the guided modes of a symmetric slab waveguide.

The controls allow the user to vary:

- core refractive index \(n_1\);
- cladding refractive index \(n_2\);
- slab thickness \(d\);
- wavelength \(\lambda\);
- TE or TM polarization.

The notebook automatically recalculates:

- number of guided modes;
- effective indices \(n_{\rm eff}\);
- propagation constants;
- transverse field profiles;
- evanescent decay in the cladding;
- modal cutoff conditions.

---

### `Slab_Dispersion_Explorer.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PaoloBardellaPolito/Photonic-Devices-2026/blob/main/02_Slab/Slab_Dispersion_Explorer.ipynb)

Interactive exploration of the dependence of the modal effective index on wavelength and slab thickness.

The notebook displays:

- the two-dimensional map
  \[
  n_{\rm eff}(\lambda,d);
  \]
- \(n_{\rm eff}(\lambda)\) at fixed slab thickness;
- \(n_{\rm eff}(d)\) at fixed wavelength;
- cutoff boundaries for higher-order modes.

Interactive controls allow the user to modify:

- \(n_1\);
- \(n_2\);
- slab thickness \(d\);
- wavelength \(\lambda\);
- TE or TM polarization;
- modal order.

In this notebook, \(n_1\) and \(n_2\) are assumed to be wavelength independent. The wavelength dependence of \(n_{\rm eff}\) therefore represents **pure waveguide dispersion**.

## Suggested exploration

Before changing a parameter, try to predict the result.

Some useful questions are:

- What happens to the number of guided modes when the slab thickness increases?
- How does increasing the wavelength affect confinement?
- What happens when the refractive-index contrast \(n_1-n_2\) is reduced?
- How do TE and TM modes differ?
- What happens to \(n_{\rm eff}\) when a mode approaches cutoff?
- Why can \(n_{\rm eff}\) depend on wavelength even when \(n_1\) and \(n_2\) do not?

A mode approaching cutoff satisfies
\[
n_{\rm eff}\rightarrow n_2,
\]
while its evanescent decay constant in the cladding tends to zero.

## Notes

The models assume a symmetric, lossless, non-magnetic dielectric slab with \(n_1>n_2\).

The material is intended for educational use in the **Photonic Devices 2026** course.
