# M8P

[<img src=img/M8P/M8P_Title.png width="600" />](https://z1996xm.github.io/BIGTREETECH/M8P.html)

## **· Introduction**

<p>BIGTREETECH MANTA M8P is a 32-bit printer motherboard developed by the 3D printing team of <br> Shenzhen Big Tree Technology Co., Ltd. for Klipper firmware. You can simply plug in the core<br> board to run the Klipper firmware, which greatly simplifies the connection between the motherboard and <br>the Raspberry Pi, and saves a lot of space. Moreover, the BTB connector is designed to install CM4 or<br> other solutions to solve the current expensive problem of CM4.<br></p>

## **· Announcements**



## **· Main Features**

- Adopt 32-bit 64MHz ARM Cortex-M0+ series STM32G0B1VET6 as the main control chip;
- The power chip, TPS5450-5A, supports DC12/24V power input. The output current of the chip is up to 5A, and the peak value can reach 6A, which perfectly supports the power supply of Raspberry Pi; 
- There is a BOOT button reserved on the motherboard, users can update the bootloader through DFU;
- The thermistor part includes a protection circuit that protects the main control chip from the possibility of burning caused by leakage of the heated bed or heater cartridge;
- 24V, 12V, and 5V voltages are available for CNC fans, eliminating the need for an external transformer module, thereby reducing the chance of damage to the motherboard due to improper operation;
- The thermistor can select the pull-up resistor value through the jumper, in this way, it supports PT1000 without an external module, which is convenient for customers to DIY;
- The MCU firmware can be updated via an SD card, or through Klipper's make flash command using DFU;
- The motherboard and the core board use the BTB connection to allow using other solutions other than CM4;
- On-board TMC-driver SPI and UART working modes, on-board DIAG function pins, can be used by simply plugging and unplugging the jumper cap;
- Support filament runout detection, auto shutdown, BLTouch, RGB lights...
- High efficiency MOSFET for less heat generation;
- Adopt replaceable fuse for easy replacement;
- Three-way four-wire fan interface is reserved, and can be used to connect the water cooling device;
- The proximity switch interface is reserved, supports NPN and PNP types, (24V, 12V, 5V) voltage selection is available, common voltage selection with VFAN6;
- Provide the SPI expansion interface to allow Klipper firmware users to connect an external acceleration sensor for acceleration compensation.

## **· Basic Parameters**

- Product Size: 170 x 102.7mm, you can read more details here **BIGTREETECH MANTA M8P V1.0-SIZE-top.pdf**
- Installation Size: Please read: **BIGTREETECH MANTA M8P V1.0-SIZE-top.pdf**
- Microprocessor: ARM Cortex-M0+ STM32G0B1VET6 64MHz
- Drive Input Voltage: VIN（12V/24V） Or HV(≤56V) 
- Motherboard Input Voltage: VIN=DC12V or DC24V
- Heated Bed Input Voltage: BED IN=DC12V or DC24V
- Logic Voltage: DC3.3V
- Heating Port: Heated Bed(HB), Heater Cartridge(HE0, HE1, HE2, HE3)
- The maximum output current of the heated bed port: 10A, Peak Value: 12A
- The maximum output current of the heater cartridge port: 5.5A, Peak Value: 6A
- Fan Port: Two-wire CNC Fan (FAN0, FAN1, FAN2, FAN3), four-wire CNC Fan fan (FAN4, FAN5, FAN6), Always-on Fan (24V FAN x 2), among which the CNC Fan voltages are 5V, 12V, 24V optional
- The maximum output current of the fan port: 1A, Peak Value: 1.5A
- Total current for heater cartridge + driver + fan: ＜12A
- Extended Interface: BLTouch(Servos, Probe), PS-ON, Fil-DET, RGBx2, SPI
- Motor Driver: Support TMC5160, TMC2209, TMC2225, TMC2226, TMC2208, TMC2130, ST820, LV8729, DRV8825, A4988...
- Driver Working Mode Support: SPI, UART, STEP/DIR
- Motor Drive Interface: Motor1, Motor2, Motor3(dual motor interface), Motor4, Motor5, Motor6, Motor7, Motor8, a total of Eight
- Temperature Sensor Interface: 5-way 100K NTC, of which 4-way 100K NTC and PT1000 are optional
- Support Screen: SPI Touch Screen, LCD Screen
- PC Communication Interface: Type-C
- Functional Interface: USB 2.0 x 3, LAN, DSI, CSI, SPI, 40Pin-GPIO, HDMI0 and HDMI1, SOC-Card, MCU-Card
- Support Machine Structure: Cartesian, Delta, Kossel, Ultimaker, CoreXY
- Recommended Software: Cura, Simplify3D, Pronterface, Repetier-host, Makerware

## **· Dimensions**

<img src=img/M8P/M8P_Dimensions1.png width="600" />

<img src=img/M8P/M8P_Dimensions2.png width="600" />

## **· Pin Out**

<img src=img/M8P/M8P_Pin_Out.png width="600" />

**Differences between V1.0 and V1.1**

Changes in V1.1 include：M6，M7，M8，SPI，MCU-Card，RGB1&RGB2，FAN4，CAN，Pi-FAN

<img src=img/M8P/M8P_Pin_Out1.png width="600" />

## **· CAD**

<img src=img/M8P/M8P_CAD.png width="600" />

**V1.1 added functions**

CAN interface（2Pin*2 XH2.54），USB port function selection（UART to USB，USB OTG），Pi-FAN（Controlled by GPIO26），FAN4 becomes a 2-wire CNC fan.

<img src=img/M8P/M8P_Add_Func1.png width="600" />

The 5V and 12V power output ports are added with E-FUSE protection, which has short reaction time, strong protection and realizes over-current protection, short circuit protection and spark protection.

**M8P V1.1+CB1：**

<img src=img/M8P/M8P_Add_Func2.png width="600" />

**M8P V1.1-Bot：**

<img src=img/M8P/M8P_Add_Func3.png width="600" />

## **· Schematic**

