# Robot Skill Marketplace Standard

**Date:** 2026-08-20  
**Author:** madazz01  
**Status:** Prior art disclosure — all rights reserved by author

---

## Concept

A portable robot skill program format tied to an open hardware dock standard, enabling a cross-manufacturer community marketplace of downloadable robot skills.

A user teaches their robot to cook a meal. They upload the skill. Anyone else running a compatible body downloads it, and their robot can now cook that meal. A martial artist uploads a kata. A chef uploads a prep sequence. A cleaner uploads a folding routine. The community library grows continuously. Every body that implements the open dock standard can run every skill in the library.

**The standard is the infrastructure. The marketplace is the platform. The community is the moat.**

---

## Core Claims

### 1. Portable Robot Skill Programs

A robot skill program is a structured, portable behavior specification that can be transferred between any robot bodies implementing the open dock standard. Skills are not motion recordings — they are goal-directed programs containing:

- **Motor primitives** — parameterised joint angle targets, velocity profiles, and timing sequences expressed in terms of the dock protocol's servo command abstraction
- **Perception hooks** — conditional branches triggered by sensor feedback (camera, force/current sensing, proximity, IMU) that allow the skill to adapt to environmental variation
- **Goal conditions** — declarative completion criteria evaluated from sensor state (e.g. "onion is translucent", "joint angle within 2° of target", "object in hand is stable")
- **Calibration parameters** — environment-specific offsets that allow the same skill to execute correctly across different physical environments (different kitchens, different tools, different surfaces)

Because skills target the dock protocol abstraction layer rather than specific hardware, a skill created on one manufacturer's body runs on any other body implementing the same protocol.

### 2. The Dock Protocol as Common ABI

The open hardware dock protocol (see prior art: smartphone-docked-robot-brain, 2026-08-19) defines a hardware abstraction layer for robot bodies. This abstraction layer functions as an Application Binary Interface (ABI) for skill programs.

A skill program written against the dock ABI specifies:
- Servo commands in terms of DOF index, position target, velocity, and torque limit — not hardware-specific register addresses
- Sensor reads in terms of named sensor types (camera, IMU, proximity, force) — not hardware-specific bus addresses
- Timing in terms of abstract timesteps — not processor-specific clock cycles

Any body that correctly implements the dock protocol exposes the same ABI. Skills are therefore hardware-portable by construction — identical to how a compiled program targeting a standard ABI runs on any conforming CPU, regardless of manufacturer.

### 3. Open Standard + Controlled Marketplace — Intentional Strategic Architecture

The dock protocol is published as an open standard with prior art disclosure preventing patent capture by any party. This is intentional:

- Hardware manufacturers can implement the standard freely — no license fee, no permission required
- Manufacturers whose bodies do not implement the standard cannot offer customers access to the skill marketplace
- Adoption pressure flows from the community: users with skill library access choose compatible bodies; manufacturers implement the standard to remain competitive
- The open standard creates the market; the marketplace captures the value

This mirrors the MIDI standard (1983): published openly, universally adopted, with ecosystem value captured by platform builders rather than standard holders.

The marketplace — community curation, ratings, verified skill trees, creator royalties, skill bundles — is the proprietary layer. The standard is the commons.

### 4. Community Skill Marketplace

A platform enabling:

**Supply side:**
- Individual users upload skills they have taught their robot
- Professional skill creators (chefs, martial artists, physiotherapists, tradespeople) upload verified skill trees
- Skills are organised into primitives, programs, and bundles

**Demand side:**
- Users browse, download, and install skills to their robot's skill library
- Skills execute via the phone reasoning layer (see smartphone-docked-robot-brain prior art) orchestrating the body

**Marketplace structure:**
- **Motor primitives** — atomic physical operations: grasp, release, chop, stir, reach, balance-step (community, free)
- **Skill programs** — goal-directed task sequences built from primitives with perception hooks: chop onion, fold shirt, throw jab, pour liquid (community + premium)
- **Skill bundles** — curated collections: "complete kitchen prep", "beginner Muay Thai kata set", "household maintenance pack"
- **Verified master skills** — professional-origin skills with certification: Michelin-star chef knife technique, black belt kata sets

**Creator economy:**
- Skill creators earn royalties per download or subscription share
- Verification system for professional-origin skills
- Community ratings and execution success metrics

### 5. Skill Portability via Hardware Standard Adoption Pressure

