---
layout: landing_page
title: Geotechnical Engineering
permalink: /geotech/
---

## Geotechnical Engineering

Some basic notes on Geotechnical Engineering for easy access on the web.  
*(Disclaimer: This content is for personal revision use and has not been peer reviewed.)*

---

### 🧱 What is Geotechnical Engineering?

Geotechnical engineering is the branch of civil engineering concerned with the behaviour of **soils, rocks, and groundwater** under loading, construction, and environmental conditions. Essentially:  
> **How does the ground affect our ability to build on it?**

---

### 🔍 Key Areas in Geotechnics

#### **🕳 Tunnelling**
My undergraduate thesis focused on tunnelling. It involves understanding how the ground reacts to excavations, including settlement, face stability, and long-term ground behaviour — especially in soft clays.

#### **⛰ Slope Stability**
The resistance of natural or man-made slopes (soil or rock) to sliding or collapse. It’s essential to ensure slope safety, particularly under loading or during rainfall.

#### **🪜 Piles & Foundations**
Used when surface soils are too weak to support loads. Piles are deep foundations designed based on ground conditions and can work through end bearing or shaft friction.

#### **🧱 Retaining Walls**
Walls built to hold back soil — commonly used in basements, cuttings, and embankments. Design must account for:
- Lateral earth pressures (e.g. Rankine or Coulomb)
- Water pressure (pore pressure)
- Surcharges

#### **🪢 Soil Reinforcement**
Improving soil stability using materials like **geogrids**, **soil nails**, or **rock bolts**. A common design reference in the UK is:
> **BS 8006-1:2010** – Strengthened/reinforced soils and other fills.

#### **☣ Contaminated Land**
Contaminated sites require careful assessment and design of countermeasures. Engineers may:
- Develop a **Conceptual Site Model (CSM)**
- Predict contaminant **seepage using advection–dispersion equations**
- Use **slurry walls** or **cut-off barriers**

---
---

## 🧠 Conceptual Site Models (CSMs)

A **Conceptual Site Model (CSM)** is a structured way of describing the **environmental and geotechnical conditions of a site**, focusing on **how contamination might travel** and **who or what might be affected**.

It forms the foundation for **risk assessment** and guides **site investigation and design**.

---

### 🔗 Source–Pathway–Receptor Model

The CSM is typically built around this simple structure:

| Element   | Description |
|-----------|-------------|
| **Source**    | Where the contamination originates (e.g. fuel spill, arsenic in made ground) |
| **Pathway**   | How the contaminant moves (e.g. through groundwater, soil vapour) |
| **Receptor**  | What or who could be harmed (e.g. construction workers, groundwater, ecosystems) |

💡 **Contamination only poses a risk if there is a complete Source → Pathway → Receptor (SPR) linkage.**

---

### 🧭 When is a CSM Used?

CSMs are used throughout site development, particularly for **brownfield sites** or areas with a history of industrial use.

- Site planning and risk management
- Design of remediation or containment (e.g. slurry walls)
- Regulatory reporting and planning permission

---

### 📝 How to Build a CSM

1. **Desk Study / Preliminary Risk Assessment (Phase 1)**
   - Review maps, historical land use, geology, hydrogeology
   - Identify potential contaminants

2. **Site Walkover**
   - Look for evidence of pollution, ground disturbance, venting, staining

3. **Intrusive Investigation (Phase 2)**
   - Boreholes, trial pits, groundwater and gas monitoring
   - Soil and water sampling

4. **Conceptual Model Development**
   - Combine all data into a visual or tabular model
   - Highlight possible contaminant transport and exposure scenarios

---

### 🧪 Example: Arsenic-Contaminated Site

| Component   | Example |
|-------------|---------|
| **Source**     | Arsenic in made ground (historic industrial waste) |
| **Pathway**    | Downward migration via groundwater flow |
| **Receptor**   | Underlying clean soil, construction workers, groundwater aquifer |
| **Barriers**   | Capping layer, slurry wall (mechanical containment) |

Visualising this helps decide whether intervention is needed — e.g. to install a cut-off wall or monitor groundwater.

---

### 📉 Why CSMs Matter in Geotechnics

Even if you're not remediating a chemical spill, **CSMs help manage geotechnical risk**:
- Identify **soft zones** or **compressible layers**
- Understand **groundwater influence** on retaining walls and slopes
- Prevent costly surprises during excavation

---

> “You can’t manage risk if you don’t understand it. That’s what a CSM is for.”

## 🔹 1. Darcy’s Law & Seepage

**Key Formulas:**

- \( q = k \cdot i \)
- \( i = \frac{\Delta h}{\Delta l} \)
- \( v = \frac{q}{n} \)
- \( k = \frac{v}{i} \), \( v = \frac{Q}{A} \), \( q = \frac{V}{t} \)

---

## 🔹 2. Consolidation Settlement

**Time factor:**  
\( T_v = \frac{C_v \cdot t}{d^2} \)

**Short-term settlement:**  
\( s(t) = s_{\text{final}} \left(1 - \frac{2}{\pi} e^{-\frac{\pi^2 T_v}{4}} \right) \)

**Final (long-term) settlement:**  
\( s = m_v \cdot \Delta \sigma \cdot H \)

---

## 🔹 3. Bearing Capacity

**Undrained (clay):**  
\( q_f = N_c \cdot s_u + \gamma \cdot D \)

**Drained (sand):**  
\( q_f = q' \cdot N_q + 0.5 \cdot \gamma \cdot B \cdot N_\gamma \)

**With eccentricity:**  
\( q_{\text{max}} = \frac{P}{A} + \frac{6M}{B^2} \)

Check:  
\( q_{\text{max}} < \frac{q_f}{\text{FS}} \)

---

## 🔹 4. Retaining Walls

**Rankine pressure:**  
\( K_a = \tan^2\left(45^\circ - \frac{\varphi}{2}\right) \)

**Lateral pressure:**  
\( \sigma_h = K_a \cdot \gamma \cdot z \)

**Pore pressure:**  
\( u = \gamma_w \cdot h \)

**Prop force by moment balance:**  
\( \sum M = 0 \Rightarrow P = \frac{\text{soil moment}}{\text{arm}} \)

---

## 🔹 5. Slope Stability

**Moment balance for FoS:**  
\( Q \cdot a + W \cdot b = P \cdot c + S \cdot R \)

**Design strength (undrained):**  
\( s_u^{\text{design}} = \frac{s_u}{\text{FS}} \)

Tip: Use geometry for centroids and areas. Draw clearly.

---

## 🔹 6. Contaminant Transport

**Advection-dispersion:**  
\( C(x,t) = \frac{C_0}{2} \cdot \text{erfc}\left( \frac{x - ut}{2\sqrt{D t}} \right) \)

Where:  
- \( u = \frac{ki}{n} \) (seepage velocity)  
- \( D = \tau D_0 + \alpha u \) (dispersion)

---

## 🔹 7. Conceptual Site Model (CSM)

Build a **Source–Pathway–Receptor** model:

- **Source**: Contaminant (e.g. hydrocarbons, arsenic)
- **Pathway**: e.g. groundwater flow
- **Receptor**: e.g. aquifer, human health

Always sketch your linkage.

---

