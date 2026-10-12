# Interactive all-pass ring resonator

A compact educational notebook for exploring the spectral response of an **all-pass ring resonator**.

The notebook is intended for the **Photonic Devices 2026** course. It connects the analytical ring-resonator model used in the lectures with an interactive wavelength-domain simulation.

## Notebook

### `BPM_directional_coupler_Colab.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/PaoloBardellaPolito/Photonic-Devices-2026/blob/main/Ring/All_Pass_Ring.ipynb)

## Physical model

The round-trip propagation factor is

$$
p(\lambda)=a\,e^{-j\phi(\lambda)},
$$

with

$$
\phi(\lambda)=\beta(\lambda)L,
\qquad
\beta(\lambda)=\frac{2\pi n_{\rm eff}(\lambda)}{\lambda}.
$$

The through-port transfer function is

$$
H_{\rm th}(\lambda)=\frac{t-p(\lambda)}{1-t\,p(\lambda)}.
$$

and the power transmission is

$$
T(\lambda)=|H_{\rm th}(\lambda)|^2.
$$

The propagation loss is specified as a **power attenuation coefficient in dB/cm**. The corresponding round-trip field attenuation is

$$
a=10^{-\alpha_{\rm dB/cm}L_{\rm cm}/20}.
$$

At resonance,

$$
H_{\rm th,res}=\frac{t-a}{1-ta}.
$$

Hence the ring is:

- **undercoupled** for $t>a$;
- **critically coupled** for $t=a$;
- **overcoupled** for $t<a$.

At critical coupling, the through-port transmission ideally vanishes at resonance.

## Linearized effective-index model

The wavelength dependence of the effective index is represented by a first-order expansion around

$$
\lambda_0=1.55\,\mu{\rm m}.
$$

Using

$$
n_g=n_{\rm eff}-\lambda\frac{d n_{\rm eff}}{d\lambda}.
$$

the notebook writes

$$
n_{\rm eff}(\lambda)
\simeq
n_{\rm eff,0}
+
\frac{n_{\rm eff,0}-n_g}{\lambda_0}
(\lambda-\lambda_0).
$$

This separates two useful effects:

- $n_{\rm eff,0}$ mainly determines the absolute resonance positions;
- $n_g$ determines the resonance spacing to first order.

## What the notebook does

The notebook contains:

- an analytical all-pass-ring transfer function;
- a linearized model of $n_{\rm eff}(\lambda)$;
- conversion of waveguide loss in dB/cm into round-trip field attenuation;
- interactive sliders for $t$, $L$, propagation loss, $n_{\rm eff,0}$, and $n_g$;
- automatic identification of the coupling regime;
- calculation of the resonance nearest $\lambda_0$;
- calculation of FSR in frequency and wavelength;
- calculation of FWHM, finesse, and quality factor $Q$;
- through-port power transmission versus wavelength;
- through-port phase response versus wavelength;
- markers showing consecutive resonances.

The wavelength window is automatically adapted to the FSR so that several resonances remain visible while the parameters are changed.

## Main analytical quantities

The free spectral range is approximated by

$$
{\rm FSR}_f
\simeq
\frac{c}{n_gL},
$$

or, in wavelength,

$$
{\rm FSR}_\lambda
\simeq
\frac{\lambda_r^2}{n_gL}.
$$

For a sufficiently narrow resonance,

$$
\Delta\lambda_{\rm FWHM}
\simeq
{\rm FSR}_\lambda
\frac{1-ta}{\pi\sqrt{ta}},
$$

and

$$
Q=\frac{\lambda_r}{\Delta\lambda_{\rm FWHM}}.
$$

For an ideal lossless bus-ring coupler,

$$
t^2+\kappa^2=1.
$$

## Requirements

The notebook uses only standard scientific Python packages plus Jupyter widgets:

```text
numpy
matplotlib
ipywidgets
```

These packages are available in Google Colab.

For a local installation:

```bash
pip install numpy matplotlib ipywidgets
```

## Running in Google Colab

The notebook is stored in the `Ring` directory of the course repository.

Use the direct Colab link above, or:

1. open Google Colab;
2. select **File -> Open notebook -> GitHub**;
3. enter the repository `PaoloBardellaPolito/Photonic-Devices-2026`;
4. open `Ring/All_Pass_Ring.ipynb`;
5. select **Runtime -> Run all**.

No additional data files are required.

## Main parameters to explore

The interactive controls are:

```python
t              # field self-coupling coefficient
L_um           # ring round-trip length [um]
loss_dB_cm     # waveguide power loss [dB/cm]
neff0          # effective index at lambda0
ng             # group index at lambda0
```

The reference wavelength is fixed at

```python
lambda0_um = 1.55
```

so that the role of the other parameters remains easy to interpret.

## Suggested exercises

Possible experiments include:

1. increase the ring length and verify that the FSR decreases;
2. change $n_g$ and observe the change in resonance spacing;
3. change $n_{\rm eff,0}$ and observe the shift of the resonance wavelengths;
4. vary $t$ across the critical-coupling condition $t=a$;
5. compare undercoupled, critically coupled, and overcoupled responses;
6. increase propagation loss and observe the changes in linewidth and $Q$;
7. compare the numerical response with the analytical FSR and FWHM expressions.

## Scope

This is intentionally a compact educational model.

It assumes:

- a single bus waveguide and a single ring mode;
- a real, wavelength-independent field self-coupling coefficient $t$;
- a first-order wavelength model for $n_{\rm eff}$;
- constant group index over the displayed wavelength range;
- distributed propagation loss represented by a single round-trip amplitude factor.

The notebook does **not** include:

- a wavelength-dependent directional-coupler model;
- bending radiation calculated from Maxwell's equations;
- back-reflection;
- higher-order spatial modes;
- nonlinear effects;
- thermal or electro-optic tuning.

Its purpose is not to replace a full electromagnetic simulator, but to provide a compact interactive representation of the all-pass ring model used in the course.
