<div align="center">
  <a href="https://github.com/JMU-Underwater/Underwater-Vehicle-Electrical-Control-System"><img src="./img/image.png" alt="logo"></a>
  <a href="https://github.com/JMU-Underwater/Underwater-Vehicle-Electrical-Control-System"><h1>Underwater Vehicle Electrical Control System</h1></a>
</div>

[ English | [中文](README.md) ]

## Project Introduction  

This modular electronic control system adopts a heterogeneous computing architecture built with the domestic SoC (System on Chip) Rockchip RV1103 and the domestic MCU (Microcontroller Unit) Espressif ESP32S3. The two communicate efficiently via high-speed UART serial ports, achieving optimized task allocation through a high-low performance combination:  

### RV1103  

Equipped with an ARM Cortex-A7 (1.2GHz) and an NPU (0.5TOPS), it is dedicated to handling high-load, high-difficulty tasks for underwater vehicles, including:  

- Real-time underwater image processing (e.g., image reconstruction, target recognition, and turbidity compensation);  
- Trajectory calculation through multi-sensor data fusion (DVL, USBL, fiber-optic inertial navigation, etc.);  
- H264/H265 encoding/decoding compression and network transmission of gigabit Ethernet video streams.  

### ESP32-S3  

Leveraging the power-efficient Xtensa 32-bit LX7 dual-core microprocessor and its robust peripherals, it is responsible for the underwater vehicle's attitude calculation and real-time control:  

- Expanding multiple analog/digital modulation control interfaces to drive the underwater vehicle's propulsion system;  
- Attitude calculation and closed-loop motion control of the underwater vehicle;  
- Expansion of multiple industrial communication buses (UART, I2C, SPI, CAN, etc.);  
- Hardware watchdog reset monitoring and electronic control fault recovery mechanisms.  

### Power Management  

A highly efficient synchronous Buck topology is adopted, utilizing a multi-stage cascaded Buck design to construct multiple power rails. This setup separately controls the power-up sequence and soft-start timing for the RV1103 SoC module's core, storage, and peripheral modules. Additionally, integrated synchronous Buck controllers enable wide-voltage input, allowing the system to adapt flexibly to various power supply scenarios.  

### Communication Management  

Through the RV1103 and an integrated gigabit switch, line impedance is controlled to establish a low-latency, high-bandwidth channel for video streaming and control signal transmission. It supports 4K30FPS video streaming and high-realtime control command input. Meanwhile, the ESP32S3's extensive peripheral support and integrated communication transceivers expand industrial communication interfaces such as RS485/232, I2C, SPI, and UART, ensuring the scalability of the electronic control system.  

## Relevant Links  

  - **Hardware Construction**: By [@SFerret](https://github.com/SFerret)  [Underwater Vehicle Electrical Control System Based on RV1103 and ESP32](https://github.com/JMU-Underwater/Underwater-Vehicle-Electrical-Control-System)  
  - **Software Development**: By [@Xiao](https://github.com/sfxfs)  [Universal Underwater Robot Control Program Based on Linux Platform](https://github.com/JMU-Underwater/sub-navi)