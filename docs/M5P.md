# M5P

[<img src=img/M5P/M5P_Title.png />](https://z1996xm.github.io/BIGTREETECH/M5P.html)

## · Introduction

​		BIGTREETECH MANTA M5P is a 32-bit motherboard developed by the 3D printing team of Shenzhen Big Tree 

Technology Co., Ltd. for Klipper running. It can run Klipper with a core board, which greatly eliminates the mass 

wiring between the motherboard and Raspberry Pi, and also greatly saves space in the chassis. The BTB headers 

are designed on MANTA M5P, so that customers can choose to use CM4 or other solutions, thus solving the insane 

shortage of Raspberry Pi CM4.

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

<img src=img/M5P/M5P_Dimension1.png />

![](img/M5P/M5P_Dimension2.png /)

## · CAD

![](img/M5P/M5P_Diagram.png /)

## · Schematic



## · Pin Out

![](img/M5P/M5P_Pinout.png /)

## **· Hardware Configuration**

**USB Power Supply**

After the BIGTREETECH MANTA M5P has been powered, the red light D22 on the left side of the MCU will light up, indicating power on. When using only the USB to power the board or provide power through the USB, please insert the jumper cap onto the VUSB.

![](img/M5P/M5P_USB_PS.png /)

## · Hardware Installation

### · Stepper Driver

#### · STEP/DIR (STANDALONE) Mode

e.g.: A4988, DRV8825, LV8729, ST820, etc., connect jumpers(MS0-MS2) according to the microstep chart.

![](img/M5P/M5P_STEP_Mode.png /)

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
    <td><img src=img/M5P/M5P_DRI1.png /></td>
    <td colspan="5"><img src=img/M5P/M5P_DRI2.png /></td>
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
    <td><img src=img/M5P/M5P_DRI3.png /></td>
    <td colspan="5"><img src=img/M5P/M5P_DRI4.png /></td>  
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
    <td><img src=img/M5P/M5P_DRI5.png /></td>
    <td colspan="5"><img src=img/M5P/M5P_DRI6.png /></td>  
</table>



#### · UART Mode of TMC Driver

