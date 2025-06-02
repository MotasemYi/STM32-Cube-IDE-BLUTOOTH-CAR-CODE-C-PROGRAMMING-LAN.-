# STM32-Cube-IDE-BLUTOOTH-CAR-CODE-C-PROGRAMMING-LAN.-
This project demonstrates a Bluetooth-controlled car built using an STM32 microcontroller and programmed in C (HAL library). It allows the user to control motor directions (forward, backward, left, right, stop) via Bluetooth UART commands.
🧠 Project Overview
The STM32 receives commands from a Bluetooth module (e.g., HC-05) over UART. Based on the character received (F, B, L, R, S), the microcontroller:

Drives two motors using PWM signals generated from TIM2 and TIM3.

Sets the motor direction using GPIO pins.

🎮 Control Commands
| Command | Action     |
| ------- | ---------- |
| `F`     | Forward    |
| `B`     | Backward   |
| `L`     | Turn Left  |
| `R`     | Turn Right |
| `S`     | Stop       |


📦 Features
UART communication via USART1

Motor control using PWM via TIM2_CH1 and TIM3_CH1

Direction control using GPIOA pins:

PA0, PA1 for one motor

PA3, PA4 for the other

Reusable and expandable architecture

Full support for HAL-based STM32CubeIDE

⚙️ Technical Details
Microcontroller: STM32 (configured with STM32CubeMX)

Communication: UART (9600 baud)

PWM Timer Channels:

TIM2 Channel 1

TIM3 Channel 1

Development Tools:

STM32CubeMX

STM32CubeIDE

Peripheral Initialization:

GPIO: Motor direction

TIM2/TIM3: PWM speed control

UART1: Bluetooth input

🔁 How it Works
Bluetooth module sends a character via UART.

STM32 receives and parses the character.

Based on the command:

PWM values are set via __HAL_TIM_SET_COMPARE.

Direction is set via GPIO pin logic.

On S (stop), PWM is set to 0 and all motor pins are reset.

📝 Notes
This project can be extended to include:

Speed control via additional commands.

Mobile app integration.

Sensor inputs for obstacle avoidance.

Make sure the Bluetooth module TX/RX is connected to STM32’s UART1 p
