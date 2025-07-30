---
layout: post  
title: FTIR Spectroscopy  
date: 2025-07-29 23:48:24  
description: A detailed explanation of FTIR spectroscopy principles and a step-by-step practical guide.  
tags: spectroscopy FTIR chemistry analytical-techniques  
tabs: true  
---  

## **1. Introduction to FTIR Spectroscopy**  
Fourier Transform Infrared (FTIR) spectroscopy is an analytical technique used to identify and characterize chemical compounds by measuring their absorption of infrared (IR) radiation. It provides a molecular fingerprint of the sample, allowing for qualitative and quantitative analysis.  

### **Key Principles**  
- **Infrared Absorption**: Molecules absorb IR light at specific frequencies corresponding to their vibrational modes (e.g., stretching, bending).  
- **Interferometry**: Instead of a dispersive element (like in traditional IR spectroscopy), FTIR uses an interferometer to modulate IR light, producing an interferogram.  
- **Fourier Transformation**: The interferogram is converted into a spectrum (absorbance vs. wavenumber, $$cm^{-1}$$) using a mathematical Fourier transform.  

## **2. Step-by-Step Practical Example**  

### **Step 1: Sample Preparation**  
- **Solid Samples**:  
  - **KBr Pellet Method**: Mix ~1 mg of sample with 100 mg KBr, press into a transparent pellet.  
  - **ATR (Attenuated Total Reflectance)**: Place solid directly on ATR crystal (no preparation needed).  
- **Liquid Samples**:  
  - Apply a thin film between two NaCl or KBr plates.  
  - For volatile liquids, use a sealed liquid cell.  
- **Gas Samples**: Use a gas cell with IR-transparent windows.  

### **Step 2: Instrument Setup**  
1. **Turn on the FTIR spectrometer** and allow it to warm up (~15-30 min).  
2. **Background Scan**: Run a scan without the sample to account for atmospheric CO₂ and H₂O interference.  
3. **Load the sample** into the sample compartment (e.g., place KBr pellet in holder or ATR crystal).  

### **Step 3: Data Acquisition**  
1. **Select scan parameters**:  
   - Wavenumber range: Typically **4000–400 cm⁻¹**  
   - Resolution: **4 cm⁻¹** (higher resolution for fine details)  
   - Number of scans: **16–64** (averaging improves signal-to-noise ratio)  
2. **Run the scan**: The interferometer modulates IR light, and the detector records the interferogram.  
3. **Fourier Transform**: Software converts the interferogram into a spectrum.  

### **Step 4: Data Analysis**  
- **Peak Identification**: Compare observed peaks to reference spectra (e.g., O-H stretch ~3300 cm⁻¹, C=O stretch ~1700 cm⁻¹).  
- **Quantitative Analysis**: Use Beer-Lambert law ($$A = \epsilon \cdot c \cdot l$$) for concentration determination.  

### **Step 5: Post-Measurement**  
- Clean the sample holder (e.g., wipe ATR crystal with ethanol).  
- Store data and export spectra for further processing.  

## **3. Example Application**  
**Identifying an Unknown Polymer**  
1. Obtain a spectrum of the polymer (e.g., polyethylene).  
2. Observe key peaks:  
   - **C-H stretch**: ~2900 cm⁻¹  
   - **C-H bending**: ~1460 cm⁻¹  
3. Match with a spectral library to confirm identity.  

## **4. Advantages of FTIR**  
- Fast acquisition (seconds per scan).  
- High sensitivity and resolution.  
- Minimal sample preparation (especially with ATR).  

By following these steps, FTIR spectroscopy can be effectively used for material characterization in chemistry, pharmaceuticals, and materials science.