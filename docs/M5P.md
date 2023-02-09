# M5P

[<img src=img/M5P/M5P_Title.png width="800" />](https://z1996xm.github.io/BIGTREETECH/M5P.html)

## · Introduction

​		BIGTREETECH MANTA M5P is a 32-bit motherboard developed by the 3D printing team of Shenzhen Big Tree Technology Co., Ltd. for Klipper running. It can run Klipper with a core board, which greatly eliminates the mass wiring between the motherboard and Raspberry Pi, and also greatly saves space in the chassis. The BTB headers are designed on MANTA M5P, so that customers can choose to use CM4 or other solutions, thus solving the insane shortage of Raspberry Pi CM4.

## · Announcements



## · Main Features

1. 32bit 64MHz ARM Cortex-M0+ series STM32G0B1RET6 MCU.

2. The thermistor circuit is protected to prevent MCU damage from shorted heated bed and heater cartridge connections. 

3. The CNC fan's voltage is selectable in 24V, 12V, and 5V, no more need for external stepdown thus preventing board damage from user error.

4. Thermistor connection supports pull-up resistance value setting using jumpers, no more extra module needed for PT1000.

5. MCU firmware can be upgraded via an SD card, or use DFU via Klipper's make flash command.

6. BTB connectors are adopted between the motherboard and core board, allowing the choice of other core board solutions in addition to CM4.

7. Integrated SPI and UART mode of TMC driver and DIAG pin, easily configurable with jumpers.

8. Support filament runout sensor, BLTouch, RGB, etc.

9. Replaceable fuse for easy maintenance.

10. Onboard proximity switch port, support NPN and PNP type selection, (24V, 12V, 5V) voltage selection.

11. Onboard SPI interface for connecting acceleration sensor to enable Klipper's input shaping.

12. The new E-FUSE fuse is equipped, which can respond quickly, enhance self-protection ability, and greatly reduce the motherboard burnout caused by short circuits or ignition.

## · Basic Parameters

| Dimensions                    | 137.5mm x 95mm, for details please refer to BIGTREETECH MANTA M5P V1.0-SIZE-top.pdf |
| ----------------------------- | ------------------------------------------------------------ |
| Mounting Size                 | Please refer to BIGTREETECH MANTA M5P V1.0-SIZE-top.pdf      |
| MCU                           | ARM Cortex-M0+ STM32G0B1RET6 64MHz                           |
| Driver Input Voltage          | VIN (DC12V-24V), HV (DC24V-56V) Selectable                   |
| Motherboard Input Voltage     | VIN=DC12V or DC24V                                           |
| Logic Voltage                 | DC 3.3V                                                      |
| Heater Connection             | Heated Bed (HB), Heater Cartridge (HE0, HE1)                 |
| HB Port Max Current           | 10A Continuous, 11A Instantaneous                            |
| Heater Cartridge Max Current  | 5.5A Continuous, 6A Instantaneous                            |
| Fan Port                      | 3 x 2 pins CNC (FAN0, FAN1, Pi-FAN) (5/12/24V Selectable Voltage), 1 x Always On (FAN) |
| Fan Port Max Current          | 1A Continuous, 1.1A Instantaneous                            |
| Overall Current of Fan Ports) | ＜2.5A                                                       |
| Expansion Port                | CAN, Probe, RGBx2, SPI, EXP1+EXP2, MIN1-MIN4, 40Pin-GPIO     |
| Motor Driver                  | Support TMC5160, TMC2209, TMC2225, TMC2226, TMC2208, TMC2130, ST820, LV8729, DRV8825, A4988... |
| Driver Mode                   | SPI, UART, STEP/DIR                                          |
| Motor Driver Port             | Motor1, Motor2, Motor3 (Dual Motors Port), Motor4, Motor5   5 Channels in Total |
| Thermistor                    | 3 x 100K NTC, two of which are selectable for NTC and PT1000 |
| Display                       | SPI Touchscreen, LCD Display, HDMI Touchscreen, DSI Touchscreen |
| PC Connection                 | Type-C                                                       |
| Interface                     | USB 2.0x2, LAN, DSI, CSI, SPI, HDMI0, HDMI1, SOC-Card, MCU-Card |
| Supported Kinematics          | Cartesian, Delta, Kossel, Ultimaker, CoreXY                  |
| Recommended Slicer/Console    | Cura, Simplify3D, Pronterface, Repetier-host, Makerware      |

