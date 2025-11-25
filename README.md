# Estimating the Meridional Flow on the Sun’s Surface

This repository contains the complete code, data-processing pipeline, and results for my UG Project titled **“Estimating the Meridional Flow on the Sun’s Surface.”**  
The project was carried out under the supervision of **Dr. Bidya Binay Karak**, Department of Physics, IIT (BHU) Varanasi.

---

## 🔍 Project Overview

Meridional flow is a **slow poleward plasma motion** on the Sun’s surface (≈10–20 m/s) that transports magnetic flux from low to high latitudes. This flow plays a key role in building and reversing the Sun’s **polar magnetic field**, which sets the amplitude of the next solar cycle.

This project uses a **data-driven approach** to estimate the meridional flow for the year **1955**, based on daily magnetic-field maps generated from a Surface Flux Transport (SFT) simulation.

---

## 🛰️ Data Used

- Daily **radial magnetic-field maps** (512×1024) from an SFT simulation (year 1955).  
- Maps provided by supervisor for research use.  
- Example visualizations and a full-year animation are included in the repository.

---
### 📁 **Data Access**
The daily SFT synoptic maps (1955) used in this project are large in size, so they are **hosted on Google Drive**.  
You can download the dataset from the link below:

🔗 **Data Link:** [https://drive.google.com/your_dataset_link_here](https://drive.google.com/drive/folders/1t3Rh1qalSUgXdGlPdm-e-u__pAe2QM6p?usp=sharing)

---

## 🧠 Methodology

### 1. **Map Preprocessing**
- Read daily `.dat` binary maps  
- Apply a **27-day running mean** to:
  - Smooth small-scale noise  
  - Highlight large-scale magnetic structures  
  - Match the Carrington rotation period  

### 2. **Cross-Correlation Tracking**
- Compare map(t) with map(t + 27 days)  
- For each latitude:
  - Slide maps vertically  
  - Compute correlation  
  - Record the **pixel shift** with maximum similarity  

### 3. **Convert Pixel Shift → Speed**
- Pixel → degrees → radians → meters  
- Divide by 27 days to obtain **meridional flow speed in m/s**

### 4. **Yearly Aggregation**
- Repeat for all 338 map pairs  
- Compute:
  - Mean meridional flow  
  - Standard deviation  
- Fit a smooth analytic profile:  
  *A sin(2λ) + B sin(4λ)*

---

## 📊 Results

Key quantitative results for **1955**:

- **Peak North flow:** +10.93 m/s at +43.86°  
- **Peak South flow:** –12.88 m/s at –44.56°  
- **Global mean speed:** 2.61 m/s  
- **Global RMS speed:** 3.88 m/s  
- **Total 27-day pairs analyzed:** 338  

A plot of the final meridional flow profile is included in the repository.
