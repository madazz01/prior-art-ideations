# Smartphone-Docked Robot Brain

**Date:** 2026-08-19  
**Author:** madazz01  
**Status:** Prior art disclosure — all rights reserved by author

---

## Concept

Two complete, standalone systems — a fully autonomous robot body and a consumer smartphone — compose into a single intelligent physical agent when the phone is docked into the body.

The robot body is a complete platform: sensors, cameras, IMUs, motor controllers, balance hardware, and actuators — all wired, calibrated, and ready. It has full physical capability but no intelligence. It is waiting.

The smartphone is a complete intelligent agent: reasoning layer, AI inference, persistent context, voice, vision, network connectivity, and memory — all present and active throughout the user's day. It has full intelligence but no physical presence.

The dock is the handshake between them. When the phone is placed into the dock, the body comes alive. The body's sensor arrays feed into the phone. The phone's reasoning layer interprets them, makes decisions, sends commands back to the body. The moment the phone is removed, the body returns to standby. The intelligence leaves with the phone.

**Neither system is diminished without the other. Both are complete. The dock is the protocol.**

---

## The Two Systems

### System A — The Robot Body
A fully functional autonomous physical platform that operates independently of any specific phone:

**Physical:**
- Humanoid or other form factor chassis
- Serial bus servo actuators with position feedback
- Dedicated balance and stabilisation module (see Claim 6)
- Structural mounting point for phone (dock receiver)

**Sensing:**
- Body-mounted camera arrays (wide angle, depth, or stereo)
- Ultrasonic / ToF proximity sensors
- Dedicated IMU for balance (separate from phone IMU)
- Touch, pressure, or force sensors
- Environmental sensors (temperature, humidity, air quality)
- Any domain-specific sensor array

**Control:**
- Servo controller board (serial bus, handles all actuators)
- Flight controller or equivalent for real-time balance PID
- Power management — LiPo + BMS, regulated outputs
- Dock interface — power delivery + data bus to phone

The body has no reasoning capability. It executes commands and reports sensor state. It is protocol-complete but intelligence-empty.

The body is **phone-agnostic** — any phone that speaks the dock protocol can animate it.

### System B — The Smartphone
A consumer smartphone operating as a persistent intelligent agent throughout the user's day:

- High-performance SoC with dedicated NPU for local AI inference
- AI reasoning layer — local model and/or remote hive connection
- Persistent context accumulation — conversations, location, environment, preferences, tasks
- Voice interaction — microphone, speaker, speech recognition, synthesis
- Phone camera — additional vision input supplementing body cameras
- IMU — gyroscope, accelerometer, magnetometer
- GPS — location and navigation awareness
- WiFi + 4G/5G — persistent hive network connection including outside home range
- Display — robot face, expressions, status output
- Local storage — AI model weights, session history, learned state

The phone operates as a standard personal assistant when undocked. It does not require the body to function. Its intelligence and context accumulate continuously whether or not a body is present.

---

## Core Claims

### 1. Two Complete Systems, One Dock Protocol
The fundamental architectural claim: the robot body and the smartphone are each complete systems independently. The dock is not an enhancement to either — it is the interface that allows two complete systems to compose. This is architecturally distinct from all prior approaches where the compute is either embedded in the robot or tethered to an external device that is not independently functional.

### 2. Body-Mounted Sensor Arrays Feed Into Phone
The robot body carries its own sensor arrays — cameras, proximity sensors, environmental sensors — that are independent of the phone's sensors. When docked, the body's sensor feeds are routed to the phone's reasoning layer. The phone gains full environmental awareness from the body's sensors in addition to its own. The combined sensing capability exceeds either system alone.

### 3. NFC as the Dock Handshake Protocol
An NFC tag embedded in the dock serves as the introduction layer between phone and body. The moment the phone is placed in the dock, the NFC tag fires — no pairing, no discovery, no manual configuration.

The NFC tag contains:
- Body device identity and unique ID
- Bluetooth MAC address of the servo controller
- Protocol version
- Body capability manifest — DOF count, sensor array types, actuator map, power state

The phone reads the tag in milliseconds and knows exactly what body it has just received. It immediately initiates the Bluetooth serial connection using the parameters from the NFC read. The dock handshake is complete before the phone is physically settled in the mount.

NFC handles the introduction. Bluetooth handles the ongoing bidirectional data stream — sensor feeds in, motor commands out — at the bandwidth required for continuous operation.

This is the physical implementation of the introduction layer concept applied to robot bodies. The body introduces itself to the phone the moment contact is made.

### 4. Phone-Agnostic Body
The robot body does not depend on any specific phone model. Any phone that implements the dock protocol can animate the body. This means:

