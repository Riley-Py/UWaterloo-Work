
**Luminosity vs. Apparent Brightness**

| Quantity | Definition | Units | Distance Dependence |
|----------|------------|-------|-------------------|
| **Luminosity (L)** | Total energy a star emits per second | Watts (J/s) | Independent of distance |
| **Apparent brightness (b)** | Energy per second per unit area received at Earth | W/m² | Decreases with distance² |

- Apparent brightness **depends on distance**, luminosity does not.  
- Relation:  
$b = \frac{L}{4 \pi d^2}$
Where:  
- \(b\) = apparent brightness  
- \(L\) = luminosity  
- \(d\) = distance to the star  

---
**Example: Sun vs. Alpha Centauri**
- Both have **similar luminosities**, $L_{\odot} \approx L_{\alpha Cen}$  
- Apparent brightness at Earth:  
  - Sun: **very bright** because it’s close $(d = 1 \text{ AU}$)  
  - Alpha Centauri: **much dimmer** because it’s ~4.37 light-years away  
$b_\text{sun} \gg b_\text{Alpha Cen} \quad \text{(due to distance² law)}$
---
**Determining Luminosity**
If we **measure the distance and the apparent brightness**, we can calculate the luminosity:
$L = 4 \pi d^2 \, b$
- Measure \(b\) using a telescope.  
- Measure \(d\) using **parallax** or other distance methods.  
- Invert the relation to find \(L\). 
---
**Concept of Parallax**
- **Parallax** is the apparent shift of a nearby star against the background of distant stars as Earth orbits the Sun.
- Nearby stars appear to move slightly over a year, while distant stars appear nearly fixed.
- The **parallax angle** (\(p\)) is half the angular shift observed over 6 months.
---
**Relation to Distance**
- Distance \(d\) (in parsecs) is inversely proportional to the parallax angle \(p\) (in arcseconds):
$d \,[\text{pc}] = \frac{1}{p \,[\text{arcsec}]}$
- 1 parsec (pc) ≈ 3.26 light-years.
**Examples:**
- $p = 1'' \implies d = 1 \text{ pc}$  
- $p = 0.1'' \implies d = 10 \text{ pc} \approx 32.6 \text{ ly}$ 

---
**Observational Notes**
- Parallax angles are extremely small (a few arcseconds for the closest stars).  
- Measuring them requires precise instruments.  
- Historical detection of stellar parallax wasn’t possible until the 1800s due to the tiny angles.  
- Modern telescopes (like Gaia) can measure parallaxes down to micro-arcsecond precision.
---
**Luminosity Range**
- Stars have a huge range of luminosities:
  - Most luminous: ~1,000,000 × Sun's luminosity  
  - Least luminous: ~10⁻⁴ × Sun's luminosity  
- This spans **10 orders of magnitude** in brightness.
---
**Magnitude Scale**
- Astronomers use **magnitude** to measure brightness on a logarithmic scale.
- **Apparent magnitude (m):** based on observed brightness from Earth.
  - Brighter stars → smaller magnitude  
  - Fainter stars → larger magnitude
  - Relation between two stars:
	$\frac{b_2}{b_1} = 100^{(m_1 - m_2)/5}$
- **Absolute magnitude (M):** based on intrinsic luminosity.
  - Defines brightness if the star were at **10 parsecs** from Earth.
  - Relation to luminosity:
	$\frac{L_2}{L_1} = 100^{(M_1 - M_2)/5}$
- Increasing magnitude → fainter star, decreasing magnitude → brighter star.
---
**Connection Between Apparent and Absolute Magnitude**
- Absolute magnitude is simply the **apparent magnitude a star would have at 10 pc**:
$M = m - 5 \log_{10}\left(\frac{d}{10\,\text{pc}}\right)$
Where:  
- \(M\) = absolute magnitude  
- \(m\) = apparent magnitude  
- \(d\) = distance in parsecs
- This allows comparison of stars’ intrinsic brightness regardless of distance.
---
**Thermal Radiation and Temperature**
- Dense objects emit **thermal radiation**; spectrum depends on **temperature**.  
- **Hotter objects**:
  - Emit more energy per unit area (**Stefan-Boltzmann law**):  
