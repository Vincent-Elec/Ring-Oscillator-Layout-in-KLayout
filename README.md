# 5-Stage Ring Oscillator Layout (KLayout)

I built a hierarchical layout of a five-stage ring oscillator in KLayout, demonstrating my proficiency with electronic design automation and microelectronics. By creating reusable cells for essential primitives such as contact pads and transistors, I streamlined the design flow and made the circuit easily scalable for future iterations. Throughout the project I managed multiple lithography layers—P-implant, N-implant, oxide vias, and metal interconnects—to mirror the actual fabrication sequence and ensure accurate layer-to-layer alignment. The result is a clean, reusable layout that captures every key fabrication step while highlighting disciplined layer management and thoughtful cell hierarchy.

---

## Layers Used

| Layer (name) | Purpose | Visualization* |
|--------------|---------|----------------|
| `p_implant`  | P-type active region | Red, diagonal |
| `n_implant`  | N-type active region | Blue, diagonal |
| `metal`      | Top-level interconnect | Grey, diamond |
| `VIA`        | Contact openings through oxide | Red, squares |

---

## Cell Hierarchy

RingOscillator (top)
├─ transistor ← P/N implants + three ContactPads
│ └─ ContactPad ← 1 µm metal square + VIA
├─ interconnect_1 ← jumper between top-row devices
├─ interconnect_2 ← jumper between bottom-row devices
└─ interconnect_3 ← vertical bus + I/O pads


* **ContactPad** – Ensures consistent pad and via geometry.  
* **transistor** – Encapsulates the device: implants + metal routing to three pads.  
* **RingOscillator** – A **5 × 2 array** of `transistor` cells (10 inverters) plus reusable interconnect cells to complete the loop.

---

## Build Summary

The five-stage ring oscillator was assembled using KLayout’s core drawing tools:

* Rectangle / Box for implant regions.  
* Instance & Array for repeating cells.  
* Path for metal routing.  
* Custom hierarchy levels to toggle between outlines and full detail.

A screenshot of the final layout is included in **`KLayout Ring Oscillator.png'**.


