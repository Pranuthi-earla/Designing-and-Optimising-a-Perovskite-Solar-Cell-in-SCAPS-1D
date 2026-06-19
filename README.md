# Designing-and-Optimising-a-Perovskite-Solar-Cell-in-SCAPS-1D
11-june- day1
## Contents
### Phase A — Foundations (Weeks 1–3)
- A.1 What SCAPS-1D is, in one paragraph
- A.2 Getting the software
- A.3 The cell you will build
- A.4 The baseline parameter set
- A.5 Building the cell, click by click
- A.6 Your first calculation
- A.7 Calibration — the step that makes it publishable
### Phase B — Single-parameter studies (Weeks 4–7)
- B.1 Study 1 — Absorber thickness
- B.2 Study 2 — Bulk defect density (the most important study)
- B.3 Study 3 — Absorber doping
- B.4 Study 4 — Operating temperature
### Phase C — Optimisation and publication (Weeks 8–12)
- C.1 Study 5 — Transport-layer (band-alignment) screening
- C.2 Study 6 — Interface defects: bulk vs interface recombination
- C.3 Study 7 — Coupled two-parameter optimisation
- C.4 Assemble and validate the optimised cell
- C.5 Writing the manuscript

##### A.1 What SCAPS-1D is, in one paragraph
SCAPS-1D is a free one-dimensional solar-cell simulator from the University of Gent. You describe a stack
of semiconductor layers and their material properties, shine a standard sunlight spectrum on it, and the
program solves the semiconductor equations to predict the current-voltage (J–V) curve and the four
performance numbers. It is the standard tool for thin-film and perovskite device design because it is
fast, free, and matches experiment well when the input parameters are chosen carefully.


