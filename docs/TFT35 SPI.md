# TFT 35 SPI

## **Introduction**

BIGTREETECH TFT35 SPI V2.1 is a medium-size and clear 3D printer display developed by the 3D printing team of Shenzhen Big Tree Technology Co., Ltd.

## **Main Features**

- SPI is used for LCD display, and I2C is used for touch. The touch screen is controlled by the chip on the motherboard, which significantly reduces its cost. 
- It is connected to the motherboard through the FPC cable, simple and convenient.
- Designed with XH2.54 terminal, which can communicate with the board through the terminal.

## **Basic Parameters**

- Product Dimensions: 98 x 56mm 
- Mounting Dimensions: 98 x 56mm, you can read more details here: **BIGTREETECH TFT35 SPI V2.1_SIZE**
- Input Voltage: DC 5V
- Logic Voltage: DC 3.3V 
- Screen Size: 3.5-inch
- Resolution: 480x320
- Driver IC for SPI Display: ILI9488
- Driver IC for Touch: NS2009

## **Dimensions**

<img src=img/TFT35_SPI/TFT35_SPI_Dimension.png width="600" />

## **Interface Diagram**

<img src=img/TFT35_SPI/TFT35_SPI_Interface.png width="600" />

## **Pin Out**

<img src=img/TFT35_SPI/TFT35_SPI_Pinout.png width="600" />

## **Software Installation**

Currently, it only supports CB1. V2.2.0 and earlier OS do not support TFT35 SPI. Please use V2.2.1 and later OS.

CB1 OS Image: https://github.com/bigtreetech/CB1/releases

<img src=img/TFT35_SPI/TFT35_SPI_Soft1.png width="600" />

After the OS writes to the SD card, there is a FAT32 partition named BOOT, open "BoardEnv.txt" file with Notpad, Notpad++ or VSCode.

<img src=img/TFT35_SPI/TFT35_SPI_Soft2.png width="600" />

Uncomment overlays=tft35_spi to enable TFT35 SPI screen (Delete '#' at the beginning of the line).

<font  color="red">***NOTE: If the OS image of v2.2.1 version is used. Set to overlays=tft35_spi25 instead of overlays=tft35_spi Use the SPI speed of 25Mhz instead of the default 50Mhz to avoid display confusion. If the OS image after V2.2.1 is used, The OS will use a lower and more stable speed by default.***</font>

<img src=img/TFT35_SPI/TFT35_SPI_Soft3.png width="600" />
