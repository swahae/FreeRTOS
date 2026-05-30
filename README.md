# FreeRTOS LED Blink and UART Communication on STM32F446RE

## 📌 Project Overview

This project demonstrates the implementation of **FreeRTOS multitasking** on the **STM32F446RE Nucleo Board** using **STM32CubeMX** and **STM32CubeIDE**.

The application creates three independent RTOS tasks that run concurrently:

1. **LED Task** – Blinks the onboard LED (PA5).
2. **UART Task** – Receives data through UART and echoes it back.
3. **Monitor Task** – Periodically sends a system status message over UART.

This project serves as an introductory example of task scheduling and multitasking using FreeRTOS.

---

## 🎯 Objectives

- Learn FreeRTOS task creation and scheduling.
- Configure STM32 peripherals using STM32CubeMX.
- Implement UART communication using HAL drivers.
- Understand concurrent execution of multiple tasks.
- Gain hands-on experience with STM32CubeIDE.

---

## 🛠 Hardware Requirements

- STM32F446RE Nucleo Board
- USB Type-A to Mini USB cable
- Windows PC/Laptop
- Serial Terminal (PuTTY/Tera Term)

---

## 💻 Software Requirements

- STM32CubeMX
- STM32CubeIDE
- ST-LINK Drivers
- PuTTY (for UART monitoring)

---

## ⚙️ Peripheral Configuration

### GPIO
| Pin | Function |
|------|----------|
| PA5 | Onboard LED Output |

### UART
| Peripheral | Configuration |
|------------|--------------|
| USART2 | 115200 Baud |
| Word Length | 8 Bits |
| Stop Bits | 1 |
| Parity | None |
| Mode | TX/RX |

### FreeRTOS Tasks

| Task Name | Priority | Function |
|------------|----------|----------|
| LED_TASK | Low | Blink onboard LED |
| UART_TASK | High | Receive and echo UART data |
| MONITOR_TASK | Normal | Print status message |

---

## 📂 Project Structure

```text
Core
├── Inc
│   └── main.h
│
├── Src
│   ├── main.c
│   ├── freertos.c
│   ├── stm32f4xx_it.c
│   └── stm32f4xx_hal_msp.c
│
Drivers
├── CMSIS
└── STM32F4xx_HAL_Driver

Middlewares
└── FreeRTOS
