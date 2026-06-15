# Physics Laboratory 1 – Experimental Methods & Mechanics
**University of Pavia · B.Sc. in Physics · A.Y. 2020–21**  
*Giovanni Nicola D'Aloisio*

> Hands-on introduction to experimental physics: uncertainty propagation, statistical data analysis, and mechanical oscillators.  
> Notebooks written in Python (Google Colab / Jupyter); raw data acquired with PASCO sensors and processed with NumPy/SciPy.

---

## Repository structure

```
physics-lab-1/
├── 00_intro_statistics_and_tools/   ← Error analysis, distributions, intro to Python data pipeline
├── 01_pendulum/                     ← Simple & damped pendulum, period vs length, decay constant
│   └── data/
│       ├── repeated_runs/           ← 8 independent acquisition runs (PASCO .txt)
│       ├── Lunghezze.txt            ← Length measurements
│       └── Moto_smorzato.txt        ← Damped oscillation time series
├── 02_spring_oscillator/            ← Hooke's law (static) + SHM (dynamic, 16 acquisitions)
│   └── data/
│       ├── dynamic_measurements/    ← Ril1–Ril16.txt + .cap oscilloscope capture
│       ├── Misure_statiche.txt
│       └── Riepilogo.txt
├── 03_standing_waves_and_acoustics/ ← Standing waves on string + resonance in air column
│   └── autocad_sketches/            ← Experimental setup drawings (.dwg)
├── 04_millikan/                     ← Millikan oil-drop experiment, elementary charge measurement
│   └── data/
│       └── Lab_210519 - Millikan.xlsx
└── 05_foucault_telescope/           ← ⭐ HIGHLIGHT: Foucault knife-edge test on a JWST-inspired
    └── data/                            Cassegrain telescope mirror; CCD wavefront analysis
        ├── CCD_images/              ← 14 × 16-bit TIFF frames at different mirror positions
        └── intensity_profiles/      ← Extracted 1D intensity profiles for fitting (14 × .txt)
```

---

## Highlight: Foucault telescope test (`05_foucault_telescope/`)

The Foucault knife-edge test is the same wavefront-sensing principle used during the JWST mirror alignment campaign.  
In this experiment a Cassegrain-geometry optical bench was built and tested:

- A CCD camera captured 14 frames at mirror-to-knife separations ranging from **641.9 to 1831.5 mm**.
- Each `.tif` frame is a **2752 × 2200 px, 16-bit greyscale** image of the illuminated aperture.
- Intensity profiles were extracted and fitted to characterise mirror aberrations.
- The notebook `Lab_210526_Luce.ipynb` implements the full pipeline: image loading → profile extraction → Gaussian fitting → Foucault sensitivity estimate.

---

## Experiments at a glance

| # | Experiment | Key physics | Analysis tools |
|---|---|---|---|
| 00 | Statistics intro | Gaussian, Poisson distributions | Excel + Colab |
| 01 | Simple & damped pendulum | SHM, exponential decay | SciPy curve_fit |
| 02 | Spring oscillator | Hooke's law, resonance | PASCO, NumPy |
| 03 | Standing waves & acoustics | Normal modes, speed of sound | FFT, resonance peaks |
| 04 | Millikan experiment | Stokes drag, elementary charge | OLS fitting |
| 05 | **Foucault telescope** | **Wavefront sensing, CCD imaging** | **PIL, SciPy, 2D Gaussian fit** |

---

## How to run the notebooks

```bash
pip install numpy scipy matplotlib pandas pillow openpyxl
jupyter notebook
```

Or open directly in [Google Colab](https://colab.research.google.com/) (no local install needed).

---

## License

CC BY-NC-ND 4.0 · © 2021 Giovanni Nicola D'Aloisio
