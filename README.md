## **Project 2: Interfacing a Microphone Sensor**

### **Objective**
Interface a microphone sensor with the STM32 microcontroller and display live ADC values over UART.

### **Steps**
1. **Create a New Project:**
   - Follow the same steps as Project 1 to set up the project in STM32CubeIDE.

2. **Configure Peripherals:**
   - Configure the ADC (12-bit resolution) for the microphone input.
   - Set up UART for serial communication with a default baud rate of 15200.

3. **Code Implementation:**
   - Edit the `main.c` file to include the following code:
     ```c
     int mic;

     while (1) {
         HAL_ADC_Start(&hadc1);
         HAL_ADC_PollForConversion(&hadc1, HAL_MAX_DELAY);
         mic = HAL_ADC_GetValue(&hadc1);
         printf("MIC VALUES: %d\r\n", mic);
         HAL_Delay(500);
     }

     int __io_putchar(int ch) {
         HAL_UART_Transmit(&huart2, (uint8_t*)&ch, 1, HAL_MAX_DELAY);
         return ch;
     }
     ```

4. **Build and Run:**
   - Build the project and run it.
   - Observe the microphone sensor values displayed on the serial monitor.

---

## **Requirements**
- STM32CubeIDE
- STM32 Board
- Microphone Sensor
- USB Debugger Cable

---

## **Outputs**
- **Project 1:** Blinking onboard LED.
- **Project 2:** Real-time microphone ADC values displayed on the serial monitor.

---

## **How to Use This Repository**
1. Clone the repository:
   ```bash
   git clone <repository-link>
   ```
2. Open the project in STM32CubeIDE.
3. Follow the instructions in the respective project folder to set up and run the code.

---

Feel free to reach out for any questions or suggestions! 😊
