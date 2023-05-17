# KNOMI

<img src=img/KNOMI/KNOMI_Title.png width="600" />

## **Introduction**

KNOMI is a mini round screen designed specififically for Klipper running 3D printers, offffering users a unique and personalized way to monitor their printer's operation. The screen displays important information through KNOMI UI, such as heated bed temperature, nozzle temperature, leveling status, printing progress, etc. KNOMI is an open-source product, allowing users to customize the user interface and design mounting brackets to fifit their specifific 3D printer.

## **Main Features**

- KNOMI UI-based display for quick and easy monitoring of printer status.
- User-friendly, wireless communication through WiFi.
- Open-source enables effortless customization and adaptation of KNOMI to various 3D printers with provided 3D model files, while also allowing personalized user interfaces to suit preferences.
- Compatibility with Voron StealthBurner using our custom printed part files.
- Wide input voltage range (DC 5V-24V) for convenient power supply.
- Reserved Type-C port for DIY burning, increasing versatility.
- Full-view screen for accurate color representation from any angle.

<font  color="red">**For information about KNOMI structure, please click**</font> :

[KNOMI USER GUIDE.PDF](https://raw.githack.com/z1996xm/BIGTREETECH/main/docs/download/KNOMI USER GUIDE.pdf)

## **Customize UI**

### **Image conversion**

1、We have provided seventeen customizable gifs in knomi.

<img src=img/KNOMI/KNOMI_GIF.png width="600" />

<font  color="red">**For information about KNOMI GIF, please click**</font> :[KNOMI GIF](https://raw.githack.com/z1996xm/BIGTREETECH/main/docs/download/KNOMI_GIF.zip)

2、Change your GIF to the same name and pixel as the GIF you want to replace.

<img src=img/KNOMI/KNOMI_Tip.png width="600" />

3、Open the project and enter lvgl_ Gif.cpp file.

<img src=img/KNOMI/KNOMI_Tip1.png width="600" />

4、Right click on the GIF you want to replace and click on Go To Definition

<img src=img/KNOMI/KNOMI_Tip2.png width="600" />

5、Can see the structure and data type header.cf of GIF

<img src=img/KNOMI/KNOMI_Tip3.png width="600" />

6、Click on the link to enter the GIF conversion tool https://lvgl.io/tools/imageconverter

<img src=img/KNOMI/KNOMI_Tip4.png width="600" />

7、Click on BROWSE and select the new replacement GIF，The Color format selects the same data type as the original GIF

<img src=img/KNOMI/KNOMI_Tip5.png width="600" />

8、The Output format select C array,and click on Convert.

<img src=img/KNOMI/KNOMI_Tip7.png width="600" />

9、Paste the generated file content over the source GIF file content.

10、Click Compile.

<img src=img/KNOMI/KNOMI_Tip8.png width="600" />

11、After the compilation is completed, connect knomi to the computer through TYPE-C, click on download, and once the download is completed, power on knomi again.

<img src=img/KNOMI/KNOMI_Tip9.png width="600" />
