# Irradiance and Theoretical Power Calculation Board for Photovoltaic Systems

This board is designed to measure irradiance using a small solar panel and to estimate the theoretical power output of a photovoltaic installation using an NTC temperature sensor placed on one of the panels.

The system is intended for photovoltaic setups that **cannot inject electricity into the grid** — whether on-grid or off-grid. It helps determine real-time production capacity and supports better energy management and self-consumption.

## Features

- **Irradiance Measurement**  
  A miniature solar panel captures real-time irradiance levels.

- **Theoretical Power Estimation**  
  An NTC sensor measures panel temperature to calculate expected power output under current conditions.

- **No-Grid-Injection Systems**  
  Ideal for photovoltaic installations restricted from injecting power into the grid.

- **Performance Monitoring**  
  Provides data to evaluate the system's efficiency and optimize energy usage.
  
  On the first graphe below, you can see the values of the ESP-PowerSunSensor are shown in blue, and my solar production values in yellow :
  
  <img width="1716" height="813" alt="Capture d'écran 2025-10-09 132655" src="https://github.com/user-attachments/assets/5e358a79-ca5a-40b6-877e-ab8b44c8d71d" />


  Below is the list of the different data reported by the sensor : 
  
  <img width="395" height="329" alt="Capture d'écran 2025-10-15 134230" src="https://github.com/user-attachments/assets/6160d3f0-0a1f-484a-a99e-df59a6f3d2d6" />


## Use Cases

- Estimating maximum potential production of a solar installation  
- Monitoring performance over time  
- Supporting system design or troubleshooting  
- Managing loads in self-consumption scenarios

## Required Components

- Miniature solar panel (I personally used the glass solar panel from a solar garden lamp recovered from the recycling center)  
- NTC temperature sensor (attach to one of the main panels) : Any NTC sensor can be used, as long as you adapt the pull-up resistor (R16 on the PCB) value and know the sensor’s B25/50 characteristics, which should be entered into the YAML configuration.
- An ESP-PowerSunSensor PCB wired according to the associated schematic diagram
- Power supply and data interface (USB, Wi-Fi, etc.)

Beta version : 

<img width="192" height="144" alt="image" src="https://github.com/user-attachments/assets/9f07aa3a-3c1f-4fc0-a733-3ddd7c1e7d14" />

## 💰 How Much Does It Cost?

This project is designed to be **as low-cost as possible**, using affordable or recycled components.

| Component                        | Estimated Price (€) | Notes                                                                 |
|----------------------------------|----------------------|-----------------------------------------------------------------------|
| Miniature solar panel            | 0 – 5 €              | Recovered from a solar garden lamp (recycling center, old devices)   |
| NTC temperature sensor           | 1 – 3 €              | Any NTC sensor works 10kR to 100kR (adapt pull-up resistor and B-value in YAML)    |
| ESP32-C3-WROOM-02                | 3 – 8 €              |                                                                      |
| ESP-PowerSunSensor PCB           | 2 – 5 €              | Depending on quantity and supplier (JLCPCB, PCBWay, etc.)            |
| Resistors, connectors, etc.      | 1 – 2 €              | Very cheap, or reusable from old electronics                         |
| 5V USB power supply              | 2 – 5 €              | Standard USB charger or reused power source                          |

### 💡 Total Estimated Cost: **around 10 to 25 €**

> 💬 **Tip**: If you recycle parts (panel, power supply, cables), the full setup can cost **less than 10 €**!

## Installation

1. Connect J2 by strapping it to enable bootloader mode on the ESP32
2. Attach the electronic board to your computer using an USB cable.
3. Disconnect J2 (unstrap it) after enabling bootloader mode
4. Go to your ESP-home server and flash the new device with attached yaml customized for your settings
5. After that, you can remove the USB cable
6. Connect the miniature solar panel to the input for irradiance measurement (J3).
7. Attach the NTC sensor firmly to the back side of one of your main solar panels and connect it on J1 connector.
<img width="192" height="144" alt="image" src="https://github.com/user-attachments/assets/51e51614-b569-45c9-adf0-24bf7e64da0c" />

8. Mount the sensor in same direction of your installation you want to monitor, example (files attached in repo) :
<img width="192" height="144" alt="image" src="https://github.com/user-attachments/assets/d52ec0b3-3490-4675-9c07-b48d1d293f4d" />
<img width="192" height="144" alt="image" src="https://github.com/user-attachments/assets/af118ae3-e01c-4ce5-b522-d1985430df33" />
<img width="192" height="144" alt="image" src="https://github.com/user-attachments/assets/7f69529d-6c65-4c58-8b05-f3f8aba6fd13" />
<img width="192" height="144" alt="image" src="https://github.com/user-attachments/assets/8f56dc22-a288-4c68-a5e0-0fa2f586b9c1" />


9. You can separate the solar panel and NTC sensor from the electronics PCB. In my case, they are positioned 15 meters apart, and the system works fine. This tip allows for a better Wi-Fi connection by placing the electronics closer to my Wi-Fi access point.
10. Connect the USB cable to the power supply.
11. Enjoy your setup and power monitoring!

## Author

- @M3c4tr0x

## License

[MIT License]
