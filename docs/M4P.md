# M4P

<img src=img/M4P_Title.png />

<a href ="https://z1996xm.github.io/BIGTREETECH/"><<img src=img/M4P_Title.png />

## 1. Brief Introduction

### 1.1 Main Features

- DSI1, CSI1 interface (for CM4)

- Gigabit Ethernet interface (1000M for CM4, 100M for CB1)

- 3 USB 2.0 ports

- Equipping the ESD protection chip on the USB and Ethernet ports to prevent being 

  broken down by the static electricity

- When working with Raspberry Pi CM4, its 40pin pin header has the same function 

  as that of Raspberry Pi(Custom IO for CB1)

- Using a BTB board-to-board connection, which can be further reinforced with 

  screws, perfectly compatible with CB1 or Raspberry Pi CM4

- The MCU adopts STM32G0B0RE 32-bit ARM Cortex-M0+ @64MHz chip

- The power chip adopts TPS5450-5A, which supports DC12/24V power input, the 

  output current of the chip is up to 5A, and the peak value can reach 6A, which 

  perfectly supports the power supply of the core board

- The protection circuit of the thermistor part prevents the main control chip from 

  burning due to leakage of the heated bed or heater cartridge

- In CNC fan ports: FAN0, FAN1, and FAN2, a 24V (DCIN) or 5V power supply can 

  be selected with a jumper cap (Note: the voltage of the three CNC fans should be 

  the same, and cannot be set to different voltages individually)

- MCU firmware can be upgraded through SD card, or through DFU with Klipper's 

  make flash command

- On-board TMC-driven SPI and UART working modes, on-board DIAG function 

  pins, can be used by simply plugging and unplugging the jumper cap

- Support filament runout detection, BLTouch, RGB lights...

- Adopt replaceable fuse for easy replacement

### 1.2 Basic Parameters

- Product Size: 160 x 95mm

- Installation Size: 146 x 84.2mm; 97 x 84.2mm

- Core Board Installation Size: 33 x 48mm

- The maximum output current of the heated bed port: 10A

- The maximum output current of the heater cartridge port: 6A

- Fan Port: Three for CNC Fan(24V/5V Voltage Selectable), One SoC Fan(Voltage 

  not Selectable)

- The maximum output current of the fan port:1A

- Total current for heater cartridge + driver + fan: ＜20A

- Extended Interface: BLTouch(Servos, Probe), Fil-DET, 2 * RGB

- Motor Driver: Support TMC5160, TMC2209, TMC2225, TMC2226, TMC2208, 

  TMC2130, ST820, LV8729, DRV8825, A4988...

- Driver Working Mode Support: SPI, UART, STEP/DIR

- Motor Drive Interface: X, Y, Z(Dual Z-axis), E0, a total of four.

- Temperature Sensor Interface: 2-way 100K NTC

- Display Screen: RepRapDiscount EXP-1 + EXP-2

### 1.3 Product Dimension

<img src=img/M4P_Size.png />

## 2. Peripheral Interface

### 2.1 Interface Diagram

<img src=img/M4P_Interface_Diagram.png />

### 2.2 Pin Out

<img src=img/M4P_Pin_Out.png />

## 3. Interface Instruction

### 3.1 Installing the Core Board

M4P+CM4：Pay attention to the direction, as shown below.

<img src=img/M4P+CM4.png />

M4P+CB1：Pay attention to the direction, as shown below.

<img src=img/M4P+CB1.png />

### 3.2 40 pin GPIO

When working with CM4, the pin arrangement of 40 Pin GPIO is exactly the same as that of Raspberry Pi. When working with CB1, it is a custom IO arrangement, as shown in the figure below, the 'GPIO4' in front of '_' is the IO of CM4, and the latter 'PC7' is the IO of CB1.

<img src=img/M4P_40_Pin.png />

### 3.3 TYPE-C

After the M4P is powered on, the red LED1 on the lower right side of the motherboard will light up, indicating that the power supply is normal. The J8 on the middle of the board is the power selection terminal, it needs to be short circuited only when the type-C USB is used to supply power to the motherboard or the USB is used to supply power externally. The signal of type-C is connected to the SoC, Only used when writing OS image for CM4 eMMC version.

<img src=img/M4P_TYPE_C.png />

### 3.4 Stepper Driver

#### 3.4.1 Normal STEP/DIR(STANDALONE) Mode

For example, A4988, DRV8825, LV8729, ST820...use the jumper cap to short MS0-MS2 according to the driver subdivision table.

<img src=img/M4P_Stepper_Driver.png />

**Note: If using A4988or DRV8825, RST and SLP must be shorted with jumper caps for normal operation.**

| Driver chips                  | MS1                           | MS2  | MS3  | Microsteps | Excitation Mode |
| ----------------------------- | ----------------------------- | ---- | ---- | ---------- | --------------- |
| A498816 microstep max 35V 2A  | L                             | L    | L    | Full Step  | 2 Phase         |
|                               | H                             | L    | L    | 1/2        | 1-2 Phase       |
|                               | L                             | H    | L    | 1/4        | W1-2 Phase      |
|                               | H                             | H    | L    | 1/8        | 2W1-2 Phase     |
|                               | H                             | H    | H    | 1/16       | 4W1-2 Phase     |
| <img src=img/M4P_Data2.png /> | <img src=img/M4P_Data1.png /> |      |      |            |                 |

 

