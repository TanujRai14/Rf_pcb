📡 STM32 + nRF24L01P USB Dongle (4-Layer PCB)

This project implements a USB-based transceiver dongle using the STM32L432 MCU and nRF24L01P RF module.
The board is designed as a 4-layer PCB optimized for USB high-speed signaling and RF performance.

🔧 Features

MCU: STM32L432KBU6 (Cortex-M4, USB support, low-power).

RF Transceiver: nRF24L01P with SMA antenna connector.

USB Interface: Micro USB-B with ESD protection.

Power Regulation: Onboard 3.3V regulator with USB +5V input.

Programming & Debugging: SWD connector for firmware upload/debug.

Clocking: 16 MHz crystal oscillator for the transceiver.

⚡️ PCB Design Notes

This design follows best practices for mixed-signal (USB + RF) high-speed boards:

4-Layer Stackup

Layer 1: Signal

Layer 2: Ground plane

Layer 3: Power plane + signal

Layer 4: Signal

➝ Provides controlled impedance routing and solid ground return paths.

USB Differential Pair

Routed as 90 Ω differential impedance.

Length matched using squiggle traces for proper signal timing.

Minimal via usage to reduce reflections.

Crystal Oscillator

No ground plane directly beneath the crystal to avoid damping oscillations.

RF Section

50 Ω controlled impedance routing to the SMA connector.

Antenna matching network (L-C components) placed close to RF pin.

Short traces and minimized via count for RF integrity.

Decoupling & Power Integrity

Multiple ceramic capacitors (100nF, 1µF, 10µF) placed near VDD pins.

Bulk capacitor on regulator output for stability.

Power traces kept short and wide to reduce IR drop.

Grounding

Continuous solid GND plane on Layer 2.

Stitching vias placed around high-speed and RF sections.

Segregation of analog/RF and digital sections to reduce noise coupling.

Other Notes

ESD protection diodes added on USB lines.

Reset capacitor for parasitic reset protection.

Careful placement of SWD pins for easy programming access.



🚀 Getting Started

Connect the board via USB Micro-B cable.

Flash firmware via SWD programmer (ST-Link, J-Link, etc.).

Use the USB interface for communication and debugging.

Attach an SMA antenna to nRF24L01P for wireless operation.

📌 To-Do / Future Improvements

 Add test points for power rails.

 Consider shielding can for RF section.

 Explore USB Type-C instead of Micro-B.

 Improve thermal relief on regulator section.

👤 Designer: Tanuj Rai
🛠 Tools Used: KiCad (schematic & PCB), 4-layer controlled impedance design.# Rf_pcb
