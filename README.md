# Day 4 – Layout Design of Differential Amplifier (BGR Core)

> Tool: Cadence Virtuoso Layout Suite XL  
> Technology: gpdk045  
> Verification: Assura DRC  
> Objective: Physical layout creation and DRC verification of the Differential Amplifier used in Bandgap Reference (BGR)

---

##  Objective

The objective of Day 4 is to implement the **physical layout** of the Differential Amplifier used in the Bandgap Reference (BGR) circuit and verify that it satisfies **foundry design rules** using Design Rule Check (DRC).

This step ensures that the schematic design can be fabricated without violations.

---

## 1️ Circuit and Opening of Layout  
**Image Name:** `01_schematic_and_layout_launch.png`

![Schematic and Layout Launch](images/01_schematic_and_layout_launch.png)

The layout process starts from the Differential Amplifier schematic.  
Using **Layout Suite XL**, the layout view is created directly from the schematic, ensuring correct schematic–layout connectivity.

---

## 2️ Enabling Visibility Only for Oxide Layer  
**Image Name:** `02_oxide_layer_visibility.png`

![Oxide Layer Visibility](images/02_oxide_layer_visibility.png)

Only the **Oxide layer** visibility is enabled while other layers are turned off.

**Purpose:**
- Identify active regions of MOSFETs
- Understand physical placement
- Reduce visual complexity during layout analysis

---

## 3️ Identifying MOSFETs Connected to CS_1  
**Image Name:** `03_cs1_connected_mosfets.png`

![CS_1 Connected MOSFETs](images/03_cs1_connected_mosfets.png)

MOSFETs connected to **CS_1** are identified using layer isolation.

This step helps in:
- Tracing current paths
- Verifying correct device connectivity
- Ensuring symmetry in the differential structure

---

## 4️ DF_1 Connected MOSFET Identification  
**Image Name:** `04_df1_connected_mosfets.png`

![DF_1 Connected MOSFETs](images/04_df1_connected_mosfets.png)

MOSFETs connected to **DF_1** are identified and verified.

This confirms:
- Correct schematic-to-layout mapping
- Proper differential branch implementation
- No unintended missing or extra connections

---

## 5️ TL_2 Connected MOSFET Identification  
**Image Name:** `05_tl2_connected_mosfets.png`

![TL_2 Connected MOSFETs](images/05_tl2_connected_mosfets.png)

MOSFETs connected to **TL_2** (tail current source branch) are identified.

This ensures:
- Correct tail current routing
- Proper bias connections
- Balanced differential operation

---

## 6️ Zoomed View of MOSFET Layers  
**Image Name:** `06_mosfet_layer_zoom.png`

![MOSFET Layer Zoom](images/06_mosfet_layer_zoom.png)

A zoomed-in view is used to inspect different MOSFET layers:

- Oxide
- Poly
- Diffusion
- Contacts
- Metal layers

This confirms proper layer stacking and enclosure rules.

---

## 7️ Setting Adjacent MOSFET Distance to 0.1 µm  
**Image Name:** `07_adjacent_mosfet_spacing.png`

![MOSFET Spacing](images/07_adjacent_mosfet_spacing.png)

The spacing between adjacent MOSFETs is set to **0.1 µm**.

**Why this is important:**
- Avoids spacing-related DRC violations
- Improves device matching
- Reduces parasitic effects in analog layouts

---

## 8️ Selecting DRC for gpdk045 Technology  
**Image Name:** `08_drc_technology_selection.png`

![DRC Technology Selection](images/08_drc_technology_selection.png)

Design Rule Check (DRC) is configured using **Assura** with:

- Technology: gpdk045
- Rule set: default
- Area checked: Full layout

This ensures correct foundry rules are applied.

---

## 9️ Identifying the DRC Error Path  
**Image Name:** `09_drc_error_path.png`

![DRC Error Path](images/09_drc_error_path.png)

After running DRC, specific error paths are identified and traced to their exact layout locations.

This helps in:
- Understanding rule violations
- Locating problematic regions
- Planning corrective actions

---

##  DRC Output of the Design  
**Image Name:** `10_drc_results.png`

![DRC Results](images/10_drc_results.png)

The DRC results window displays:
- List of executed rule checks
- Identified violations
- Corresponding layout regions

This confirms the current DRC status of the layout.

---

##  Key Learnings

- Layout XL maintains schematic–layout consistency
- Layer-based inspection simplifies layout understanding
- Device spacing is critical for analog performance
- DRC is mandatory before LVS and tape-out

---

##  Conclusion

The Differential Amplifier layout for the Bandgap Reference was successfully created using Cadence Virtuoso Layout Suite XL. Device connectivity was verified through layer inspection, spacing rules were applied consciously, and DRC was executed using gpdk045 technology rules.

This layout is now ready for **LVS verification** and **integration into the complete BGR layout**.