| Driver chips                                          | MODE2                         | MODE1 | MODE0 | Microsteps | Excitation Mode |
| ----------------------------------------------------- | ----------------------------- | ----- | ----- | ---------- | --------------- |
| DRV8825Maximum 32microsteps8.2V-45V 2.5A at 24V T=25℃ | L                             | L     | L     | Full Step  | 2 Phase         |
|                                                       | L                             | L     | H     | 1/2        | 1-2 Phase       |
|                                                       | L                             | H     | L     | 1/4        | W1-2 Phase      |
|                                                       | L                             | H     | H     | 1/8        |                 |
|                                                       | H                             | L     | L     | 1/16       |                 |
|                                                       | H                             | L     | H     | 1/32       |                 |
|                                                       | H                             | H     | L     | 1/32       |                 |
|                                                       | H                             | H     | H     | 1/32       |                 |
| <img src=img/M4P_Data3.png />                         | <img src=img/M4P_Data4.png /> |       |       |            |                 |

 

| Driver chips                        | MD3                           | MD2  | MD1  | Microsteps | Excitation Mode |
| ----------------------------------- | ----------------------------- | ---- | ---- | ---------- | --------------- |
| LV8729Maximum 128microsteps36V 1.8A | L                             | L    | L    | Full Step  | 2 Phase         |
|                                     | L                             | L    | H    | 1/2        | 1-2 Phase       |
|                                     | L                             | H    | L    | 1/4        | W1-2 Phase      |
|                                     | L                             | H    | H    | 1/8        | 2W1-2 Phase     |
|                                     | H                             | L    | L    | 1/16       | 4W1-2 Phase     |
|                                     | H                             | L    | H    | 1/32       | 8W1-2 Phase     |
|                                     | H                             | H    | L    | 1/64       | 16W1-2 Phase    |
|                                     | H                             | H    | H    | 1/128      | 32W1-2 Phase    |
| <img src=img/M4P_Data5.png />       | <img src=img/M4P_Data6.png /> |      |      |            |                 |

 

| Driver chips                       | MS3                           | MS2  | MS1  | Microsteps |
| ---------------------------------- | ----------------------------- | ---- | ---- | ---------- |
| ST820Maximum 256microsteps45V 1.5A | L                             | L    | L    | Full Step  |
|                                    | L                             | L    | H    | 1/2        |
|                                    | L                             | H    | L    | 1/4        |
|                                    | L                             | H    | H    | 1/8        |
|                                    | H                             | L    | L    | 1/16       |
|                                    | H                             | L    | H    | 1/32       |
|                                    | H                             | H    | L    | 1/128      |
|                                    | H                             | H    | H    | 1/256      |
| <img src=img/M4P_Data7.png />      | <img src=img/M4P_Data8.png /> |      |      |            |

#### 3.4.2 UART Mode of TMC Driver

For example, TMC2208, TMC2209, TMC2225... Use a jumper cap for each to connect the position of the red box in the figure, and the subdivision and driver current is set by firmware.

<img src=img/M4P_TMC_UART_Mode.png />

#### 3.4.3 SPI Mode of TMC Driver 

For example, TMC2130, TMC5160, TMC5161... Use 4 jumper caps for each to connect the position of the red box in the figure, and the subdivision and driver current is set by firmware.

<img src=img/M4P_TMC_SPI_Mode.png />

#### 3.4.4 DIAG(Sensorless Homing) of TMC Driver 

As shown in the figure, plug the jumper cap when using the Sensorless Homing function, and leave it unplugged when it is not used. There is no need to cut the DIAG pin of the driver.

<img src=img/M4P_TMC_DIAG_Mode.png />

#### 3.4.5 Stepper Driver Voltage Selection

The power supply of each driver can be set by the jumper. When the jumper is inserted into the left side, the independent MOTOR POWER port is used for driver power, and the supported voltage up to 56V. When the jumper is inserted into the right side, the main POWER port is used for driver power, and the 12/24v voltage is supported.

##### Driver independent power supply

The jumper is inserted into the left side and powered by the MOTOR POWER port. the supported voltage up to 56V.

<img src=img/M4P_IPS.png />

##### Main power supply

The jumper is inserted into the right side and powered by the main POWER port. the 12/24v voltage is supported.

<img src=img/M4P_MPS.png />

### 3.5 BLTouch Wiring

M4P_BLTouch_Wiring

<img src=img/M4P_BLTouch_Wiring.png />

### 3.6 EXP1+EXP2 and LCD Screen Wiring

M4P_E1_E2_LCD

<img src=img/M4P_E1_E2_LCD.png />

### 3.7 RGB Wiring

<img src=img/M4P_RGB_Wiring.png />

### 3.8 DSI/CSI Wiring

<img src=img/M4P_DSI_CSI_Wiring.png />

### 3.9 SPI Display Wiring

<img src=img/M4P_SPI_Display_Wiring.png />

### 3.10 ADXL345 Accelerometer

Refer to here: https://www.klipper3d.org/Measuring_Resonances.html, We can refer to the following wiring and configuration when connecting to the M4P motherboard

<img src=img/M4P_ADXL345.png />

[adxl345]

    ```
    cs_pin: PD9
    spi_bus: spi1
    #spi_software_sclk_pin: PA5
    #spi_software_mosi_pin: PA7
    #spi_software_miso_pin: PA6
    ```

## 4. OS Download

For details, please click: https://z1996xm.github.io/BIGTREETECH/Tutorials.html