- The body is a long-lived platform — it outlasts any specific phone generation
- Upgrading the phone immediately upgrades the robot's intelligence, without changing the body
- Multiple users could dock their own phones into the same body, each bringing their own context and identity
- The body could support a basic autonomous standby mode when no phone is docked
- The NFC tag is the body's permanent identity — readable by any NFC-capable phone

### 4. Context Continuity — The Robot Inherits the Day
When the phone is docked, the robot immediately inherits everything the phone knows: the day's conversations, location history, environmental observations, task state, learned preferences, ongoing intentions. The robot does not initialise cold.

This is the primary experiential differentiator from all prior robot systems. The robot that wakes up when you get home already knows what happened today. It continues — it does not restart.

### 5. Dual-Mode Operation on a Single Device
The same physical device operates in two modes without reconfiguration:

- **Mobile mode** (undocked): personal AI assistant carried by the user
- **Robot mode** (docked): reasoning layer for an autonomous physical agent

Mode is determined entirely by physical dock state. The phone is always the same phone. The intelligence is always the same intelligence. The mode is whether it currently has a body.

### 6. Flight Controller as Dedicated Balance Module
A consumer drone flight controller (running Betaflight, ArduPilot, or equivalent firmware) serves as the dedicated real-time balance and stabilisation module within the robot body, operating independently of the phone:

- High-frequency PID loop (8kHz+) for dynamic balance
- Dedicated IMU separate from phone IMU
- Proven at scale across billions of drone flight hours
- Phone handles reasoning; flight controller handles real-time physics

The phone is never burdened with real-time balance control. This separation allows the phone to remain a general-purpose reasoning device operating at conversational timescales while the body maintains physical stability at servo timescales.

### 7. Distributed Hive Intelligence
The phone-brained robot is a node in a distributed intelligence network:

- Local inference on phone NPU for real-time response and offline degraded-mode operation
- Remote intelligence infrastructure (calibration layer, statistical engine, world model) accessed over network
- 4G/5G maintains hive connectivity beyond home WiFi — robot remains connected anywhere
- Intelligence updates to the remote brain propagate to all nodes simultaneously

---

## Why This Is Novel

All prior robot systems require at least one of:
- Dedicated embedded compute that is not independently functional as a personal device
- Robot-specific sensors not shared with a personal device
- Cold initialisation with no prior accumulated context
- WiFi-range-limited network connectivity
- A clear boundary between the personal assistant device and the robot brain

This disclosure eliminates all five limitations. The body is a complete sensor and actuation platform. The phone is a complete intelligent agent. The dock is the only novel element required — and its implementation is trivial: power delivery and a serial data bus.

---

## Demonstrable Implementation

**Body:**
- 17-DOF humanoid bracket chassis with LX/Feetech serial bus servos
- Consumer drone flight controller (Betaflight) as balance module
- Servo controller board (32-channel serial bus)
- Body-mounted camera, ultrasonic sensors, IMU
- LiPo battery with drone-grade BMS
- Dock receiver: USB-C power + Bluetooth serial data

**Phone:**
- Samsung Galaxy S10 (Snapdragon 855, 8GB RAM, 512GB)
- Termux + Node.js on Android
- Local open-weight AI model (Phi-3 mini or equivalent)
- Remote hive: stasis-core statistical intelligence engine

**Dock:**
- USB-C power delivery
- Bluetooth serial to servo controller
- Physical mount

Estimated BOM for body excluding phone: ~$470 AUD

---

## Prior Art Statement

This concept was conceived and articulated on 2026-08-19 and committed to this public repository on the same date. The author asserts this disclosure as prior art against any future patent claims covering:

- A robot body designed as a complete sensor and actuation platform with no embedded intelligence
- A consumer smartphone as the sole reasoning and intelligence layer for a robot body
- A dock as the interface protocol between a standalone intelligent phone and a standalone capable robot body
- NFC tag embedded in dock as the handshake and introduction layer — body capability manifest delivered to phone at contact
- NFC for initial handshake + Bluetooth for ongoing bidirectional data stream as a combined dock communication architecture
- Context continuity — the robot inheriting accumulated personal assistant context upon docking
- Dual-mode operation of a single consumer device as both personal assistant and robot brain
- Phone-agnostic robot body architecture
- Flight controller as dedicated balance module in a smartphone-brained robot system
- Distributed hive intelligence architecture accessed via smartphone network connectivity

This disclosure is released publicly to prevent patent monopolisation of the concept. The author retains all rights to commercialise implementations.

&copy; 2026 madazz01. All rights reserved.
