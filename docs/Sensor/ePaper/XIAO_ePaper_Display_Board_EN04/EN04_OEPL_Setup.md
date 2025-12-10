---
description: Setup and Configure OpenEPaperLink with OpenEPaperLink BLE DIY Kit
title: Setup and Configure OpenEPaperLink with OpenEPaperLink BLE DIY Kit
keywords:
  - epaper
  - oepl
  - en04
image: https://files.seeedstudio.com/wiki/Epaper/EN04/EN04_2.webp
sidebar_position: 1
slug: /epaper_EN04_OEPL
last_update:
  date: 12/10/2025
  author: Tomasz
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import Steppers from '@site/src/components/utils/Stepper';

# Setup and Configure OpenEPaperLink with OpenEPaperLink BLE DIY Kit

<div class="table-center">
<table align="center">
    <tr>
        <th>OpenEPaperLink BLE DIY Kit</th>
    </tr>
    <tr>
    <td><div align="center"><img width ={300} src="https://files.seeedstudio.com/wiki/XIAO_Gadget/TRMNL_Kit_Pic/2.jpg"/></div>
    <div class="get_one_now_container" style={{textAlign: 'center'}}>
        <a class="get_one_now_item" href="https://www.seeedstudio.com/XIAO-ePaper-Display-Board-nRF52840-EN04-p-6589.html" target="_blank">
                <strong><span><font color={'FFFFFF'} size={"4"}> Get One Now 🖱️</font></span></strong>
        </a>
    </div></td>
    </tr>
 </table>
</div>

## Introduction

Powered by **XIAO nRF52840** Plus, the OpenEPaperLink BLE DIY Kit is the easiest way to get started with Bluetooth-enabled e-paper displays using the OEPL_BLE firmware. Unlike traditional OpenEPaperLink systems that require dedicated Access Points with 802.15.4 radios, this kit uses Bluetooth Low Energy for direct wireless control from your phone, computer, or Home Assistant.

The OpenEPaperLink BLE DIY Kit includes:
- **XIAO ePaper Board EN04** x1 - Custom designed board with nRF52840, battery management, and display driver
- **7.3" spectra™ 6 E-Ink / ePaper Display** x1 - 800x480 resolution e-paper panel
- **FPC Extension Cable (10 cm)** x1 - For flexible display placement
- **FPC Connector** x1 - For connecting display to board
- **2000mAh Battery** x1 - Li-Po battery for portable operation

Everything is ready to use - just assemble the hardware, install the firmware, configure the device via web browser, and start displaying custom content!

### Application

- **Smart Home Dashboard**: Display real-time information such as weather updates, calendar events, and notifications from various smart home devices.
- **Energy Monitoring**: Show energy consumption data from smart meters, helping homeowners track and manage their energy usage more efficiently.
- **Security Alerts**: Display alerts and notifications about security events, such as motion detection or door/window sensor activation.
- **Smart Thermostat Display**: Show temperature and humidity levels, as well as control settings for your smart thermostat.

## What is [OpenEPaperLink](https://openepaperlink.de/)?

OpenEPaperLink (OEPL) is an open-source project that provides firmware and protocols for e-paper displays. While the main OEPL project focuses on repurposing commercial Electronic Shelf Labels (ESL), the **OEPL_BLE firmware** is designed specifically for custom hardware builds using microcontrollers like the nRF52840 and ESP32.

