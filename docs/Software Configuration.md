# Tutorials

## 1. Raspberry PI CM4 Setup steps

### 1.1 Download OS Image

If CM4 core board is used, You can directly download the images of Fluidd or 
Mainsail, also can download the OS image from the official website of Raspberry Pi 
Fluidd: https://github.com/fluidd-core/FluiddPI/releases
Mainsail: https://github.com/mainsail-crew/MainsailOS/releases
Raspberry Pi official OS: https://www.raspberrypi.com/software/operating-systems
(CM4 needs to refer to the following system settings to enable the system's USB, DSI 
and other interfaces, whose operation is slightly different from the standard Raspberry 
Pi 3B, 4B, etc.)

Raspberry_Pi_OS

<img src=img/Raspberry_Pi_OS.png />

### 1.2 Download and Install Raspberry Pi Imager

Install the official Raspberry Pi Imager: https://www.raspberrypi.com/software/

### 1.3 Write OS

#### 1.3.1 CM4 LITE Version (Micro SD Card)

1. Plug the Micro SD card into the computer via a card reader

2. Select Operating System

<img src=img/Rasp1.png />

3. Select "Use Custom", then select a custom.img from your computer

<img src=img/Rasp2.png />



4. Click the setting icon in the lower right corner

<img src=img/Rasp3.png />

5. “Enable SSH”and click“SAVE”， There are other features that can be set in this menu. 

  Please modify them according to your own needs. Details are as follows：
  Set hostname: raspberrypi.local //Custom hostname Default:raspberrypi.local
  Enable SSH
  Set username and password // Custom username and password，Default 
  username: pi password：raspberry
  Configure wireless LAN // Custom the SSID and password of WLAN

<img src=img/Rasp4.png />

6. Select the Micro SD card and click "WRITE" (Writing the image will format the Micro SD card.

   Be careful not to select the wrong storage device, otherwise, the data will be formatted).

<img src=img/Rasp5.png />

7. Wait for the writing to finish.

<img src=img/Rasp6.png />

#### 1.3.2 CM4 eMMC Version

**(Note: eMMC version will not tun the system from the Micro SD card.)**

1. Install rpiboot For Windows:http://github.com/raspberrypi/usbboot/raw/master/win32/rpiboot_setup.exe

​	For Mac and Linux:https://github.com/raspberrypi/usbboot#building

2. Push the DIP switch 4 (USB OTG) and 3 (BOOT) to ON to enter BOOT mode.

<img src=img/M4P_USB.png />

3. Plug the Type-C into the USB port of the computer(in order to avoid problems caused by the insufficient USB 

  power supply of the computer, it is best to use an external 24V power supply to power the motherboard). Run 
  sudo ./rpiboot(Mac/Linux) or rpiboot.exe on Windows, then the eMMC of CM4 will be recognized as a mass 

  storage device by the computer (if rpiboot reports an error at this time, you can try to re-plug the USB).

4. The step of using the Raspberry Pi Imager to write the OS image is exactly the same as the LITE version. 

  Note: the SSH function should also be enabled.

5. When the writing is completed, push the DIP switch 4 (USB OTG) and 3 (BOOT) back to OFF after power off, 

  and power on again to enter the normal working mode.

### 1.4. System Settings (CM4)

#### 1.4.1 USB 2.0 Hub Ports

M4P is designed with a USB 2.0 Hub, in order to save power consumption, the USB port of CM4 is disabled by default. 

If you want to enable it, you need to add the following content to the config.txt file:

```
dtoverlay=dwc2,dr_mode=host
```

#### 1.4.2 DSI1 Display Interface

The default display interface is HDMI. The onboard DSI port of M4P uses the DSI1 
interface. You need to download the DSI1 driver and enter the following sentence in 
the command line:

```
sudo wget https://datasheets.raspberrypi.com/cmio/dt-blob-disp1-cam1.bin -O /boot/dt-blob.bin
```

After downloading this driver and restarting, the screen of DSI1 will work normally. If 
you want to use the HDMI interface, you need to delete the downloaded **/boot/dt-blob.bin** driver and restart, 

then the HDMI can output normally.

#### 1.4.3 CSI1 Camera

The DSI1 driver downloaded in 4.4.2 DSI1 Display Interface also includes the CSI1 driver. If you just want to install 

the CSI1 driver, not DSI1, please find the driver you want to use at https://datasheets.raspberrypi.com/licence.html 

and download it in the boot folder of CM4 and rename it to dt-blob.bin, and then refer to the settings here. 
https://projects.raspberrypi.org/en/projects/getting-started-with-picamera/

## 2. BIGTREETECH CB1 Setup steps

### 2.1 Download OS Image

If BIGTREETECH CB1 core board is used, You can only download and install the system image provided by BIGTREETECH:

https://github.com/bigtreetech/CB1/releases

### 2.2 Download and Install Raspberry Pi Imager

Install the official Raspberry Pi Imager: https://www.raspberrypi.com/software/
The system image of CB1 can also be written with this software.

### 2.3 Write OS Image

1. Plug the Micro SD card into the computer via a card reader.
2. Select Operating System.

<img src=img/Rasp1.png width="500"/>

