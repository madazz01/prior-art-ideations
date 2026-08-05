# EV Supercapacitor Buffer Charging System

**Author:** Bryan Horsfield  
**Date:** 2026-08-05  
**Status:** Prior art disclosure — public timestamp  
**Note:** Author states this concept was originated several years prior when EVs were first becoming mainstream.

## Concept

A dual-stage EV energy storage and charging architecture that uses a large supercapacitor bank as an intermediary buffer between the charging source and the battery pack — solving both grid infrastructure stress and battery longevity problems simultaneously.

## System Architecture

**Stage 1 — Capacitor bank accepts instantaneous charge dump:**
- Charging station delivers maximum available current to the supercapacitor bank, not the battery
- Capacitors accept the full instantaneous current spike (their natural strength)
- Grid sees a large but brief demand spike rather than a sustained high-power draw
- Charge time to capacitor bank: seconds to minutes

**Stage 2 — Capacitor trickle charges battery on the move:**
- While the vehicle is in motion, the capacitor bank trickles stored energy into the battery pack at the battery's optimal charge rate
- Battery receives smooth, controlled DC — extending cycle life significantly
- Driver experiences instant "full charge" at the station; battery fills properly during the journey

**Stage 3 — Regenerative braking feeds capacitors, not batteries:**
- Regenerative braking produces sharp, high-current spikes — ideal for capacitors, damaging for batteries
- Caps absorb the spike instantly, protect the battery from current stress
- Caps then trickle recovered energy back to the battery at a safe rate

## Problems Solved

1. **Grid infrastructure:** Current fast-charging requires 150–350kW sustained draw per vehicle. With cap buffering, the grid sees a brief spike and the station infrastructure is simpler and cheaper.

2. **Battery longevity:** High-rate charging is the primary cause of battery degradation. Cap buffering means the battery never sees a fast charge — only a slow, safe trickle.

3. **Regenerative braking efficiency:** Batteries cannot efficiently absorb the sharp current spikes from hard braking. Caps capture 100% of available regen energy, batteries capture a fraction.

4. **Charging experience:** User experience is instant — plug in, caps fill, drive away. Battery continues filling en route.

## Key Components

- Supercapacitor bank (high energy density, fast charge/discharge)
- Bidirectional DC-DC converter between cap bank and battery pack
- Charge management controller — monitors cap state, battery state, drive load
- Regenerative braking integration at cap bank input

## Prior Art Note

This concept was originated by Bryan Horsfield several years prior to this 2026-08-05 written disclosure, at the time EVs were first entering mainstream discussion. The specific combination of: supercapacitor buffer at charging input + trickle charge to battery while driving + regenerative braking directed to caps not battery — as a unified architecture — constitutes the novel claim.