![Image](https://images.openai.com/static-rsc-4/Sl-tuuWh4px3_iWUjN747G4iaF95Y_4xzXjWKdZZtvb2yHgqwTb_VpKbuMGjwbkuqAPOcvI0xJrgtA5yP82991arN3t9FLb59w40YW5QmRutIg24gRBk4Y7dAWOgxLzSSLcW7i1IT0uZ-bfX9yoiRkRvFipH6mQS5BlSdSPL23SYMR9IYYnhnPWKGS4ITmqT?purpose=fullsize)

---

#### Material System of TiO₂/MAPbI₃/Spiro-OMeTAD Perovskite Solar Cell
- why each material is chosen, how it functions, and how its properties influence the photovoltaic behavior of the device.
  
The selection of materials in a perovskite solar cell plays a crucial role in determining device efficiency and stability. Although numerous electron transport layers (ETLs), absorber materials, and hole transport layers (HTLs) have been investigated, the combination of TiO₂, MAPbI₃, and Spiro-OMeTAD remains one of the most extensively studied and experimentally validated architectures. This configuration has served as a benchmark structure for both experimental investigations and numerical simulations because of its favorable band alignment, efficient charge transport, and availability of well-established material parameters.
The perovskite solar cell structure consisting of titanium dioxide (TiO₂), methylammonium lead iodide (MAPbI₃), and Spiro-OMeTAD has attracted significant attention due to its remarkable power conversion efficiency and relatively simple fabrication process. In this architecture, each layer performs a specific function that contributes to efficient charge generation, charge transport, and suppression of carrier recombination losses.

The complete device structure generally consists of:

**FTO/TiO₂/MAPbI₃/Spiro-OMeTAD/Au**

where fluorine-doped tin oxide (FTO) acts as the transparent front electrode and gold (Au) serves as the back contact.

---

# Titanium Dioxide (TiO₂) as Electron Transport Layer

Titanium dioxide is one of the most widely employed electron transport materials in perovskite solar cells because of its excellent transparency, chemical stability, and favorable energy level alignment with the perovskite absorber.

TiO₂ is a wide bandgap semiconductor with a bandgap of approximately 3.2 eV in its anatase phase. Owing to this large bandgap, the material absorbs very little visible light and allows most of the incident photons to reach the absorber layer. Consequently, optical losses at the front side of the device are minimized.

In the TiO₂/MAPbI₃/Spiro-OMeTAD structure, TiO₂ performs two major functions. First, it extracts photogenerated electrons from the conduction band of MAPbI₃ and transports them towards the FTO electrode. Second, it acts as a hole-blocking layer, preventing holes generated within the absorber from reaching the front contact. This selective transport significantly reduces electron-hole recombination and improves the open-circuit voltage of the device.

The conduction band minimum of TiO₂ lies close to that of MAPbI₃, which facilitates efficient electron transfer. Meanwhile, its deep valence band suppresses hole injection into the electron transport layer. Such favorable band alignment contributes to efficient charge separation and carrier collection.

Another advantage of TiO₂ is its excellent chemical stability and ease of preparation through techniques such as spray pyrolysis, spin coating, and chemical bath deposition. However, TiO₂ possesses relatively low electron mobility compared with alternative ETL materials such as SnO₂. Moreover, trap states and ultraviolet-induced photocatalytic activity can induce performance degradation and hysteresis effects in perovskite devices.

Typical properties of TiO₂ used in simulation studies are:

| Parameter             | Value      |
| --------------------- | ---------- |
| Bandgap               | 3.2 eV     |
| Electron affinity     | 4.0 eV     |
| Relative permittivity | 9          |
| Electron mobility     | 20 cm²/V·s |
| Donor concentration   | 10¹⁸ cm⁻³  |
| Thickness             | 30–100 nm  |

---

# MAPbI₃ as the Light-Absorbing Layer

Methylammonium lead iodide (CH₃NH₃PbI₃), commonly referred to as MAPbI₃, is the active absorber material responsible for converting solar energy into electrical energy. It belongs to the family of organic-inorganic hybrid perovskites characterized by the general formula ABX₃, where A represents methylammonium (CH₃NH₃⁺), B denotes Pb²⁺ ions, and X corresponds to iodide ions.

MAPbI₃ has emerged as an exceptional photovoltaic material because of its direct bandgap of approximately 1.55 eV, which is close to the optimum value predicted by the Shockley-Queisser limit for single-junction solar cells. This bandgap allows efficient absorption across a large portion of the visible spectrum, leading to high photocurrent generation.

One of the most remarkable features of MAPbI₃ is its extremely high absorption coefficient, on the order of 10⁵ cm⁻¹. Consequently, a relatively thin layer of only a few hundred nanometers is sufficient to absorb most incident sunlight. This property distinguishes perovskite absorbers from conventional silicon solar cells, which require significantly thicker active layers.

Another important characteristic of MAPbI₃ is its balanced electron and hole transport properties. The material exhibits relatively high carrier mobilities and long diffusion lengths, enabling photogenerated carriers to reach their respective transport layers before recombination occurs. These characteristics contribute to high short-circuit current density and overall device efficiency.

Upon illumination, photons absorbed by MAPbI₃ generate electron-hole pairs. Electrons are transferred to the TiO₂ layer, whereas holes migrate toward the Spiro-OMeTAD layer. Efficient charge separation at these interfaces is crucial for minimizing recombination losses and maximizing power conversion efficiency.

Despite its outstanding optoelectronic properties, MAPbI₃ suffers from several limitations. The material is highly sensitive to moisture, oxygen, heat, and ultraviolet radiation. These factors can induce decomposition and reduce long-term device stability. Furthermore, the presence of lead raises environmental concerns and motivates ongoing research into lead-free alternatives.

Typical simulation parameters for MAPbI₃ are:

| Parameter             | Value         |
| --------------------- | ------------- |
| Bandgap               | 1.55 eV       |
| Electron affinity     | 3.9 eV        |
| Relative permittivity | 6.5–10        |
| Electron mobility     | 10 cm²/V·s    |
| Hole mobility         | 10 cm²/V·s    |
| Carrier concentration | 10⁹–10¹⁰ cm⁻³ |
| Thickness             | 300–700 nm    |

---

# Spiro-OMeTAD as Hole Transport Layer

Spiro-OMeTAD, chemically known as 2,2′,7,7′-tetrakis-(N,N-di-p-methoxyphenylamine)-9,9′-spirobifluorene, is one of the most commonly employed hole transport materials in high-efficiency perovskite solar cells.

The primary function of Spiro-OMeTAD is to selectively extract holes generated in the MAPbI₃ absorber and transport them toward the metallic back electrode. At the same time, it blocks electrons from reaching the rear contact, thereby suppressing interfacial recombination.

The HOMO energy level of Spiro-OMeTAD aligns well with the valence band maximum of MAPbI₃, promoting efficient hole extraction. This favorable energy level matching contributes to enhanced open-circuit voltage and fill factor.

Although pristine Spiro-OMeTAD possesses relatively low conductivity, its electrical properties can be significantly improved through p-type doping using additives such as lithium bis(trifluoromethanesulfonyl)imide (Li-TFSI) and 4-tert-butylpyridine (tBP). These dopants increase hole mobility and conductivity, resulting in improved charge transport and higher power conversion efficiency.

However, Spiro-OMeTAD is expensive and exhibits hygroscopic behavior because of the dopants employed. Moisture absorption can accelerate device degradation and limit long-term stability. These drawbacks have stimulated extensive research into alternative hole transport materials, including CuSCN, NiOₓ, PTAA, and CuI.

Typical parameters used in SCAPS simulations are:

| Parameter              | Value            |
| ---------------------- | ---------------- |
| Bandgap                | 3.0 eV           |
| Electron affinity      | 2.2 eV           |
| Relative permittivity  | 3                |
| Hole mobility          | 2 × 10⁻⁴ cm²/V·s |
| Acceptor concentration | 10¹⁸ cm⁻³        |
| Thickness              | 100–250 nm       |

---

# Charge Transport Mechanism

Under solar illumination, photons are absorbed by the MAPbI₃ layer, resulting in the generation of electron-hole pairs. Due to the favorable band alignment, electrons migrate from the conduction band of MAPbI₃ to TiO₂ and subsequently to the FTO electrode. Simultaneously, holes move from the valence band of MAPbI₃ to Spiro-OMeTAD and finally reach the gold electrode.

This selective carrier transport mechanism effectively suppresses recombination and enables efficient extraction of photogenerated carriers. Consequently, the TiO₂/MAPbI₃/Spiro-OMeTAD architecture can achieve power conversion efficiencies exceeding 20%.

---

# Suitability of this Material Combination

The TiO₂/MAPbI₃/Spiro-OMeTAD system is frequently adopted as a reference structure in SCAPS-1D simulation studies because of:

1. Favorable energy band alignment between adjacent layers.
2. Excellent light absorption capability of MAPbI₃.
3. Efficient electron extraction by TiO₂.
4. Effective hole transport through Spiro-OMeTAD.
5. Availability of extensive experimental and simulation data for validation.
6. High reported power conversion efficiencies.

Therefore, this material combination serves as an ideal platform for investigating the influence of layer thickness, defect density, carrier concentration, interface properties, and temperature effects on the photovoltaic performance of perovskite solar cells.

--------------------------------------------------------------------------------------------------------------------------------------------------
12-jun-day 2
- Layer-by-Layer Function & Band Alignment
- FTO (Front Contact): Fluorine-doped Tin Oxide (FTO) coated on glass is the transparent conducting substrate. It allows sunlight to enter the cell while serving as the negative electrode.
- TiO₂ (ETL): Titanium Dioxide acts as the Electron Transport Layer, extracting electrons from the perovskite while blocking holes. Its conduction band (CBM ≈ -4.0 eV) aligns perfectly to extract electrons smoothly from MAPbI₃.
- MAPbI₃ (Absorber): Methylammonium Lead Iodide is the photoactive layer. With an optimal bandgap of ≈ 1.55 eV, it absorbs visible light and generates free electron-hole pairs.
- Spiro-OMeTAD (HTL): This organic semiconductor acts as the Hole Transport Layer. It extracts holes from the perovskite (VBM ≈ -5.2 eV) while blocking electrons. It is almost universally doped with additives like Li-TFSI and 4-tert-butylpyridine (tBP) to boost conductivity.
- Au (Back Contact): Gold is thermally evaporated on top of the HTL to collect the holes and act as the positive electrode.

---------------------------

## Day 3 — Report entry

**Date:** 19–20 June 2026
**Objective:** Build the baseline FTO/TiO₂/MAPbI₃/Spiro-OMeTAD/Au layer stack in SCAPS 3.3.10 per NAMTECH Handbook §A.4–A.5.

**Procedure followed:**
1. Opened Set Problem → Solar Cell Definition panel.
2. Added three layers — TiO2, MAPbI3, Spiro — with parameters entered per the baseline table (full values below).
3. Encountered an error: clicking "Invert the structure" caused layer data to reset to blank generic layers ("layer 1/2/3"), which was inadvertently auto-saved. Identified and corrected by starting a **new** problem and re-adding all three layers manually in the correct order (TiO2 → MAPbI3 → Spiro), avoiding the Invert function entirely.
4. Verified layer order: **left contact (front) → TiO₂ → MAPbI₃ → Spiro → right contact (back)**.
5. Set **illuminated from: left**, confirmed visually via the light-ray diagram entering the TiO₂ side.
6. Saved as `baseline.def`.
<img width="1511" height="804" alt="image" src="https://github.com/user-attachments/assets/0ba479ba-b5bc-424d-ac37-67bd20f90835" />

<img width="1511" height="828" alt="image" src="https://github.com/user-attachments/assets/12428a42-2883-45b1-beb2-ad19e05fa69f" />
<img width="1511" height="817" alt="image" src="https://github.com/user-attachments/assets/a73c07d8-7dc5-4a54-a734-96f53d039518" />



**Parameters entered:**

| Parameter | TiO₂ | MAPbI₃ | Spiro |
|---|---|---|---|
| Thickness (nm) | 50 | 400 | 200 |
| Eg (eV) | 3.2 | 1.55 | 3.0 |
| χ (eV) | 4.0 | 3.9 | 2.2 |
| εr | 9 | 6.5 | 3 |
| NC (cm⁻³) | 2.2×10¹⁸ | 2.2×10¹⁸ | 2.2×10¹⁸ |
| NV (cm⁻³) | 1.8×10¹⁹ | 1.8×10¹⁹ | 1.8×10¹⁹ |
| μn (cm²/Vs) | 20 | 2 | 2×10⁻⁴ |
| μp (cm²/Vs) | 10 | 2 | 2×10⁻⁴ |
| ND (cm⁻³) | 1×10¹⁷ | 0 | 0 |
| NA (cm⁻³) | 0 | 1×10¹⁶ | 1×10¹⁸ |
| Nt (cm⁻³) | 1×10¹⁵, neutral, mid-gap | 1×10¹⁵, neutral, mid-gap | 1×10¹⁵, neutral, mid-gap |

Source: NAMTECH Handbook (rev. 2), Table A.4; values consistent with standard literature MAPbI₃ device parameters (e.g. Saliba et al., *Science* 2016).

**Issues encountered & fixes:**
- TiO2 layer initially had incorrect ND (1×10¹⁶ instead of 1×10¹⁷) and nonzero NA (should be 0) — corrected.
- Spiro layer initially had incorrect NV (2.18×10²⁰ instead of 1.8×10¹⁹) — corrected.
- "Invert the structure" caused full layer-data loss — avoided this function;
  data lost
<img width="1092" height="707" alt="Screenshot 2026-06-20 000834" src="https://github.com/user-attachments/assets/ebf20693-9dcc-42a4-995b-39bd41440584" />
rebuilt layer-by-layer with correct order/illumination set manually instead.
<img width="1370" height="883" alt="image" src="https://github.com/user-attachments/assets/783cf661-b6b5-4688-9557-790c4f21e0b7" />

<img width="1354" height="884" alt="image" src="https://github.com/user-attachments/assets/ab7a1b4e-5540-4adc-917f-3b3051e275f2" />



**Result:** `baseline.def` saved successfully at 20-6-2026, 00:22:23. No calculation run yet (reserved for Day 6–7).

**Next steps:** Day 4–5 — final review pass; confirm absorption model and defect settings once more in each layer before Day 6's first calculation.

---

