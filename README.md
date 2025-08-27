# 8051 ADC0808 Interfacing Experiment

## Project Overview
This project demonstrates interfacing the **ADC0808** analog-to-digital converter with the **8051 microcontroller**. The goal is to read analog signals, convert them to digital values using the ADC0808, and display the result on an **LCD**.

- **Microcontroller:** AT89C51 (8051)
- **ADC:** ADC0808
- **Display:** 16x2 LCD
- **Development Environment:** Keil uVision
- **Simulation Software:** Proteus

---

## Circuit Description
- The ADC0808 converts the analog input into an 8-bit digital value.
- The 8051 reads the digital data from the ADC via port P1.
- Control signals for ADC (`ALE`, `START`, `EOC`, `OE`) are connected to P0 pins.
- The 16x2 LCD is connected to port P2 and control lines to P3 for displaying the ADC value.
- Potentiometers (`RV1`, `RV2`) are used for adjustable input signals in simulation.

**Proteus Simulation Screenshot:**

![ADC0808 Interfacing](adc_0808_8051_interfacing.png)

---

## Files in Repository
- `adc_0808_code.c` : Keil C source code  
- `adc_0808_8051.uvproj` : Keil project file  
- `adc_0808_8051.pdsprj` : Proteus project file  
- `adc_0808_8051.hex` : Compiled hex file for 8051  
- `adc_simulation.png` : Screenshot of Proteus simulation  

---

## How to Run
1. Open the Keil project (`.uvproj`) in **Keil uVision**.  
2. Compile the code to generate the `.hex` file.  
3. Open the Proteus project (`.pdsprj`) in **Proteus**.  
4. Load the compiled `.hex` file into the AT89C51 microcontroller in Proteus.  
5. Run the simulation and observe the analog-to-digital conversion displayed on the LCD.

---

## Code Explanation
- `adcinit()` : Initializes ADC control lines.  
- `adcstrtconv()` : Starts the ADC conversion.  
- `adcread()` : Waits for ADC conversion to complete and enables data output.  
- `lcdcmd()` : Sends command instructions to the LCD.  
- `display()` : Displays a single character on the LCD.  
- `main()` : Continuously reads ADC values and displays them on the LCD after converting to ASCII digits.

---

## Notes
- Ensure all Proteus connections match the port assignments in the code.  
- Only essential files are included; intermediate build files like `.obj` or `.bak` should be ignored using `.gitignore`.

