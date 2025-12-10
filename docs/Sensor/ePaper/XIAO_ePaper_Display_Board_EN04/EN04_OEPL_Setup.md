---
description: Setup and Configure OpenEPaperLink with OpenEPaperLink BLE DIY Kit
title: Setup and Configure OpenEPaperLink with OpenEPaperLink BLE DIY Kit
keywords:
  - epaper
  - oepl
  - en04
image: https://github.com/user-attachments/assets/e72b5b6e-f477-467b-981d-5ffe05615f49
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
    <td><div align="center"><img width ={300} src="https://raw.githubusercontent.com/Misiu/seeed-wiki-documents/docusaurus-version/static/img/en04/1.jpg"/></div>
    <div class="get_one_now_container" style={{textAlign: 'center'}}>
        <a class="get_one_now_item" href="https://www.seeedstudio.com/XIAO-ePaper-Display-Board-nRF52840-EN04-p-6589.html" target="_blank">
                <strong><span><font color={'FFFFFF'} size={"4"}> Get One Now 🖱️</font></span></strong>
        </a>
    </div></td>
    </tr>
 </table>
</div>

## Introduction

Powered by **XIAO nRF52840** Plus, the XIAO EN04 ePaper Display Board is the easiest way to get started with Bluetooth-enabled e-paper displays using the OEPL_BLE firmware. Unlike traditional OpenEPaperLink systems that require dedicated Access Points with 802.15.4 radios, this board uses Bluetooth Low Energy for direct wireless control from your phone, computer, or Home Assistant.

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
- **Purpose-built Hardware**: Designed for boards like the EN04, not limited to commercial ESL tags
- **Open Source & Free**: Completely open-source project with active development on GitHub
- **Multiple Microcontroller Support**: Works with nRF52840, ESP32-S3, ESP32-C6, and ESP32-C3
- **Simple Setup**: Upload firmware via drag and drop a single file to your board, configure via web interface, no complex programming required
- **Battery Efficient**: Optimized for low-power operation with e-paper displays
- **Active Community**: Support and development through [OpenEPaperLink Discord](https://discord.gg/fekcBc5RN5)


## Getting Started with OEPL_BLE

### Hardware Assembly

**Step 1. Connect Display to Driver Board**  
Align the FPC cable with the connector on the XIAO EN04 Board, then secure the latch to ensure a firm connection.  

:::tip
The metal side of the FPC cable should face upwards, otherwise, no content will be displayed. Most displays have 1 and 50 on FPC cable, those numbers must align with the ones on the board!

Please follow the installation tutorial below, many people get it wrong.
:::

<div style={{textAlign:'center'}}><img src="https://raw.githubusercontent.com/Misiu/seeed-wiki-documents/docusaurus-version/static/img/en04/1.jpg" style={{width:600, height:'auto'}}/></div>

**Step 2. Attach the Battery**  
Connect the battery cable to the JST connector on the driver board, ensuring correct polarity (red wire to +, black to -).  

<div style={{textAlign:'center'}}><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1741838/525020218-945edbab-c546-4fef-b480-ee1524d33edf.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251210%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251210T200721Z&X-Amz-Expires=300&X-Amz-Signature=c9d62d562bca5f7078bea7955ec276721a0dfd5cf87f3866c9a05f7f3c6b3e88&X-Amz-SignedHeaders=host" style={{width:600, height:'auto'}}/></div>

:::caution
Double check the polarity, different batteries can have mixed wiring. If the red and black are misaligned, they can be easily removed from JST connector using a needle and then positioned correctly.
:::



## Installing OEPL_BLE Firmware

### Web Installer Method (Recommended)

The easiest way to install the OEPL_BLE firmware is using the web-based installer.

**Step 1. Open Web Installer**  
Visit the [OEPL Web Installer](https://openepaperlink.org/ble/install/) in a browser.

**Step 2. Select Your Device**  
Choose **"Seeed EN04 4.26"** or **"Seeed EN04 7.3"** (or any preset that suits your hardware) from the device list (based on the display size in your kit).

**Step 3. Download the firmware**  
Click the **"Download Firmware"** button and save the **"NRF52840.uf2"** on your hard drive.

**Step 4. Connect Your Board**  
Connect the XIAO ePaper Board EN04 to your computer using a USB-C cable.

**Step 5. Install Firmware**  
Press the reset button twice consecutively. You will see a file manager pop up on your PC. Copy the downloaded **"NRF52840.uf2"** file to the USB drive that appears (the USB drive is the EN04 board in DFU mode)

:::tip
If the installation fails, try:
- Using a different USB cable (some cables are power-only)
- Pressing the reset button twice on the EN04 board
- Using a different USB port
:::

**Step 6. Configure the Board**  
Open the [OEPL Configuration Page](https://openepaperlink.org/ble/config/?config=nrf52840-en04-s6) and connect to your board.


<div style={{textAlign:'center'}}><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1741838/525021717-d9797294-ef68-41a1-81d3-f3024ed051dd.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251210%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251210T201205Z&X-Amz-Expires=300&X-Amz-Signature=9c4a916a5dfaad6e3cac4c694457f1ef3817ac0e78df0dbba6e5b3ea201f56c3&X-Amz-SignedHeaders=host" style={{width:600, height:'auto'}}/></div>


If you selected **"Seeed EN04 4.26"** or **"Seeed EN04 7.3"**, you will see **"Auto Install to Device"**.
This is the easiest way to configure your DIY Kit.

**Step 7. Connect to the Board**
Press the **""Connect** button on the page. You should see a window showing available OEPl devices, select the new device and press **""Pair**

<div style={{textAlign:'center'}}><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1741838/525023030-fbeff42a-0c9e-4f89-8bb5-561012d614c1.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251210%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251210T201610Z&X-Amz-Expires=300&X-Amz-Signature=9bd2778f4b854412059c5a660fa7a3f2db555df66da7af4d0fc161dbfab6d47c&X-Amz-SignedHeaders=host" style={{width:500, height:'auto'}}/></div>


**Step 7. Save the configuration to the Board**  
The last thing to do is to press the **"Auto Install to Device"** button, this will save the configuration to the device.


### Verify Configuration

After installation and configuration, the display should show a startup screen. The device is now ready to display content via Bluetooth.

<div style={{textAlign:'center'}}><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1741838/525024428-a9577e37-0346-4199-b8d0-5fdf43bfbfd8.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251210%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251210T202010Z&X-Amz-Expires=300&X-Amz-Signature=d22c5f729b7960e101f7ba80ca155a4e0aedaf3695528f4953cff28e334f0191&X-Amz-SignedHeaders=host" style={{width:500, height:'auto'}}/></div>




## Uploading Images to Display

### Using the Web Display Tool

**Step 1. Open Display Tool**  
Visit [OpenEPaperLink BLE Tester](https://openepaperlink.org/ble/display/) in your browser.

**Step 2. Connect to Device**  
Click **"Connect"** and select your OEPL device from the Bluetooth pairing dialog.

**Step 3. Select Image**  
Click **"Select Image"** and choose an image file from your computer.


<div style={{textAlign:'center'}}><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1741838/525025512-bd864447-a8ad-4bfb-a963-29940957b3da.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251210%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251210T202254Z&X-Amz-Expires=300&X-Amz-Signature=8a6d5cb84df433e70d0fca9018b1198d2dcc08e9f7a9fddebf76190cb1c047df&X-Amz-SignedHeaders=host" style={{width:500, height:'auto'}}/></div>




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


### Home Assistant Integration
:::tip
To integrate with Home Assistant, you need a Bluetooth-capable setup:
- **Home Assistant Green** (built-in Bluetooth)
- **Home Assistant OS/Supervised** on hardware with Bluetooth support
- **ESPHome Bluetooth Proxy** (recommended for better range)

**Note**: Shelly devices acting as Bluetooth proxies **do not support active connections** required by OEPL, so they cannot be used for this integration.
:::

**Step 1. Install Integration**

For detailed installation instructions, please refer to the [OpenEPaperLink Home Assistant Integration Repository](https://github.com/OpenEPaperLink/Home_Assistant_Integration?tab=readme-ov-file#getting-help).

The easiest way to install the integration is via **HACS** (Home Assistant Community Store). Click the button below to open the repository directly in HACS:

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=OpenEpaperLink&repository=Home_Assistant_Integration)

:::info
After installing the custom integration via HACS, you must **restart Home Assistant** for the changes to take effect.
:::

**Step 2. Add Discovered Device**

Once Home Assistant has restarted:
1. Navigate to **Settings > Devices & services**.
2. You should see your OEPL device listed under **Discovered**.
3. Click on**Add**.
4. A dialog will appear allowing you to set the device **Name** and **Area**.
5. Click **Finish**. You will be redirected to the device details page where you can manage your e-paper display.

You will see a new image displayed on the display, showing that the device is connected to Home Assistant.


<div style={{textAlign:'center'}}><img src="https://github-production-user-asset-6210df.s3.amazonaws.com/1741838/525025512-bd864447-a8ad-4bfb-a963-29940957b3da.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251210%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251210T202254Z&X-Amz-Expires=300&X-Amz-Signature=8a6d5cb84df433e70d0fca9018b1198d2dcc08e9f7a9fddebf76190cb1c047df&X-Amz-SignedHeaders=host" style={{width:500, height:'auto'}}/></div>



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