## · Dimensions

<img src=img/M5P/M5P_Dimension1.png width="800" />

<img src=img/M5P/M5P_Dimension2.png width="800" />

## · CAD

<img src=img/M5P/M5P_Diagram.png width="800" />

## · Schematic



## · Pin Out

<img src=img/M5P/M5P_Pinout.png width="800" />

## **· Hardware Configuration**

**USB Power Supply**

After the BIGTREETECH MANTA M5P has been powered, the red light D22 on the left side of the MCU will light up, indicating power on. When using only the USB to power the board or provide power through the USB, please insert the jumper cap onto the VUSB.

<img src=img/M5P/M5P_USB_PS.png width="800" />

## · Hardware Installation

### · Stepper Driver

#### · STEP/DIR (STANDALONE) Mode

e.g.: A4988, DRV8825, LV8729, ST820, etc., connect jumpers(MS0-MS2) according to the microstep chart.

<img src=img/M5P/M5P_STEP_Mode.png width="800" />

​					Note: RST and SLP must be shorted by jumpers for A4988 or DRV8825. 

<table>
	<tr>
    <td>Driver Chips</td><td>MODE2</td><td>MODE1</td><td>MODE0</td><td>Microsteps</td><td>Excitation Mode</td></tr>
    <tr>
    <td rowspan="8">DRV8825 Maximum 32 microsteps<br /> 
        8.2V-45V 2.5A at 24V T=25℃</td>
    <td>L</td><td>L</td><td>L</td><td>Full Step</td><td>2 Phase</td>
    <tr>
    <td>L</td><td>L</td><td>H</td><td>1/2</td><td>1-2 Phase</td>
    <tr>
    <td>L</td><td>H</td><td>L</td><td>1/4</td><td>W1-2 Phase</td>
    <tr>
    <td>L</td><td>H</td><td>H</td><td>1/8</td><td></td></tr>
    <tr>
    <td>H</td><td>L</td><td>L</td><td>1/16</td><td></td></tr>
    <tr>
    <td>H</td><td>L</td><td>H</td><td>1/32</td><td></td></tr>
    <tr>
    <td>H</td><td>H</td><td>L</td><td>1/32</td><td></td></tr>
    <tr>
    <td>H</td><td>H</td><td>H</td><td>1/32</td><td></td></tr>
    <tr>
    <td><img src=img/M5P/M5P_DRI1.png width="130" /></td>
    <td colspan="5"><img src=img/M5P/M5P_DRI2.png width="200" /></td>
    <tr>    
</table>
<table>
	<tr>
    <td>Driver Chips</td><td>MS1</td><td>MS2</td><td>MS3</td><td>Microsteps</td><td>Excitation Mode</td></tr>
    <tr>
    <td rowspan="5">A4988 16 microstep max 35V 2A</td>
    <td>L</td><td>L</td><td>L</td><td>Full Step</td><td>2 Phase</td>
    <tr>
    <td>H</td><td>L</td><td>L</td><td>1/2</td><td>1-2 Phase</td>
    <tr>
    <td>L</td><td>H</td><td>L</td><td>1/4</td><td>W1-2 Phase</td>
    <tr>
    <td>H</td><td>H</td><td>L</td><td>1/8</td><td>2W1-2 Phase</td>
    <tr>
    <td>H</td><td>H</td><td>H</td><td>1/16</td><td>4W1-2 Phase</td>
    <tr>
    <td><img src=img/M5P/M5P_DRI3.png width="110" /></td>
    <td colspan="5"><img src=img/M5P/M5P_DRI4.png width="200" /></td>  
    <tr>    
