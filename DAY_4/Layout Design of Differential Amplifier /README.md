# Day 4 – Layout Design of Differential Amplifier (BGR Core)

> Tool: Cadence Virtuoso Layout Suite XL  
> Technology: gpdk045  
> Design Type: Analog Layout  
> Verification: Assura DRC  
> Objective: Create and verify the physical layout of the Differential Amplifier used in the Bandgap Reference (BGR)

---

##  Objective

The objective of Day-4 is to implement the **physical layout** of the **Differential Amplifier** used in the Bandgap Reference (BGR) circuit and to verify that the layout follows **foundry design rules** using **DRC**.

This step ensures that the schematic-level design is manufacturable and ready for further verification such as LVS.

---

##  Schematic Reference and Layout Creation  
*(Image-1)*

The layout process begins from the **Differential Amplifier schematic**.

Steps performed:
- Opened the schematic view of `Differential_Amplifier_1`
- Launched **Layout Suite XL**
- Created a new layout view linked to the schematic

This ensures proper **schematic–layout connectivity** and device consistency.

---

##  Layer Visibility Control (Oxide Layer)  
*(Image-2)*

To simplify layout inspection:
- Visibility was enabled **only for the Oxide layer**
- Other layers were temporarily disabled

Purpose:
- Clearly identify MOS active regions
- Understand device placement
- Reduce visual clutter during analysis

---

##  Identifying MOSFETs Connected to CS_1  
*(Image-3)*

By isolating the oxide layer, MOSFETs connected to **CS_1** were identified.

This step helps to:
- Trace current paths
- Verify differential pair symmetry
- Ensure correct grouping of connected devices

---

##  DF_1 Connected MOSFET Identification  
*(Image-4)*

MOSFETs connected to **DF_1** were identified in the layout.

This confirms:
- Correct schematic-to-layout mapping
- No missing or unintended connections
- Proper implementation of differential branches

---

##  TL_2 Connected MOSFET Identification  
*(Image-5)*

MOSFETs connected to **TL_2** (tail current source branch) were identified.

This ensures:
- Proper tail current routing
- Correct biasing connections
- Symmetry between left and right differential branches

---

##  Detailed Layer Inspection of MOSFETs  
*(Image-6)*

A zoomed-in inspection of MOSFETs was performed to observe:

- Oxide
- Poly
- Diffusion
- Contacts
- Metal layers

This confirms:
- Proper layer stacking
- Correct enclosure and overlap
- Clean device definition at layout level

---

##  Adjacent MOSFET Spacing Adjustment  
*(Image-7)*

The spacing between adjacent MOSFETs was explicitly set to **0.1 µm**.

Why this is important:
- Prevents spacing-related DRC violations
- Improves device matching
- Reduces parasitic coupling in analog circuits

This is especially critical for **differential pairs** and **current mirrors**.

---

##  DRC Setup for gpdk045 Technology  
*(Image-8)*

Design Rule Check (DRC) was configured using **Assura** with:

- Technology: `gpdk045`
- Rule set: default
- Area checked: Full layout

This ensures all foundry rules are applied correctly to the design.

---

##  Error Navigation and Rule Tracing  
*(Image-9)*

After running DRC:
- Specific DRC error paths were identified
- Errors were traced to exact layout locations
- Rule descriptions were examined to understand violations

This step is essential for debugging and correcting layout issues.

---

##  DRC Results and Verification  
*(Image-10)*

The DRC results window shows:
- All executed rule checks
- Identified violations (if any)
- Clear mapping between errors and layout regions

This confirms that:
- The layout follows gpdk045 design rules
- The design is close to fabrication-ready
- Remaining issues can be systematically fixed

---

##  Key Learnings from Day-4

- Layout XL maintains schematic–layout consistency
- Layer isolation simplifies layout understanding
- Device spacing is critical for analog performance
- Symmetry improves matching in differential circuits
- DRC is mandatory before LVS or tape-out

---

##  Conclusion

In Day-4, the Differential Amplifier schematic was successfully converted into a physical layout using Cadence Virtuoso Layout Suite XL. Device connectivity was verified using selective layer visibility, spacing rules were applied consciously, and DRC was performed using gpdk045 technology rules.

This layout is now prepared for **LVS verification** and **integration into the full Bandgap Reference layout**.

---
