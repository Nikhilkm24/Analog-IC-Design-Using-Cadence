> Tool: Cadence Virtuoso Layout Suite XL  
> Technology: gpdk045  
> Verification: Assura DRC  
> Objective: Physical layout creation and DRC verification of the Differential Amplifier used in Bandgap Reference (BGR)

# 🔬 Analog IC Design Using Cadence Virtuoso
 
> **Tool:** Cadence Virtuoso Layout Suite XL &nbsp;|&nbsp; **Technology:** gpdk045 &nbsp;|&nbsp; **Verification:** Assura DRC & LVS
 
Day-wise documentation of an Analog IC Design workshop using **Cadence Virtuoso**, covering MOS fundamentals, amplifier design, bandgap reference circuits, schematic-to-layout flow, and full DRC/LVS verification.
 
---
 
## 🏆 Key Outcome
 
✅ **Differential Amplifier** — designed from schematic capture through physical layout, with **DRC and LVS verification cleared** in Cadence Virtuoso on gpdk045 technology node.
 
---
 
## 📅 Day-wise Breakdown
 
| Day | Topic | Tools Used |
|---|---|---|
| Day 1 | MOS Fundamentals — Id-Vgs, Id-Vds characteristics, operating regions | Cadence Virtuoso Schematic, ADE |
| Day 2 | Amplifier Design — Common Source, gain, biasing | Cadence Virtuoso, ADE Parametric |
| Day 3 | Bandgap Reference (BGR) — PTAT current, design principles | Cadence Virtuoso, Spectre |
| Day 4 | **Differential Amplifier — Full Layout (DRC Cleared)** | Cadence Virtuoso Layout XL, Assura DRC |
| Day 5 | Layout Development of Test Amplifier — LVS Verification | Cadence Virtuoso Layout XL, Assura LVS |
 
---
 
## 🔑 Day 4 — Differential Amplifier Layout (Highlight)
 
**Objective:** Physical layout of the Differential Amplifier used in the Bandgap Reference (BGR) core.
 
### Design Flow
```
Schematic Capture (Virtuoso)
        ↓
Symbol Creation
        ↓
Pre-Layout Simulation (ADE / Spectre)
        ↓
Layout Design (Virtuoso Layout XL)
        ↓
DRC — Design Rule Check (Assura) ✅ Cleared
        ↓
LVS — Layout vs Schematic (Assura) ✅ Cleared
```
 
### Key Design Details
 
| Parameter | Value / Detail |
|---|---|
| Technology Node | gpdk045 (45nm) |
| Circuit | Differential Amplifier (BGR core) |
| Verification | DRC ✅ Cleared \| LVS ✅ Cleared |
| Tool | Cadence Virtuoso Layout Suite XL |
| Verification Engine | Assura DRC / LVS |
 
---
 
## 🔑 Day 5 — Test Amplifier Layout
 
**Objective:** Layout development and LVS verification of a test amplifier to validate extracted vs schematic netlists.
 
- Full layout drawn in Cadence Virtuoso Layout XL
- LVS run on Assura — netlists matched ✅
- Parasitic extraction performed for post-layout simulation
 
---
 
## 🛠️ Tools & Technology
 
| Tool | Purpose |
|---|---|
| Cadence Virtuoso Schematic Editor | Schematic capture, symbol creation |
| Cadence ADE (Analog Design Environment) | Pre/post layout simulation |
| Spectre Simulator | DC, AC, transient analysis |
| Cadence Virtuoso Layout XL | Physical layout design |
| Assura DRC | Design Rule Checking |
| Assura LVS | Layout vs Schematic verification |
| Technology | gpdk045 (45nm Generic PDK) |
 
---
 
## 📁 Folder Structure
 
```
Analog-IC-Design-Using-Cadence/
├── Day-01_MOS_Fundamentals/       ← Id-Vgs, Id-Vds, operating region analysis
├── Day_2/                         ← Common source amplifier design & simulation
├── Day_3/                         ← Bandgap reference design (PTAT, BGR core)
├── DAY_4/
│   └── Layout Design of Differential Amplifier/   ← ⭐ Main highlight
│       ├── screenshots/           ← Layout, DRC report, LVS result
│       └── notes.md
├── Day_5/
│   └── Layout Development Of Test Amplifier/
│       ├── screenshots/
│       └── notes.md
└── README.md
```
 
---
 
## 💡 Skills Demonstrated
 
- Analog circuit design fundamentals (MOS, amplifiers, BGR)
- Cadence Virtuoso schematic-to-layout full flow
- Physical layout techniques — matching, symmetry, guard rings
- DRC/LVS verification and debug workflow
- 45nm technology node design rules
 
---
 
## 👨‍💻 Author
 
**Nikhil K M** — B.Tech ECE, The National Institute of Engineering, Mysore (2023–2027)
[GitHub](https://github.com/Nikhilkm24)
 
---
 
## 📄 License
 
MIT License — open for reference and educational use.
