# Water Quality Monitoring Robot

This project involves a water quality monitoring robot that uses an Arduino to measure and log environmental parameters such as Temperature, pH, Oxygenation, and Water Clarity of a body of water, along with a timestamp. The data is then read by a Python script that also pulls weather data from an API, and plots each parameter in relation to the others for comprehensive analysis.

## Table of Contents
- [Hardware Components](#hardware-components)
- [Software Components](#software-components)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Data Analysis](#data-analysis)
- [Contributing](#contributing)
- [License](#license)

## Hardware Components
- **Arduino Board**: The central microcontroller that reads sensor data.
- **12V Lithium-Ion Battery**: Powers the Arduino and the sensors.
- **Temperature Sensor**: Measures the water temperature.
- **pH Sensor**: Measures the pH level of the water.
- **Dissolved Oxygen Sensor**: Measures the oxygenation level in the water.
- **Turbidity Sensor**: Measures the clarity of the water.
- **RTC Module**: Keeps track of the current time for timestamping the data.

## Software Components
- **Arduino Sketch**: Code to read data from the sensors and log it with timestamps.
- **Python Script**: Reads data from the Arduino, fetches weather data from an API, and plots the data.

## Setup and Installation

### Hardware Setup
1. **Assemble the components**:
   - Connect the Temperature, pH, Dissolved Oxygen, and Turbidity sensors to the appropriate analog or digital pins on the Arduino.
   - Connect the RTC module to the Arduino using the I2C interface.
   - Power the Arduino using the 12V Lithium-Ion battery.

2. **Wiring**:
   - Follow the specific sensor datasheets for proper wiring.
   - Ensure the RTC module is correctly connected to the SDA and SCL pins of the Arduino.

### Software Setup
1. **Arduino IDE**:
   - Install the Arduino IDE from the [official website](https://www.arduino.cc/en/software).
   - Install necessary libraries for the sensors and RTC module (e.g., `RTClib` for the RTC module).
   - Upload the provided Arduino sketch (`water_quality_monitor.ino`) to the Arduino board.

2. **Python Environment**:
   - Install Python 3 from the [official website](https://www.python.org/).
   - Install the required Python libraries:
     ```bash
     pip install requests matplotlib pandas
     ```

## Usage

### Running the Arduino
1. Upload the `water_quality_monitor.ino` sketch to the Arduino.
2. Ensure all sensors are properly connected and powered.
3. The Arduino will start logging data with timestamps.

## Running the Python Script

1. Ensure the Arduino is connected to the computer via USB or Bluetooth.
2. Run the Python script to read the logged data from the Arduino:
   python read_water_quality.py

3. The script will also fetch current weather data from a weather API. Make sure you have an API key for the weather service and update the script with your API key.
4. The script will generate plots showing the relationship between different parameters and save them to the specified directory.

## Data Analysis

The Python script generates various plots to help analyze the data:

- **Temperature vs. Time**
- **pH vs. Time**
- **Oxygenation vs. Time**
- **Water Clarity vs. Time**
- **Correlation plots** between different parameters

These plots help in understanding the trends and correlations between water quality parameters and external weather conditions.


## Contributing

Contributions are welcome! Please fork this repository and submit a pull request with your improvements. For major changes, please open an issue first to discuss what you would like to change.


This project is licensed under the MIT License. See the LICENSE file for details.