The [OEPL_BLE firmware](https://github.com/OpenEPaperLink/OEPL_BLE) enables:
- **Bluetooth Low Energy (BLE) Communication**: Direct wireless control without requiring dedicated access points
- **Dedicated Hardware Support**: Works with purpose-built boards like the XIAO ePaper Board EN04, EE04, and others
- **Web-based Flashing and Configuration**: Easy setup and image upload through web interface at [openepaperlink.org/ble](https://openepaperlink.org/ble/)
- **Multiple Display Support**: Compatible with various e-paper sizes and controllers


### Why use OEPL_BLE?

The OEPL_BLE firmware offers several advantages for custom e-paper display projects:

- **No Access Point Required**: Uses Bluetooth Low Energy for direct communication - no additional hardware needed
- **Web-based Tools**: Easy firmware installation, configuration, and image upload through browser-based tools
- **Purpose-built Hardware**: Designed for custom boards like the EN04, not limited to commercial ESL tags
- **Open Source & Free**: Completely open-source project with active development on GitHub
- **Multiple Microcontroller Support**: Works with nRF52840, ESP32-S3, ESP32-C6, and ESP32-C3
- **Simple Setup**: Upload firmware via web installer, configure via web interface, no complex programming required
- **Battery Efficient**: Optimized for low-power operation with e-paper displays
- **Active Community**: Support and development through [OpenEPaperLink Discord](https://discord.gg/fekcBc5RN5)

The OpenEPaperLink BLE DIY Kit with EN04 board provides everything needed to create a custom BLE-enabled e-paper display right out of the box.

## Getting Started with OEPL_BLE

### Hardware Assembly

**Step 1. Connect Display to Driver Board**  
Align the FPC cable with the connector on the XIAO EN04 Board, then secure the latch to ensure a firm connection.  

:::tip
The metal side of the FPC cable should face upwards, otherwise, no content will be displayed. Most displays have 1 and 50 on FPC cable, those numbers must align with the ones on the board!

Please follow the installation tutorial below, many people get it wrong.
:::

<div style={{textAlign:'center'}}><img src="https://files.seeedstudio.com/wiki/XIAO_Gadget/TRMNL_Kit_Pic/2.jpg" style={{width:600, height:'auto'}}/></div>

**Step 2. Attach the Battery**  
Connect the battery cable to the JST connector on the driver board, ensuring correct polarity (red wire to +, black to -).  

<div style={{textAlign:'center'}}><img src="https://files.seeedstudio.com/wiki/XIAO_Gadget/TRMNL_Kit_Pic/3.jpg" style={{width:600, height:'auto'}}/></div>

:::caution
Double check the polarity, different batteries can have mixed wiring. If the red and black are misaligned, they can be easily removed from JST connector using a needle and then positioned correctly.
:::



## Installing OEPL_BLE Firmware

### Web Installer Method (Recommended)

The easiest way to install the OEPL_BLE firmware is using the web-based installer.

**Step 1. Connect Your Board**  
Connect the XIAO ePaper Board EN04 to your computer using a USB-C cable.

**Step 2. Open Web Installer**  
Visit the [OEPL Web Installer](https://openepaperlink.org/ble/install/) in a browser.

**Step 3. Select Your Device**  
Choose **"Seeed EN04 4.26"** or **"Seeed EN04 7.3"** from the device list (based on the display size in your kit).

<div style={{textAlign:'center'}}><img src="https://files.seeedstudio.com/wiki/Epaper/EN04/oepl_install_1.png" style={{width:800, height:'auto'}}/></div>

**Step 4. Download the firmware**  
Click the **"Download Firmware"** button and save the **"NRF52840.uf2"** on your hard drive.

**Step 5. Install Firmware**  
Connect the EN04 board to the computer using a USB data cable, then press the reset button twice consecutively. You will see a file manager pop up on your PC. Copy the downloaded **"NRF52840.uf2"** file to the USB drive that appears (the USB drive is the EN04 board in DFU mode)

:::tip
If the installation fails, try:
- Using a different USB cable (some cables are power-only)
- Pressing the reset button twice on the EN04 board
- Using a different USB port
:::


**Step 6. Configure the Board**  
Open the [OEPL Configuration Page](https://openepaperlink.org/ble/config/?config=nrf52840-en04-s6) and connect to your board.

(image here)

If you selected **"Seeed EN04 4.26"** or **"Seeed EN04 7.3"**, you will see **"Auto Install to Device"**.
This is the easiest way to configure your DIY Kit.

**Step 6a. Configure Different Display Sizes and Battery Usage**

TBD

### Verify Configuration

After installation and configuration, the display should show a startup screen (image to be added). The device is now ready to display content via Bluetooth.


## Uploading Images to Display

### Using the Web Display Tool

**Step 1. Open Display Tool**  
Visit [OpenEPaperLink BLE Tester](https://openepaperlink.org/ble/display/) in your browser.

**Step 2. Connect to Device**  
Click **"Connect"** and select your OEPL device from the Bluetooth pairing dialog.

**Step 3. Select Image**  
Click **"Select Image"** and choose an image file from your computer.

:::tip
For best results:
- Use images that match your display resolution (7.3" display is 800x480 pixels)
- Black and white images work best on monochrome displays
- The tool will automatically convert and dither color images
:::

**Step 4. Upload Image**  
Click **"Upload Image"** to send the image to your display. The e-paper will refresh and show your image.

### Creating Custom Content

You can create custom display content using:
- Image editing software (GIMP, Photoshop, etc.)
- Python scripts with PIL/Pillow library
- Web-based image generators
- Home Assistant integration


## Troubleshooting

### Firmware Installation Issues

**Problem**: PC doesn't detect a new USB drive after connecting the EN04 board
- **Solution**: 
  - Try a different USB cable (data cable, not power-only)
  - Press the reset button twice after connecting the board


### Configuration Issues

**Problem**: The EN04 board isn't discovered
- **Solution**:
  - Verify the LED on the board blinks - this confirms the device is powered
  - Try rebooting the board
  - Verify the firmware installation or copy the file again

**Problem**: Display shows nothing after firmware installation
- **Solution**:
  - Verify the FPC cable is inserted correctly (metal contacts facing up)
  - Check that the cable is fully inserted and latched
  - Verify if the configuration is correct (you can connect to the board via the configurator and read the configuration)


### Bluetooth Connection Issues

**Problem**: Cannot find OEPL device in Bluetooth pairing
- **Solution**:
  - Ensure device is powered on and firmware is installed
  - Move closer to the device (within 2-3 meters)
  - Check that Bluetooth is enabled on your computer/phone

**Problem**: Connection drops during image upload
- **Solution**:
  - Stay close to the device during upload
  - Ensure battery is sufficiently charged or power the device via USB
  - Avoid uploading very large images
  - Try again with a more stable Bluetooth environment

### Battery and Power Issues

**Problem**: Short battery life
- **Solution**:
  - Configure longer sleep intervals in the configurator
  - Always use the latest version of the firmware; each version optimizes battery usage
  - Reduce display refresh frequency
  - Verify battery is fully charged (4.2V for Li-Po)

**Problem**: Device won't charge
- **Solution**:
  - Check battery polarity (red: +, black: -)
  - Verify charging cable provides sufficient current (min. 500mA)
  - Ensure power switch is in ON position
  - Test with different USB power source

## Resources

- **[GitHub]** [OEPL_BLE Firmware Repository](https://github.com/OpenEPaperLink/OEPL_BLE)
- **[Web Tool]** [Firmware Web Installer](https://openepaperlink.org/ble/install/)
- **[Web Tool]** [Configuration Builder](https://openepaperlink.org/ble/config/)
- **[Web Tool]** [Display Tester](https://openepaperlink.org/ble/display/)
- **[Discord]** [OpenEPaperLink Community](https://discord.gg/fekcBc5RN5)
- **[Website]** [OpenEPaperLink Official Site](https://openepaperlink.de/)
- **[Documentation]** [OpenEPaperLink Wiki](https://github.com/OpenEPaperLink/OpenEPaperLink/wiki)

### Hardware Resources
Coming soon...
<!-- - **[PDF]** [Seeed Studio XIAO ePaper Display EN04 Schematic](https://files.seeedstudio.com/wiki/Epaper/EN04/XIAO_ePaper_Display_Board_EN04_SCH_V1.2.pdf)
- **[3D Model]** [Seeed Studio XIAO ePaper Display EN04 GrabCAD](https://grabcad.com/library/xiao-epaper-display-board-nRF52840-EN04-1)
- **[ZIP]** [Seeed Studio XIAO ePaper Display EN04 SCH&PCB](https://files.seeedstudio.com/wiki/Epaper/EN04/XIAO_ePaper_Display_Board_EN04_V1.2_SCH&PCB.zip) -->



## Tech Support & Product Discussion

Thank you for choosing our products! We are here to provide you with different support to ensure that your experience with our products is as smooth as possible. We offer several communication channels to cater to different preferences and needs.

<div class="button_tech_support_container">
<a href="https://forum.seeedstudio.com/" class="button_forum"></a>
<a href="https://www.seeedstudio.com/contacts" class="button_email"></a>
</div>

<div class="button_tech_support_container">
<a href="https://discord.gg/eWkprNDMU7" class="button_discord"></a>
<a href="https://github.com/Seeed-Studio/wiki-documents/discussions/69" class="button_discussion"></a>
</div>
