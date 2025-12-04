
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