3. Select "Use Custom", then select a custom.img from your computer.

<img src=img/Rasp2.png width="500"/>

4. Select the Micro SD card and click "WRITE" (Writing the image will format the Micro SD card.

   Be careful not to select the wrong storage device, otherwise, the data will be formatted).

<img src=img/Rasp5.png width="500"/>

5. Wait for the writing to finish.

<img src=img/Rasp6.png />

### 2.4 WIFI Setting

Note: This step can be skipped if you are using a network cable connection.CB1 cannot directly use the Raspberry Pi 

Imager to set the WiFi name and password like CM4. After the OS image writing is completed, the MicroSD card will 

have a FAT32 partition recognized by the computer, find "system.cfg"

<img src=img/M4P_WIFI1.png />



Open it with Notepad, replace WIFI-SSID with your WiFi name, and PASSWORD with your password.

<img src=img/wifi.png />

## 3. Configure the motherboard

### 3.1 ssh connect to device

1. Install the ssh application Mobaxterm: https://mobaxterm.mobatek.net/downloadhome-edition.html

2. Insert Micro SD card to M4P, wait for system to load after power on, aprox. 1-2min

3. The device will automatically be assigned a IP address after successfully connected to the network

4. Find the device IP address in your router page

<img src=img/Router.png />

5. Or use the https://angryip.org/ tool，scan all IP address in the current network organize by names, find

   the IP named Fluidd, Mailsail (CM4) or Hurakan (CB1) like shown below

<img src=img/AngryIP.png />

6. Open Mobaxtermand click “Session”, and click “SSH”，inset the device IP into Remote host and 

  click “OK” (note: your computer and the device needs to be in the same network)

<img src=img/MobaXterm_Login.png />

7. Input the login name and password to enter the SSH terminal interface
CM4:
 login as: pi
 password: raspberry
CB1:
 login as: biqu
 password: biqu

<img src=img/SSH_Terminal.png />

### 3.2 Compile firmware

1. After ssh successfully connected to the device, enter in terminal:

  ```
  cd ~/klipper/
  ```

  ```
  make menuconfig
  ```

  Compile with the configuration shown below(if the options below is not available, 
  please update you Klipper source code to the newest version)
* [*] Enable extra low-level configuration options 
* Micro-controller Architecture (STMicroelectronics STM32) ---> 
* Processor model (STM32G0B1) ---> 
* Bootloader offset (8KiB bootloader) ---> 
* Clock Reference (8 MHz crystal) ---> 
* Communication interface (USB (on PA11/PA12)) --->

<img src=img/M4P_Make.png />

3. Run **make** to compile firmware，”klipper.bin” file will be generated in **home/pi/kliiper/out** folder when make is finished, 

  download it onto your computer using the ssh application.

### 3.3 Firmware update

#### 3.3.1 Update using SD Card

1. Rename klipper.bin to ”firmware.bin”, Copy to the SD card root directory, insert the SD card into the SD card 

  slot of the M4P, click the “reset” button or power on again. The firmware will be updated automatically. After 

  the update, the "firmware.bin" in the SD card will be renamed as "FIRMWARE.CUR".

2. Enter: **ls /dev/serial/by-id/** in terminal to check motherboad ID to confirm 
    whether firmware is updated successfully like showm below.

```
ls /dev/serial/by-id/
```

<img src=img/M4P_Update_Using_SD.png />

#### 3.3.2 Update using DFU

If the MCU klipper device ID can be found by **ls /dev/serial/by-id/**, we can input:

```
make flash FLASH_DEVICE= /dev/serial/by-id/usb-Klipper_stm32g0b1xx_190028000D50415833323520-if00
```

to update firmware **(NOTE: Replace /dev/serial/by-id/xxx with the actual ID found in the previous step)**

<img src=img/M4P_DFU.png />

There will be an error message “dfu-util: Error during download get_status” after update. Just ignore it.

### 3.4 Configure Klipper

1. Enter your device IP address into your browser to open the webUI，find the reference config for motherboard 

  in the directory shown below，if there is no such config available, update your klipper source code to the newest

  version or download from github: https://github.com/bigtreetech/Manta-M4P

<img src=img/M4P_Conf_Klipper1.png />

2. Upload your finished config file into Configuration Files, and rename to “printer.cfg”

<img src=img/M4P_Conf_Klipper2.png />

3. Insert the correct motherboad ID

<img src=img/M4P_Conf_Klipper3.png />

Refer to https://www.klipper3d.org/Overview.html for detailed configuration guide according to your machine type.

## 4. Precautions

1. All unplugging and plugging operations should be performed under the condition of 
power off, including enabling the eMMC writing.
2. Pay attention to the heat dissipation of CM4 and CB1. If the running application 
consumes too many system resources, the CM4/CB1 will get hot quite seriously.





If you need other resources for this product, please visit https://github.com/bigtreetech/ 

and find them yourself. If you cannot find the resources you need, you can contact our after-sales support.



If you encounter other problems during use, feel free to contact us, and we are answering them carefully; 

Any good opinions or suggestions on our products are also welcome, too, and we will consider them carefully. 

Thank you for choosing BIGTREETECH. Your support means a lot to us! 
