# STM32 HAL 库 PWM 波形控制台灯项目

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)[![条款:](https://img.shields.io/badge/License-MIT-yellow.svg)] (https://opensource.org/licenses/MIT)

## 📖 项目简介

一个基于 STM32 HAL 库的项目，通过生成 PWM (脉冲宽度调制) 波形来控制一个台灯的亮度。本项目是学习 STM32 定时器和 PWM 应用的实践示例。

## 🚀 功能特性

- ✅ 使用 STM32 的定时器 (TIM) 产生 PWM 信号
- ✅ 通过按键控制动态调节占空比，从而改变台灯亮度
- ✅ 基于 STM32CubeMX 配置生成代码，使用 HAL 库驱动
- ✅ 清晰的代码结构，方便初学者学习和修改

## 🛠 硬件要求

- **主控芯片**: STM32F103C8T6 (或其他STM32系列芯片)
- **开发板**: 最小系统板或 Nucleo 板
- **台灯**: 可使用 LED 灯 + 电阻替代，或直接控制低压直流台灯
- **按键**:  tactile switch 或任何常开按钮

## 📋 引脚配置与接线说明

| STM32 引脚 | 连接对象         | 说明 |
| :--------- | :--------------- | :--- |
| `PA8`      | LED 正极         | PWM 输出引脚，控制LED亮度 |
| `GND`      | LED 负极         | 共地 |
| `PA9`      | 按键一端         | 按键输入引脚，用于控制模式/亮度 |
| `GND`      | 按键另一端       | 按键接地 |

## 🏗 软件架构
项目根目录/
├── Core/
│ ├── Inc/ # 头文件
│ └── Src/ # 源文件 (main.c, gpio.c, tim.c等)
├── Drivers/ # STM32 HAL 库驱动
├── README.md # 项目说明文件 (当前文件)
└── PWM控制台灯.ioc # STM32CubeMX 配置文件
