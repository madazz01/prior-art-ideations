# Unified Atmospheric & Quantum Vacuum Energy Harvesting System

**Author:** Bryan Horsfield  
**Date:** 2026-08-05  
**Status:** Prior art disclosure — concept in development, research phase  

## Core Insight

A unified energy harvesting architecture that combines multiple energy sources — atmospheric electric field gradient, Schumann resonance AC component, and Dynamic Casimir Effect quantum vacuum extraction — into a single solid-state circuit operating on a shared resonance principle. The key to scaling from trickle to usable current is pulse width optimisation at resonant frequency across every stage simultaneously — getting the whole system "on song."

## Energy Sources

**1. Atmospheric DC Gradient**
The Earth-ionosphere system maintains a natural electric field of approximately 100V per metre of altitude. A wire suspended at 10 metres sits in a ~1000V potential difference relative to ground. This is a continuous, always-on DC source.

**2. Schumann Resonance AC Component**
The Earth-ionosphere cavity resonates at 7.83 Hz (fundamental) with harmonics at 14.3, 20.8, 27.3 Hz etc. These are continuous, global, never-switching-off AC signals present at any point on Earth. Both the DC gradient and AC Schumann signals exist simultaneously in the same antenna — they can be separated and harvested through parallel circuit paths.

**3. Dynamic Casimir Effect**
When conductive plates at nanoscale separation are oscillated at the correct resonant frequency (research suggests GHz range depending on geometry), quantum vacuum fluctuations between the plates cannot equilibrate and are converted into real photons — extractable as usable energy. Experimentally confirmed at Chalmers University 2011. The key variable is pulse width — short sharp oscillation pulses at resonant frequency extract more energy per cycle than continuous oscillation.

## The Unified Principle — Resonance and Pulse Width

All stages share a common operating principle drawn from fluid dynamics: get the system "on song." A tuned exhaust extracts maximum power not by forcing flow but by timing pressure waves so each pulse assists the next. Same principle applied here:

- Casimir plates oscillated at their natural resonant frequency — pulse width optimised
- Atmospheric harvester tuned to local Schumann frequency — pulse width at rectifier
- Step-up transformer (ignition coil topology) — pulse width on primary determines secondary spike
- Each stage self-reinforcing, standing wave behaviour, minimum resistance, maximum throughput

The system does not force energy — it creates the conditions for energy to move in the desired direction naturally.

## Circuit Architecture

**Stage 1 — Toroidal Antenna**
Toroidal ferrite core antenna suspended at height captures both DC atmospheric gradient and AC Schumann resonances simultaneously. Toroidal geometry chosen for low external field leakage and self-contained flux — unusual choice for atmospheric harvesting, creating novel field interaction characteristics.

**Stage 2 — Self-Tuning Solid State Circuit**
Adaptive resonance circuit (PLL or varactor-based) continuously measures local field conditions and locks to optimal frequency for geographic position. Schumann frequency varies slightly by latitude, altitude, and ionospheric conditions. Circuit self-tunes rather than being fixed to a global frequency.

**Stage 3 — Parallel Harvesting Paths**
- DC path: rectifier captures atmospheric gradient component
- AC path: oscillating diode rectifier tuned to Schumann frequency captures AC component
- Both paths feed common supercapacitor bank

**Stage 4 — Dynamic Casimir Stage**
MEMS or superconducting circuit oscillates Casimir plate geometry at resonant frequency. Pulse width control circuit optimises extraction efficiency. Output fed to supercapacitor bank.

**Stage 5 — Step-Up Stage**
Ignition coil or flyback transformer topology steps up voltage to maximise charge rate into supercapacitor bank. Pulse width on primary timed to resonant frequency of overall system.

**Stage 6 — Supercapacitor Buffer Bank**
Large supercapacitor bank (high energy density, fast charge/discharge) acts as universal intermediary between harvesting sources and load. Absorbs irregular/trickle input from all harvesting stages. Delivers smooth, controlled output to downstream battery or load.

**Stage 7 — Battery Storage + Charge Management**
Supercaps trickle into LiPo or similar battery at optimal charge rate. Charge management controller monitors cap state, battery state, and load demand. Battery handles peak load delivery.

## Consumer Application — Wireless Atmospheric Phone Charger

Primary proof-of-concept application: a device that sits on a desk and charges a phone wirelessly with no plug, no solar panel, and no battery replacement. Charges from atmospheric energy passively. Supercap buffer accumulates trickle input and delivers Qi-standard wireless charging output when sufficient charge is stored.

**Product pitch:** "Charges your phone from thin air."

## $150 Proof-of-Concept Build List

| Component | Purpose | Est. Cost |
|-----------|---------|-----------|
| Toroidal ferrite core coil | Antenna stage | ~$5 |
| Grounding rod | Earth reference | ~$5 |
| Variable capacitor | Tunable LC circuit | ~$5 |
| NE555 timer or Arduino Nano | Pulse width control | ~$5-10 |
| Schottky diodes | Low-threshold fast rectifier | ~$3 |
| Germanium diodes | Ultra low threshold alternative | ~$3 |
| Small ignition coil or flyback transformer | Step-up stage | ~$10-20 |
| Supercapacitor bank (2.7V 100F × 4) | Energy buffer | ~$20-30 |
| Small LiPo battery | Downstream storage | ~$10 |
| DSO138 oscilloscope kit | Waveform visualisation — critical | ~$15 |
| Miscellaneous wire, PCB, connectors | Assembly | ~$10 |
| **Total** | | **~$100-130** |

The oscilloscope is the non-negotiable instrument — resonant frequency must be observed and tuned visually before the system can be optimised. "Finding the song" happens on the scope.

## Build Sequence

1. Antenna first — suspend toroid at height with grounding rod, measure voltage with scope
2. Tune LC circuit until DC gradient is visible on scope output
3. Add rectifier stage — confirm DC capture
4. Add NE555 pulse width stage — tune to Schumann fundamental (7.83 Hz), observe harmonic resonance
5. Add step-up (ignition coil) — observe voltage multiplication on secondary
6. Connect supercap bank — measure charge accumulation rate over time
7. Add Casimir oscillation stage (GHz range) — advanced, requires custom MEMS or adapted superconducting circuit
8. Final integration — all stages feeding common supercap bank → LiPo → USB/Qi output

## Research Needed

- Dynamic Casimir Effect optimal frequency for achievable plate geometries (GHz range — specific values TBD from literature)
- Pulse width relationships for DCE extraction efficiency
- Toroidal antenna interaction with atmospheric gradient vs standard vertical wire — experimental comparison
- Patent landscape search — what has been claimed individually, what combinations remain open
- Schumann frequency geographic variation data — Australian latitude values

## Prior Art Note

This concept was originated by Bryan Horsfield on 2026-08-05. The novel claims are:

1. **Toroidal antenna geometry** for simultaneous DC gradient + AC Schumann harvesting
2. **Self-tuning position-aware resonance circuit** — adapts to local conditions rather than fixed global frequency
3. **Dynamic Casimir Effect stage integrated with atmospheric harvesting** in a unified architecture
4. **Supercapacitor buffer as universal intermediary** across all harvesting stages
5. **Unified pulse-width-optimised resonance principle** applied across all stages simultaneously — the "on song" principle
6. **Consumer wireless phone charger** as the primary proof-of-concept application

Prior art on individual components exists (atmospheric harvesting separately documented, DCE separately documented, supercap EV buffering separately documented). The unified architecture combining all elements — and the "on song" resonance principle as the unifying operating theory — is the novel claim.
