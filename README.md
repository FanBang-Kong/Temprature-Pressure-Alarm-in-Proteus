# Temperature & Pressure Monitoring System (Arduino + OLED)

## 项目简介 / Project Overview

本项目是一个基于 **Arduino Uno** 的温度与压力综合监测系统，主要用于教学仿真与功能验证。系统集成了：

* 温度采集（LM35 模拟温度传感器）
* 压力采集（模拟压力传感器，kPa 级）
* OLED 显示（128×32，I2C）
* 按键菜单系统（主菜单 / HOME / SETTINGS）
* 定时中断 + 外部硬件中断
* 多状态指示灯与蜂鸣器告警逻辑

系统能够**实时显示温度、压力、变化趋势及诊断状态**，并在异常压力条件下进入**硬件级紧急保护模式**。

---

This project is a **temperature and pressure monitoring system** based on **Arduino Uno**, mainly designed for **educational simulation and functional verification**. The system integrates:

* Temperature measurement (LM35 analog sensor)
* Pressure measurement (analog pressure sensor, kPa scale)
* OLED display (SSD1306, 128×32, I2C)
* Button-driven menu system (Main Menu / HOME / SETTINGS)
* Timer interrupt and external hardware interrupt
* Multi-level LED and buzzer alarm logic

The system provides **real-time display of temperature, pressure, trends, and diagnostic messages**, and enters a **hardware emergency protection mode** under abnormal pressure conditions.

---

<img width="1934" height="1256" alt="SBC-23-1032+SBC-23-1033" src="https://github.com/user-attachments/assets/f2ce2869-e416-41f8-93f8-6eef37596a07" />

## 系统功能 / System Features

### 1. 温度监测 / Temperature Monitoring

* 使用 LM35 传感器采集温度
* 支持低/高温阈值可调（电位器输入）
* 三色 LED 指示状态：

  * 绿色：正常
  * 黄色：偏低
  * 红色：超限
* 温度趋势判断：UP / DN / ST（上升 / 下降 / 稳定）

### 2. 压力监测 / Pressure Monitoring

* 周期性定时采样（Timer1 中断，50 ms）
* 压力趋势判断（UP / DN / ST）
* 三色 LED + 蜂鸣器告警逻辑
* 压力异常诊断（如泄漏、堵塞、泵故障等）

### 3. OLED 显示界面 / OLED User Interface

* HOME 页面：

  * 实时温度、压力数值
  * 温度 / 压力趋势
  * 阈值范围显示
  * 系统诊断信息
* SETTINGS 页面：

  * 参数单位显示
  * 自动返回主菜单倒计时
* 主菜单支持按键切换页面

### 4. 紧急保护机制 / Emergency Protection

* 外部硬件中断（LM393 → INT0）
* 触发条件下：

  * 所有 LED 点亮
  * 蜂鸣器持续报警
  * OLED 显示严重警告信息
  * 系统逻辑锁死，需断电重启

---

## 按键说明 / Button Description

| 引脚 | 功能 / Function          |
| -- | ---------------------- |
| D3 | 菜单切换 / 向上移动（UP / NEXT） |
| D4 | 返回 / 确认（BACK / ENTER）  |

---

## 硬件与软件环境 / Environment

### 硬件 / Hardware

* Arduino Uno
* LM35 温度传感器
* 模拟压力传感器
* OLED（128×32，I2C）
* LM393 比较器（压力紧急中断）
* LED × 多个
* 有源蜂鸣器

### 软件 / Software

* Arduino AVR Core
* **Proteus 8.17**（仿真环境）

---

## 版本声明 / Version Information

* **仿真平台 / Simulation Platform**: Proteus **8.17**
* **目标处理器 / Target MCU**: Arduino Uno (ATmega328P)
* **编译环境 / Compiler**: Arduino AVR (Proteus Integrated)

本代码已在 **Proteus 8.17** 环境下完成搭建、仿真与验证。

This code was developed, simulated, and verified under **Proteus 8.17**.

---

## 说明 / Notes

* 本项目主要用于学习与演示嵌入式系统中的：

  * 多传感器融合
  * 中断驱动设计
  * OLED 人机界面
  * 状态机与保护逻辑
* 可直接用于课程设计、实验报告或功能扩展原型。

---

## 作者与说明 / Author & Notes

* 项目包含多模块协作开发（标注为 KONG / TAN）
* 代码结构以**工程可读性与教学清晰度**为主要目标
* **Fanbang Kong**
* **[Qinyi Tan](https://github.com/Qinyi-Tan)**
---

**End of README**
