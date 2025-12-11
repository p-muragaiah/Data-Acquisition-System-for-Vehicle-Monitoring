📘 Project Explanation – Data Acquisition System using LPC2129
The Data Acquisition System (DAS) developed in this project is a real-time embedded monitoring system built using the LPC2129 ARM7 microcontroller. Its purpose is to continuously collect, process, and display sensor data such as temperature, voltage, and light intensity while also timestamping every reading using an RTC module. This makes the system capable of being used in applications like vehicle monitoring, environmental sensing, industrial automation, and IoT data logging.

🔧 Core Idea of the Project
The main objective is to design a system that can:
Read real-time analog sensor values
Convert and process the data
Display results on an LCD
Send the same data to a PC for logging
Add accurate timestamps using an RTC module
The project demonstrates how multiple communication protocols (I2C, SPI, UART, ADC) can work together under a single microcontroller to build a reliable and expandable monitoring platform.

⚙️ How the System Works
1. Initialization
When powered on, the LPC2129 initializes its peripherals:
I2C → To communicate with DS1307 RTC
SPI → For reading LDR values via MCP3204 ADC
ADC → For onboard LM35 temperature sensor and potentiometer
UART → For sending data to the PC
LCD → For displaying real-time outputs

2. Sensor Data Acquisition
The system continuously reads three sensors:
✔ LM35 Temperature Sensor (Onboard ADC)
Output voltage is proportional to temperature (10mV per °C)
ADC value → Converted to °C
✔ Potentiometer (Onboard ADC)
Acts as a voltage variation input
Used to test ADC accuracy and calibration
✔ LDR Sensor (External MCP3204 via SPI)
The MCP3204 provides 12-bit precision
Light intensity is converted into a percentage value

3. Time Stamping Using DS1307 (I2C)
The Real-Time Clock provides:
Hours
Minutes
Seconds
Day of the week
AM/PM
This ensures every reading is precisely time-stamped for meaningful logging.

4. Displaying Data
The processed values are shown on a 16×2 LCD, including:
Time (HH:MM:SS AM/PM)
Day
Temperature (°C)
Pot voltage (V)
Light intensity (%)

5. Sending Data via UART
All sensor readings and timestamps are also transmitted to a PC terminal. Example output:
11:00:55 AM WED
T:29.50 C  pot:2.31V  Light:68%
This enables remote monitoring, data logging, and further analysis.

🔬 Why This Project Is Useful
Demonstrates real-time sensor integration
Uses multiple communication interfaces together (I2C+SPI+UART+ADC)
Helpful for applications like:
Vehicle health monitoring
IoT data logging
Industrial measurement systems
Environmental monitoring

🚀 Key Takeaways
Shows strong understanding of embedded C, ARM microcontroller architecture, and driver developmentś
Provides experience with register-level programming

Demonstrates how different sensors and modules work together in real time

Builds a foundation for advanced embedded systems and IoT projects
