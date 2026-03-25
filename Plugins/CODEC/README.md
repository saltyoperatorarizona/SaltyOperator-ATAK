# CODEC — Team Biometric Uplink Plugin


![CODEC HUD](CODEC-HUD-Preview.png)


## Overview


CODEC is a free, open-source ATAK plugin that monitors real-time heart rate data from Bluetooth Low Energy (BLE) heart rate sensors and displays it in a military video game-style HUD for the entire team. Named after the iconic codec communication screen from Metal Gear Solid, the plugin gives team leaders and operators a live view of every member's biometric status — directly inside ATAK.


Compatible with any standard BLE heart rate monitor (Polar H10, Wahoo TICKR, Garmin HRM-Pro, Coospo HW807, and others). No proprietary hardware required.


---


## Screenshots


**CODEC embedded live inside ATAK — biometric panel runs alongside the map in real time**

The CODEC panel docks to the right side of the ATAK map view. Team leaders see every operator's live heart rate, EKG waveform, and status card without leaving situational awareness.

---

**All operators ALIVE — normal heart rates across the team**

![All Operators Alive](images/CODEC-team-alive-all.png)

With all BLE sensors connected and heart rates within range, each operator card displays a green ALIVE status. GHOST reads 72 BPM, HAVOC 80 BPM, and REAPER 69 BPM — each with a live animated EKG trace. The header shows ACTIVE 4/4 and ACTIVE LINKS 4/4 confirming full team connectivity.

---

**Tachycardia and Bradycardia alerts — CODEC detects abnormal heart rates**

![Tachycardia and Bradycardia Alerts](images/CODEC-tachy-brady-alerts.png)

CODEC continuously monitors each operator's BPM against configurable thresholds. Here, HAVOC (Wahoo TICKR) is flagged TACHY at 152 BPM — amber card with elevated EKG. REAPER (Coospo HW807) shows BRADY at 44 BPM — blue card with suppressed waveform. These alerts give the team leader an immediate visual cue without radio calls.

---

**Running Demo Mode — simulate a 4-operator team scenario**

![Run Demo Mode Dialog](images/CODEC-run-demo-dialog.png)

The built-in demo mode adds 4 simulated operators for 30 seconds, cycling through all biometric states including ALIVE, TACHYCARDIA, BRADYCARDIA, and OPERATOR DOWN. Uses a 5-second KIA timeout so you can see all card states without a live sensor. Useful for training and plugin evaluation.

---

**Demo complete — uplink terminated**

![Demo Complete](images/CODEC-demo-complete.png)

After the demo run concludes, CODEC notifies the operator that the simulated uplink has been terminated and returns to the idle state (ACTIVE 0/0). From here the operator can scan for real BLE devices, manage the team roster, or run another demo.


---


## Features


- Live BPM display per operator with animated EKG waveform


- Multi-operator grid — 1 column portrait, 2 column landscape, auto-switching


- Four operator states with distinct color coding:


  - 🟢 ALIVE — normal heart rate, green EKG


  - 🟡 TACHYCARDIA — HR above threshold, amber EKG and warning label


  - 🔵 BRADYCARDIA — HR below threshold, blue EKG and warning label


  - 🔴 OPERATOR DOWN — signal lost beyond KIA timeout, red banner with glitch effect


- HR trend indicator — arrow shows rising ↑, falling ↓, or stable →


- BLE signal strength (RSSI) and time since last reading per card


- Configurable KIA timeout — operator marked down after X seconds with no signal (default 60s)


- Per-operator HR thresholds — custom bradycardia and tachycardia limits per team member


- Three team setup methods — scan and pair, auto-match from ATAK contacts, or pre-configure roster


- Persistent team roster — members and thresholds saved across sessions


- CoT integration — HR broadcast as remark on existing SA contact, visible to all ATAK clients
