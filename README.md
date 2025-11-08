# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.

   <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/b96ecbcc-6a03-4065-a8eb-d8dd5b81e0e9" />

2. Click **File → New STM32 Project**.
   
 <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/09fd5df8-a1d4-49e9-a74b-8cec00b6d0ce" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/f24ea587-9701-4b7d-b9a6-55cfda6ffa86" />

3. Select the **target microcontroller** or board and click **Next**.
   
   <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/3e798013-b74b-4c7f-a6d7-ce7b271dc3db" />

4. Name the project.
   
   <img width="533" height="588" alt="image" src="https://github.com/user-attachments/assets/63de2bab-69d4-4cb9-8db6-1b57adff9878" />

5. The corresponding `.ioc` file will be generated automatically.
   
   <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/f4441cd2-ef37-4cec-9cab-f16f65ee05fc" />

6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
    
   <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/6cd94fd2-9cda-4a8f-918b-1bd2cbcc4b4f" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
    
   <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/f1f4c736-c139-4111-9eb9-d2afc95e31e6" />

8. Edit the generated main program as required.
    
 <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/745fef57-05b5-4aee-99b3-0860e093e4dc" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/0185564b-0ef8-4c81-8d3e-ef97e5674f5d" />

9. Click **Project → Build All**.
    <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/04d241af-c691-4c2c-8e5a-455009fa82b1" />

10. Link the **HEX file** using the post-build process.
    
    <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/ce41d84c-2b20-4a6b-83d8-99d88aa22d62" />
   
11. Click **Debug** and connect the **STM Nucleo Board**.

    <img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/ddfa3663-6d8c-4f49-806c-bba115be483b" />

12. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 
![on](https://github.com/user-attachments/assets/5a304f95-fd5e-4292-8ce1-c8486eb8999f)

CASE 2: LED OFF
![off](https://github.com/user-attachments/assets/8f5e9b1f-7034-4b20-ac06-1772708d3db1)

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