</table>
<table>
	<tr>
    <td>Driver Chips</td><td>MD3</td><td>MD2</td><td>MD1</td><td>Microsteps</td><td>Excitation Mode</td></td>
    <tr>
    <td rowspan="8">LV8729 Maximum 128 microsteps<br /> 36V 1.8A</td> 
    <td>L</td><td>L</td><td>L</td><td>Full Step</td><td>2 Phase</td>
    <tr>
    <td>L</td><td>L</td><td>H</td><td>1/2</td><td>1-2 Phase</td>
    <tr>
    <td>L</td><td>H</td><td>L</td><td>1/4</td><td>W1-2 Phase</td>
    <tr>
    <td>L</td><td>H</td><td>H</td><td>1/8</td><td>2W1-2 Phase</td></tr>
    <tr>
    <td>H</td><td>L</td><td>L</td><td>1/16</td><td>4W1-2 Phase</td></tr>
    <tr>
    <td>H</td><td>L</td><td>H</td><td>1/32</td><td>8W1-2 Phase</td></tr>
    <tr>
    <td>H</td><td>H</td><td>L</td><td>1/64</td><td>16W1-2 Phase</td></tr>
    <tr>
    <td>H</td><td>H</td><td>H</td><td>1/128</td><td>32W1-2 Phase</td></tr>
    <tr>
    <td><img src=img/M5P/M5P_DRI5.png width="100" /></td>
    <td colspan="5"><img src=img/M5P/M5P_DRI6.png width="200" /></td>  
</table>





#### · UART Mode of TMC Driver

e.g.: TMC2208, TMC2209, TMC2225, etc., place jumpers according to the diagram below, microstep and current can be configured in firmware.

<img src=img/M5P/M5P_UART_Mode.png width="800" />

#### · TMC Driver SPI Mode

e.g.: TMC2130, TMC5160, TMC5161, etc., place jumpers according to the diagram below, microstep and current can be configured in firmware.

<img src=img/M5P/M5P_SPI_Mode.png width="800" />

#### · TMC Driver DIAG (Sensorless Homing)

When using sensorless homing, place jumpers according to the diagram below, there is no need to cut the DIAG pin off when not being used.

<img src=img/M5P/M5P_DRI_Diag.png width="800" />

#### · Driver Voltage Selection 

<img src=img/M5P/M5P_DRI_Vol1.png width="800" />

<img src=img/M5P/M5P_DRI_Vol2.png width="800" />

### · Install the Core Board via BTB Connection

M5P+CM4: Note the direction, as shown in the figure below:

<img src=img/M5P/M5P_CM4.png width="800" />

M5P+CB1: Note the direction, as shown in the figure below:

<img src=img/M5P/M5P_CB1.png width="800" />

### · Voltage Selection for CNC Fan

Through the jumper cap, you can set the output voltage to 5V, 12V, or 24V.
Note: We are not responsible for fan burnout caused by incorrect voltage selection. Please confirm the voltage the fan supports before selecting the voltage.

<img src=img/M5P/M5P_Vol_CNC.png width="800" />

### · 100K NTC or PT1000 Setting

When using 100K NTC, no jumpers need to be connected, the pull up resistance of TH0-TH3 is 4.7K 0.1%. When using PT1000, the pins indicated in the picture below need to be connected via jumpers, parallel connection of 4.12K 0.1% resistors, the pull-up resistance of TH0-TH1 is 2.2K. (This method has a much lower accuracy than the MAX31865 in reading temperature.)

<img src=img/M5P/M5P_100K.png width="800" />

### · BLTouch Wiring

<img src=img/M5P/M5P_BLTouch_Wiring.png width="800" />

### · Wiring between LCD Screen and EXP1+EXP2

<img src=img/M5P/M5P_LCD_E1_E2.png width="800" />

### · RGB Wiring

<img src=img/M5P/M5P_RGB_Wiring.png width="800" />

### · Filament Sensor Wiring

<img src=img/M5P/M5P_Filament.png width="800" />

### · 40 Pins GPIO

<img src=img/M5P/M5P_40_Pins.png width="800" />

### · DSI/CSI Wiring

<img src=img/M5P/M5P_DSI.png width="800" />

### · Proximity Switch Wiring

As shown in the figure below, 24V as an example, normally open (NPN type), no need for shorting through a jumper cap:

<img src=img/M5P/M5P_Proximity.png width="800" />

As shown in the figure below, 24V as an example, normally closed (PNP type), need for shorting through a jumper cap.

<img src=img/M5P/M5P_Proximity1.png width="800" />

## · Software Configuration

For details, please click: https://z1996xm.github.io/BIGTREETECH/Software%20Configuration.html

## · Software Installation

For details, please click: https://z1996xm.github.io/BIGTREETECH/Software%20Installation.html

## · FAQs

1. All unplugging and plugging operations should be performed under the condition of 
   power off, including enabling the eMMC writing.
2. Pay attention to the heat dissipation of CM4 and CB1. If the running application 
   consumes too many system resources, the CM4/CB1 will get hot quite seriously.

## · Product Purchase Link
