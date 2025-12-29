# STM32H7 Nucleo-144 Wi-Fi 6E Integration (Adapter Card)

**A stackable Wi-Fi 6E integration on the Dual-Core NUCLEO-H745ZI-Q using the Ezurio STM32 Nucleo Adapter Card.**

![Project Status](https://img.shields.io/badge/Status-Finished-success)
![Hardware](https://img.shields.io/badge/Hardware-NUCLEO--H745ZI--Q-blue)
![Connectivity](https://img.shields.io/badge/Module-Sona_IF573_(WiFi_6E)-orange)

## 📖 Overview
This project demonstrates how to integrate the **Ezurio (Laird Connectivity) Sona IF573** (Wi-Fi 6E) module with the **STM32 NUCLEO-H745ZI-Q** development board.

Utilizing the **Ezurio STM32 Nucleo Adapter Card**, this integration offers a **stackable, plug-and-play** solution via the Nucleo-144 headers. This project specifically addresses the complexities of the **Dual-Core (Cortex-M7 + Cortex-M4)** architecture and implements critical software configurations for stable SDIO communication.

**Key Technical Challenge:** To ensure reliable SDIO signal integrity during initialization, this integration implements a manual **GPIO Pull-Up sequence** in software (`console_task.c`) before the Wi-Fi driver initializes. This workaround stabilizes the data lines (D0-D3) to prevent enumeration failures.

## 🛠️ Tech Stack
* **MCU:** STM32H745ZI (Dual Core: Cortex-M7 @ 480MHz + Cortex-M4 @ 240MHz)
* **Wireless:** Sona IF573 (Infineon CYW55572)
* **Interface:** M.2 to Nucleo-144 Adapter (SDIO)
* **RTOS:** FreeRTOS
* **Workaround:** Software-controlled GPIO Pull-Up initialization sequence.

## 📂 Documentation
The full application note is hosted in this repository and also published online.

### 🌐 [View the Official Published Guide](https://lairdcp.github.io/guides/IF573-NUCLEO-H745ZI/1.0/IF573_NUCLEO_H745ZI_Q_Guide.html)

You can also view the local version in the `docs` folder:

### [👉 Read the Local Integration Guide](docs/IF573_NUCLEO_H745ZI_Q_Guide.md)

* **Hardware Setup:** Utilizing the Nucleo Adapter Card for instant connectivity.
* **Dual-Core Config:** Migrating the AIROC stack to the H745ZI-Q platform.
* **Stability Fix:** Implementing the custom GPIO initialization sequence for SDIO lines.

## 📦 Resources
* **Source Code:** Derived from Infineon AIROC STM32 Expansion Pack v1.7.1.
* **Hardware Used:** NUCLEO-H745ZI-Q, Ezurio Nucleo Adapter Card, Sona IF573.

---
*Disclaimer: This project requires the specific Ezurio Adapter Card for correct pin mapping.*
