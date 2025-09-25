# Microlensing-time-scales-and-flux-magnification-probabilities-of-a-sample-of-204-lensed-quasars

## Microlensing Maps Post-Analysis — Data Dictionary

This repository contains the merged catalog of lens, source, and microlensing map–level quantities used in the analysis. The tables below document each column.

> **Citation / Paper placeholder**  
> *Paper:* **TBD — add title, authors, year**  
> *DOI:* **TBD** · *ADS bibcode:* **TBD**

> **Photometry & references**  
> Reference photometry for all objects is available at:  
> https://github.com/felavila/qumas/tree/main/qumas/Tables

---

### Identification & Coordinates

| Column | Description | Units / Type |
|---|---|---|
| `name` | System identifier (primary) | string |
| `component` | Lensed image label (e.g., A, B, C, D) | string |
| `known_names` | Alternative names / aliases | string / list-like |
| `ra`, `dec` | Right Ascension, Declination (J2000) | deg |
| `z_l`, `z_s` | Lens and source redshifts | dimensionless |
| `zl_known`, `zs_known` | Flags: redshift measured/known | bool |
| `photometric_system` | Photometric system of reference mags | string |
| `Telescope`, `instrument` | Facility and instrument | string |
| `Bibcode`, `Bibcode_zl`, `Bibcode_zs` | ADS bibcodes for system, lens-z, source-z | string |
| `ref_link` | Reference URL for the system entry | string |

---

### Lens Model & Galaxy (Macro) Properties

| Column | Description | Units / Type |
|---|---|---|
| `RE`, `e_RE` | Einstein radius (image plane) and uncertainty | arcsec |
| `einstein_radii` | Einstein radius list per model (if multiple) | list-like |
| `mass_models` | Macro mass model family/families used | string / list-like |
| `mass_models_parameters` | Number of parameters of the macro model(s) | integer |
| `gamma` | External shear amplitude | dimensionless |
| `kappa` | Convergence at image position (macro) | dimensionless |
| `Re_kpc`, `e_Re_kpc` | Lens galaxy effective (half-light) radius | kpc |
| `re[cm]`, `re[lday]` | Effective radius converted to cm / light-days | cm, lday |
| `ratio_cosmo[cm]` | Cosmological conversion factor (angular→physical)† | cm |
| `rmse` | Model residual root-mean-square | mag or model units |
| `BIC`, `AICc`, `AIC` | Model selection criteria | dimensionless |

† *As defined in the Methods: combines distance ratios and unit conversions used to map angular scales to physical units.*

---

### Map & Microlensing Setup

| Column | Description | Units / Type |
|---|---|---|
| `alpha_value` | Stellar mass fraction in convergence, α ≡ κ\*/κ\_tot | dimensionless |
| `M_micro` | Assumed mean microlens mass | M⊙ |
| `pix` | Map pixel scale (source plane) | ER/pix or physical units |
| `mappix` | Linear pixel count per side of the map | integer |
| `lambda_cen` | Central/rest wavelength used for scaling | Å |
| `band_to_model` | Band/filter used in modeling | string |
| `zpt` | Photometric zero point (if applicable) | mag |

---

### Source Size & Scaling

| Column | Description | Units / Type |
|---|---|---|
| `Rs_lday` | Source size (characteristic) | lday |
| `rs`, `e_rs` | Source size in model’s native units (e.g., ER) | dimensionless |
| `rs_times` | Multiplicative size scale factor used | dimensionless |
| `factor_scale_to_sigma` | Factor converting size to Gaussian σ | dimensionless |
| `rs_sigma[pix]` | Gaussian σ equivalent of size in pixels | pix |
| `ts`, `e_ts` | Source crossing timescale | days |
| `te`, `e_te` | Einstein crossing timescale | days |

---

##### Kinematics (Effective Velocity Decomposition)

| Column | Description | Units / Type |
|---|---|---|
| `v`, `e_v` | Effective transverse velocity | km s⁻¹ |
| `v_cmb`, `e_v_cmb` | CMB dipole projection term | km s⁻¹ |
| `v_d`, `e_v_d` | Lens-plane velocity component (dispersion) | km s⁻¹ |
| `p_s`, `e_p_s` | Prior/term for source peculiar velocity | km s⁻¹ |
| `p_l`, `e_p_l` | Prior/term for lens peculiar velocity | km s⁻¹ |

---

### Flux-Ratio / Magnification Statistics (from Map Sampling)

| Column | Description | Units / Type |
|---|---|---|
| `num_bins` | Number of bins used in histograms | integer |
| `mean_edges` | Mean of Δmag histogram (signed) | mag |
| `mean_abs_edges` | Mean of |Δmag| histogram | mag |
| `mean_positive_edges` | Mean of Δmag for Δmag > 0 | mag |
| `mean_negative_edges` | Mean of Δmag for Δmag < 0 | mag |
| `prob_mag_less_than_n032_edges` | P(Δmag < −0.32) | probability |
| `prob_mag_more_than_p032_edges` | P(Δmag > +0.32) | probability |
| `var_edges` | Variance of Δmag histogram | mag² |
| `var_pmf_abs_edges` | Variance of |Δmag| PMF | mag² |
| `median_demag`, `std_demag` | Median and std. of demagnification | mag |
| `max(delta_images)` | Maximum pairwise Δ (see Methods) | mag / model units |

---

### Rescaled Sizes (Wavelength / Redshift Conversions)

| Column | Description | Units / Type |
|---|---|---|
| `rs_lday_1736`, `e_rs_lday_1736` | Size at 1736 Å (lday) | lday |
| `rescaled_rs[lday]_1736`, `e_rescaled_rs[lday]_1736` | Rescaled size at 1736 Å | lday |
| `rescaled_rs[cm]_8140`, `e_rescaled_rs[cm]_8140` | Rescaled size at 8140 Å | cm |
| `rs_8140/(1+zs)`, `e_rs_8140/(1+zs)` | Rest-frame size at 8140 Å | model units |
| `rescaled_rs[cm]_8140/(1+zs)`, `e_rescaled_rs[cm]_8140/(1+zs)` | Rest-frame size (cm) at 8140 Å | cm |
| `ts_rescaled_8140`, `e_ts_rescaled_8140` | Rescaled timescale at 8140 Å | days |
| `ts_rescaled_8140/(1+zs)`, `e_ts_rescaled_8140/(1+zs)` | Rest-frame rescaled timescale | days |
| `rescaled_rs[lday]_2500`, `e_rescaled_rs[lday]_2500` | Rescaled size at 2500 Å (lday) | lday |
| `rs[lday]_2500`, `e_rs[lday]_2500` | Size at 2500 Å (lday) | lday |
| `ref_wavelength(A)` | Reference wavelength used for scaling | Å |

> **Notes on rescalings**  
> Wavelength-dependent sizes follow the adopted accretion-disk scaling (e.g., \( R \propto \lambda^{p} \)) and are adjusted to rest-frame where indicated by `/(1+zs)`.

---


### Usage

```python
import pandas as pd
df = pd.read_csv("merged_catalog.csv")
