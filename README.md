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
## 🔧 如何使用

1.  **打开项目**: 使用 STM32CubeIDE 或 Keil uVision 打开项目。
2.  **检查配置**: 打开 `.ioc` 文件，确保 PWM 通道已正确配置 (TIM1, Channel 1 对应 PA8)。
3.  **编译下载**: 编译代码并下载到你的 STM32 开发板。
4.  **连接硬件**: 按照上面的接线说明连接 LED 和按键。
5.  **操作使用**: 上电后，LED 应该被点亮，通过按下 PA9 连接的按键可以切换亮度模式或调整亮度。
##  📝 学习要点
通过本项目，你可以学习到：

STM32CubeMX 的基本使用方法

STM32 HAL 库中定时器 (TIM) 的配置与使用

PWM 波形的原理及其在调光中的应用

GPIO 输入（按键）的处理方式

如何将软件配置与硬件外设连接起来

## 🤝 参与贡献
欢迎提交 Issue 和 Pull Request 来改进这个项目！

Fork 本仓库

创建你的特性分支 (git checkout -b feature/AmazingFeature)

提交你的改动 (git commit -m 'Add some AmazingFeature')

推送到分支 (git push origin feature/AmazingFeature)

打开一个 Pull Request

© 许可证
本项目基于 MIT 许可证开源。详情请查看 LICENSE 文件。

如果这个项目对你有所帮助，请给它一个 ⭐ Star ！谢谢！