$F = \sigma T^4$
  - Emit photons with **higher average energy** (shorter wavelength) (**Wien's law**):  

$\lambda_\text{max} = \frac{2,900,000 \,\text{nm K}}{T}$
- Surface temperature (photosphere):
  - Hottest stars: ~50,000 K  
  - Coolest stars: ~3,000 K  
  - Sun: ~5,800 K  
---
**Ionization and Spectral Lines**
- **Hot stars:** most atoms ionized → fewer absorption lines (mainly hydrogen)  
- **Cool stars:** atoms mostly neutral → many absorption lines (sodium, calcium, titanium oxide, etc.)  
- **Absorption lines** provide **temperature diagnostics** because ionization depends on temperature.
---
**Stellar Classification (Spectral Types)**
- Stars are classified based on **spectral lines** and temperature:  

| Type | Temperature         | Notes                              |
| ---- | ------------------- | ---------------------------------- |
| O    | Hottest (~50,000 K) | Few lines, mostly ionized hydrogen |
| B    | 10,000–30,000 K     | Strong hydrogen lines              |
| A    | 7,500–10,000 K      | Hydrogen lines prominent           |
| F    | 6,000–7,500 K       | Hydrogen weaker, metals appear     |
| G    | 5,200–6,000 K       | Sun’s type; metals stronger        |
| K    | 3,700–5,200 K       | Many metal lines                   |
| M    | Coolest (~3,000 K)  | Molecules visible, many lines      |
|      |                     |                                    |

---
**Measuring Stellar Temperature**
- **Peak of thermal spectrum** → Wien’s law → temperature  
- **Absorption lines** → ionization state → temperature
- Both methods together give a reliable measure of stellar surface temperature.
---
**Measuring Stellar Masses**
- **Masses** of stars are primarily measured using **binary systems**.  
- Binary types:
  1. **Visual binaries** – two stars can be resolved with a telescope; orbit around each other is directly observed.
  2. **Spectroscopic binaries** – stars cannot be resolved, but Doppler shifts in spectral lines reveal orbital motion.
  3. **Eclipsing binaries** – one star passes in front of the other; allows measurement of orbital inclination and stellar sizes.
---
**Observables and Mass Calculation**
- **Kepler’s Third Law** (Newtonian form) for binary systems:

$\frac{a^3}{P^2} = \frac{G (M_1 + M_2)}{4 \pi^2}$
Where:  
- \(a\) = orbital separation  
- \(P\) = orbital period  
- \(M_1, M_2\) = masses of the two stars  
- \(G\) = gravitational constant

- **Velocity from Doppler shift:**  
$v = \frac{2 \pi a}{P}$
- **Steps to measure masses:**
  1. Measure **orbital period** (from periodic motion or eclipses).  
  2. Measure **orbital separation** (from visual binaries) or **orbital velocity** (from spectra).  
  3. Combine two measurements to solve for **sum of masses**.  
  4. If possible, measure **mass ratio** (from two sets of spectral lines).  
  5. Inclination \(i\) can be inferred for **eclipsing binaries**; otherwise, assumptions may be needed.
---
 **Mass Ranges**
- **Most massive stars:** ~100 $M_\odot$  
- **Least massive stars:** ~0.08 $M_\odot$
- Masses vary by roughly **three orders of magnitude**.  
---
The H-R diagram reveals **patterns in stellar properties** by plotting **luminosity vs. temperature** (or spectral type).

---
**Axes and Scale**
- **Vertical axis:** Luminosity (logarithmic scale, faint → bright)  
- **Horizontal axis:** Surface temperature (hot → cool; increases to the left)
- **Alternative horizontal:** Spectral type (O → M, hottest to coolest)  
---
**Main Sequence**
- Majority of stars lie along a **diagonal band** called the **main sequence**.  
- Indicates a relationship between **temperature, luminosity, and radius**.  
- **Hotter stars** → more luminous (upper-left)  
- **Cooler stars** → less luminous (lower-right)  
- For a star on the main sequence:

$L \sim R^2 T^4$

Where:  
- \(L\) = luminosity  
- \(R\) = radius  
- \(T\) = surface temperature  
---
 **Giants and Supergiants**
- Stars **above the main sequence** have **higher luminosity** for their temperature → must be **larger radius**.  
  - **Giants:** moderately above main sequence  
  - **Supergiants:** far above main sequence (e.g., Betelgeuse, Antares)  

---
**White Dwarfs**
- Stars **below the main sequence** have **lower luminosity** for their temperature → must be **smaller radius**.  
- Typically **hot but dim** → called **white dwarfs**.
---
**Stellar Classification**
- Each star has:
  - **Spectral type** (O, B, A, F, G, K, M) based on temperature and absorption lines
  - **Luminosity class** (I: supergiant → V: main sequence)  
    Examples:  
    - Sun: G2 V  
    - Sirius: A1 V  
    - Betelgeuse: M2 I  
---
**. Reading Stellar Properties from the H-R Diagram**
- **Temperature / Color / Spectral type:** horizontal axis  
- **Luminosity:** vertical axis  
- **Radius:** from Stefan-Boltzmann law lines:
$L = 4 \pi R^2 \sigma T^4$
- **Largest radius:** upper-right (cool, luminous) → supergiants  
- **Smallest radius:** lower-left → white dwarfs  
- **Example identification:**
  - Hottest star → far left (A)  
  - Most luminous → top (C)  
  - Main sequence → along diagonal band (D)  
  - Largest radius → far above main sequence (C)
---
## 1. Main Sequence and Hydrogen Fusion
- Stars on the main sequence are **fusing hydrogen into helium** in their cores.  
- The **stellar thermostat** keeps stars in equilibrium:
  - If a star cools → contracts → heats up → fusion rate increases → luminosity rises → balance restored.
  - If a star expands → cools → fusion slows → contracts → balance restored.
- **Mass determines a star's position on the main sequence:**
  - Higher mass → higher core temperature → more luminous → blue, hot stars.  
  - Lower mass → lower core temperature → less luminous → red, cool stars.

---

## 2. Mass, Luminosity, and Lifetime
- Main sequence stars show strong correlation between **mass, luminosity, and temperature**:
  - **High-mass stars:** short-lived, luminous, blue, large radius  
    - Lifetime ~ \(10^7\) years  
  - **Sun-like stars:** moderate mass, luminosity, lifetime ~ \(10^{10}\) years  
  - **Low-mass stars:** faint, red, small radius, extremely long-lived  
    - Lifetime ~ \(10^{11}\) years  

- **Reason for rapid burn in massive stars:**
  - High mass → higher core pressure and temperature  
  - Fusion rate is very sensitive to temperature → luminosity rises steeply → fuel consumed faster

\[
\text{Lifetime} \sim \frac{\text{Fuel}}{\text{Luminosity}}
\]

---

## 3. Evolution off the Main Sequence
- Stars eventually **run out of hydrogen in the core** → leave main sequence:
  - Core contracts, outer layers expand → **giants and supergiants**  
  - After fusion ends, stars shed envelopes → **white dwarfs**
  - Some stars may undergo more exotic outcomes (neutron stars, black holes)

---

## 4. Giant vs. Supergiant vs. White Dwarf
| Type | Temperature | Luminosity | Radius | Notes |
|------|------------|-----------|-------|-------|
| **Supergiant** | Cool to hot | Very high | Huge | Upper-right of H-R |
| **Giant** | Cooler | High | Large | Above main sequence |
| **White Dwarf** | Hot | Low | Tiny | Below main sequence |

- **Example:**  
  - Sun → main sequence, will become red giant → then white dwarf  
  - Massive star → burns fuel quickly → supergiant → possible supernova

---

## 5. Variable Stars
- Some stars **cannot maintain exact equilibrium** → luminosity varies with time  
- **Instability strip:** region on H-R diagram where stars pulsate  
- Types of pulsating variables:
  - **Cepheids:** bright, upper main sequence/giant region, periods ~ days to months  
  - **RR Lyrae:** lower luminosity, shorter periods  

- Example: **Polaris (North Star)** is a variable star in the instability strip.  

> Light curves show **periodic brightness changes**, indicating oscillations in radius and luminosity.