<div align="center">
  <a href="https://github.com/JMU-Underwater/Underwater-Vehicle-Electrical-Control-System"><img src="./img/image.png" alt="logo"></a>
  <a href="https://github.com/JMU-Underwater/Underwater-Vehicle-Electrical-Control-System"><h1>Underwater Vehicle Electrical Control System</h1></a>
</div>

[ 中文 | [English](README_EN.md) ]

## 项目介绍

该模组化电控以国产SoC（System on Chip）瑞芯微RV1103与国产MCU（Microcontroller Unit）乐鑫ESP32S3构建异构计算架构，两者通过高速UART串口进行高效通讯，通过高低搭配实现任务优化分配：

### RV1103

搭载ARM Cortex-A7（1.2GHz）与NPU（0.5TOPS），可专责水下航行器高负载高难度任务，包括：

- 水下图像实时处理（如图像重建、目标识别及浑浊度补偿等任务）；

- DVL、USBL及光纤惯导等多传感器数据融合的航迹解算；

- 千兆以太网视频流的H264/H265编解码压缩与网络透传。

### ESP32-S3:

搭载Xtensa 32位LX7双核微处理器功耗特性，依托其强大外设与低功耗特性，负责水下航行器姿态解算与实时控制：

- 扩展多路模拟/数字调制控制接口，驱动水下航行器动力系统；

- 水下航行器姿态解算及运动闭环控制；

- UART、I2C、SPI及CAN等多路工业通讯总线拓展；

- 硬件看门狗复位监测与电控故障恢复控制机制。

### 电源管理

选用效率表现较优秀的同步Buck拓扑，采用多路Buck级联的方式，构建多路电源。分别控制瑞芯微RV1103其SoC模组内核、储存及外设模组的上电时序与软启动时间。同时，集成同步降压控制器，实现电控宽电压输入，使得电控可以灵活适应不同的供能场景。

### 通讯管理

通过RV1103与集成千兆交换机，控制线路阻抗，构建低时延、高带宽的视频流与控制信号传输通道。支持4K30FPS视频流传输与高实时控制命令输入。同时，通过ESP32S3的强大的外设支持与通讯收发器的集成，扩展RS485/232、I2C、SPI、UART等多种工业通讯总线，保证电控系统的拓展性。

## 相关链接

  - `硬件构建` : By[@SFerret](https://github.com/SFerret)  [基于RV1103与ESP32的水下航行器控制系统](https://github.com/JMU-Underwater/Underwater-Vehicle-Electrical-Control-System)
  - `软件搭建` : By[@Xiao](https://github.com/sfxfs)  [基于 Linux 平台的通用型水下机器人控制程序](https://github.com/JMU-Underwater/sub-navi)