Because skills only run on bodies implementing the dock standard, hardware manufacturers face a structural incentive:

- A body that does not implement the standard offers customers access to zero community skills
- A body that implements the standard offers customers access to the full community library
- As the library grows, non-implementing bodies become less attractive
- Manufacturers adopt the standard to remain viable — without licensing, without permission, without negotiation

This creates a self-reinforcing adoption loop:
- More compatible bodies → more skill creators → larger library → more users choose compatible bodies → more compatible bodies

The open prior art prevents any single manufacturer from capturing the standard and charging rent. The marketplace operator captures platform value without owning the hardware layer.

### 6. Perception-Driven Skill Execution

Skills are not kinematic recordings. Goal-directed skills (cooking, manipulation, assembly) require environmental perception:

- **Visual perception hooks** — camera frames are passed to the phone's vision layer; skill execution branches based on visual state (ingredient colour, object position, completion state)
- **Force feedback** — servo motor current provides tactile feedback; skill execution adapts grip force, detects resistance, confirms object acquisition
- **Proprioceptive feedback** — IMU and servo position feedback confirm execution accuracy and trigger error recovery branches
- **Environmental calibration** — first-run calibration pass measures tool dimensions and workspace geometry; subsequent executions use calibrated offsets

The phone reasoning layer (Aris or equivalent) orchestrates perception evaluation between motor primitive executions. The body executes motor commands; the phone evaluates whether goal conditions are met and selects the next primitive.

### 7. Skill Composition and Primitive Libraries

Complex skills are composed from simpler primitives. A "chop onion" skill composes: grasp-object, stabilise-object, raise-blade, chop-stroke (repeat N), release. Each primitive is itself a portable skill program.

Users who cannot create full skills can still contribute: uploading a new motor primitive (a particular grip technique, a balance step variant) extends the primitive library that more complex skills are built from.

### 8. Cross-Body Skill Calibration

The same skill may require minor calibration when transferred to a different body — different servo count, different link lengths, different sensor positions. The dock protocol includes a body capability manifest (see NFC handshake prior art, 2026-08-19) that the skill runtime reads on first execution to auto-derive calibration parameters.

Calibration is one-time per body per skill. Subsequent executions use stored calibration.

---

## Why This Is Novel

All prior robot skill systems require at least one of:
- Hardware-specific encoding — skills are not portable between manufacturers
- Developer-only tooling — no community creation or sharing mechanism
- Motion capture / kinematic recording — no environmental perception or adaptation
- Closed ecosystem — skill libraries controlled by the robot manufacturer, not the community

This disclosure eliminates all four limitations:
- Skills target the open dock standard ABI — portable across any conforming body
- Creation tooling is accessible to any user who can teach their robot a task
- Skills are goal-directed programs with perception hooks — not recordings
- The marketplace is community-operated under an open standard — no manufacturer controls it

---

## Relationship to Prior Art

This disclosure extends the smartphone-docked-robot-brain architecture (filed 2026-08-19, same author):

- The dock protocol defined in that filing is the ABI that makes skill portability possible
- The NFC capability manifest defined in that filing is the mechanism for cross-body skill calibration
- The phone reasoning layer defined in that filing is the orchestration runtime for perception-driven skill execution

The skill marketplace standard is a dependent claim — it requires the dock protocol as infrastructure. Both are claimed by the same author on consecutive days.

---

## Prior Art Statement

This concept was conceived on 2026-08-20 and committed to this public repository on the same date. The author asserts this disclosure as prior art against any future patent claims covering:

- A portable robot skill program format targeting a hardware abstraction layer defined by an open dock standard
- A community marketplace for downloadable robot skill programs portable across hardware manufacturers
- The intentional architectural split between open hardware standard and controlled skill marketplace as a platform adoption strategy
- Perception-driven skill execution where goal conditions are evaluated by a phone-side reasoning layer between motor primitive executions
- Visual perception hooks and force feedback loops within portable skill programs
- Cross-body skill calibration derived from the NFC dock capability manifest
- Hardware adoption pressure created by community skill library access as an incentive for manufacturers to implement an open standard
- Skill program composition from reusable motor primitives contributed by the community
- Creator royalty systems for robot skill program marketplaces

This disclosure is released publicly to prevent patent monopolisation. The author retains all rights to commercialise implementations.

&copy; 2026 madazz01. All rights reserved.
