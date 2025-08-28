# STM32 HAL 库 PWM 波形控制台灯项目

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)[![条款:](https://img.shields.io/badge/License-MIT-yellow.svg)] (https://opensource.org/licenses/MIT)

## 📖 项目简介

一个基于 STM32 HAL 库的项目，通过生成 PWM (脉冲宽度调制) 波形来控制一个台灯的亮度。本项目使用 STM32 的定时器产生 PWM 信号，通过按键控制来调节占空比，从而实现 LED 灯光的平滑调光效果。这是学习 STM32 定时器和 PWM 应用的绝佳实践示例。

## 🚀 功能特性

- 使用 STM32 的定时器 (TIM) 产生 PWM 信号
- 通过 PA9 引脚连接的按键动态调节 PWM 占空比
- 使用 PA8 引脚输出 PWM 信号控制 LED 亮度
- 基于 STM32CubeMX 配置生成代码，使用 HAL 库驱动
- 清晰的代码结构，方便初学者学习和修改
- 支持多级亮度调节，提供平滑的灯光变化效果

## 🛠 硬件要求

- **主控芯片**: STM32F103C8T6 (或其他 STM32 系列芯片)
- **开发板**: 最小系统板或 Nucleo 板
- **LED**: 高亮度 LED 灯 (建议加装适当限流电阻)
- **按键**: 轻触开关或任何常开按钮
- **其他**: 杜邦线、面包板、电阻（220Ω-1kΩ）

## 📋 引脚配置与接线说明

| STM32 引脚 | 连接对象         | 说明 |
| :--------- | :--------------- | :--- |
| `PA8`      | LED 阳极（正极） | PWM 输出引脚，控制 LED 亮度 |
| `GND`      | LED 阴极（负极） | 共地连接 |
| `PA9`      | 按键一端         | 按键输入引脚，用于亮度调节 |
| `GND`      | 按键另一端       | 按键接地 |

**注意**: 建议在 LED 上串联一个 220Ω-1kΩ 的限流电阻，以保护 LED。

## 🏗 软件架构
STM32_PWM_LED_Control/
├── Core/
│ ├── Inc/ # 头文件目录
│ └── Src/ # 源文件目录
├── Drivers/ # STM32 HAL 库驱动文件
├── README.md # 项目说明文档
└── STM32_PWM_LED.ioc # STM32CubeMX 配置文件

## 🔧 如何使用

### 硬件准备
1. 按照上述引脚配置表连接电路
2. 确保所有连接牢固无误
3. 检查电源连接是否正确

### 软件准备
1. **打开项目**: 使用 STM32CubeIDE 或 Keil uVision 打开项目
2. **检查配置**: 打开 `.ioc` 文件，确认以下配置：
   - PA8 配置为 TIM1_CH1 PWM 输出
   - PA9 配置为 GPIO 输入模式（建议使用上拉电阻）
   - 定时器 TIM1 已正确配置为 PWM 模式
3. **生成代码**: 如有修改，使用 STM32CubeMX 重新生成代码
4. **编译下载**: 编译代码并下载到 STM32 开发板

### 操作说明
1. 上电后，LED 将以默认亮度点亮
2. 按下 PA9 连接的按键可以循环切换不同的亮度级别
3. 每次按键按下，LED 亮度会在多个预设级别间循环切换

## 📝 学习要点

通过本项目，你可以学习到：

- STM32CubeMX 的基本配置和使用方法
- STM32 HAL 库中定时器 (TIM) 的配置与使用
- PWM 波形的原理及其在调光中的应用
- GPIO 输入（按键）的处理方式和简单的防抖技术
- 如何将软件配置与硬件外设连接起来
- 嵌入式系统中的状态机设计和实现

## 🔮 扩展功能建议

1. **渐变调光**: 实现按下按键时亮度平滑渐变，而不是阶梯式变化
2. **呼吸灯效果**: 添加呼吸灯模式，使 LED 呈现呼吸般的明暗变化
3. **多模式切换**: 实现多种灯光模式（常亮、闪烁、呼吸等）的循环切换
4. **亮度记忆**: 增加 EEPROM 存储功能，记住上次设置的亮度级别
5. **远程控制**: 添加无线模块，实现通过手机或遥控器控制灯光

## 🤝 参与贡献

欢迎提交 Issue 和 Pull Request 来改进这个项目！

1. Fork 本仓库
2. 创建你的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的改动 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个 Pull Request

## © 许可证

本项目基于 MIT 许可证开源。详情请查看 [LICENSE](LICENSE) 文件。

---

**如果这个项目对你有所帮助，请给它一个 ⭐ Star ！谢谢！**
