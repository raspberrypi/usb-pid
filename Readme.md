# Raspberry Pi USB product ID list

## Allocation
The USB-IF have given Raspberry Pi permission to sub-license the USB product ID values for its vendor ID (0x2E8A) since they are to be used on a common silicon component which will be used within a customer's product (the RP2040 silicon).  For each of the allocations we (Raspberry Pi) will have to apply to the USB-IF to agree this use.  This document then contains the full list of product IDs we have approved.

## Use of the IDs
Before filling in the form, please think about why you would like a separate ProductID.  In general, the only reason to require one is because Windows uses the product ID to select a vendor-specific driver for a USB device.  If you are not using a vendor specific driver and instead using a standard interface driver, such as the CDC interface (for serial devices) or a HID driver (keyboards, mice and touchscreens among others).  Please put that information into the form and we can create a standard PID to cover devices with that particular interface combination.

If you are using the standard VID/PID combination, you can still use the iManufacturer, iProduct and iSerial strings to determine and identify your particular device.  To see these on a Linux console just do 'lsusb -v' when your device is attached.

This is a common way of identifying a particular interface device (For example, the ARM CMSIS-DAP specification includes the ability to have 'CMSIS-DAP' in the product name).  This can then be used inside a udev script to control the product, here's an example from the OpenOCD sources:

```
# CMSIS-DAP compatible adapters
ATTRS{product}=="*CMSIS-DAP*", MODE="660", GROUP="plugdev", TAG+="uaccess"
```

So you can do really useful things like run your own scripts:
```
ATTRS{product}=="*MY-AWESOME-TOY*", MODE="660", GROUP="plugdev", TAG+="uaccess", RUN+="/usr/local/bin/my_script.sh"
```

Note, udev will be blocked during the running of the script, if you want to start some background process, your script should do something like `systemctl start my_service.service` to start a systemd service.

## Assignment

To create an assignment, go to the [application form](https://docs.google.com/forms/d/e/1FAIpQLSeaAkcxVD5xSgf-vFdZe7URqDeUhAo9Vx-17YZgtpXpeTHpVQ/viewform?usp=sf_link) filling in the relevant information.  If you would like to reserve an allocation before making a new product public, select that option and email info@raspberrypi.com to request activation of the allocation when you are ready to go public (failure to do this will mean losing the allocation).

Vendor-ID = 0x2E8A

| Product ID | Company | Product Description | Product link |
| --- | --- | --- | --- |
| **Internal** | | | |
| 0x0003 | Raspberry Pi | Raspberry Pi RP2040 boot | [RP2040](https://www.raspberrypi.org/documentation/pico/getting-started/) |
| 0x0004 | Raspberry Pi | Raspberry Pi PicoProbe | [PicoProbe](https://github.com/raspberrypi/picoprobe/) | NA |
| 0x0005 | Raspberry Pi | Raspberry Pi Pico MicroPython firmware (CDC) | [MicroPython Firmware](https://micropython.org/download/rp2-pico/) |
| 0x000A | Raspberry Pi | Raspberry Pi Pico SDK CDC UART | [Raspberry Pi Pico SDK](https://raspberrypi.github.io/pico-sdk-doxygen/index.html) |
| 0x000B | Raspberry Pi | Raspberry Pi Pico CircuitPython firmware | [CircuitPython Downloads](https://circuitpython.org/board/raspberry_pi_pico/) |
| 0x000C | Raspberry Pi | Raspberry Pi RP2040 CMSIS-DAP debug adapter |  |
| 0x000D | Raspberry Pi | Raspberry Pi USB3HUB ( USB2 hub part) |  |
| 0x000E | Raspberry Pi | Raspberry Pi USB3HUB ( USB3 hub part) |  |
| **Commercial** ||||
| **0x1000 - 0x1fff** ||||
| 0x1000 | Cytron Technologies | Cytron Maker Pi RP2040 | https://www.cytron.io/p-maker-pi-rp2040 |
| 0x1001 | Pimoroni | Picade 2040 | http://pimoroni.com/picade2040 |
| 0x1002 | Pimoroni | Pimoroni Pico Lipo (4MB) | https://shop.pimoroni.com/products/pimoroni-pico-lipo |
| 0x1003 | Pimoroni | Pimoroni Pico Lipo (16MB) | https://shop.pimoroni.com/products/pimoroni-pico-lipo |
| 0x1004 | Reserved 2 ||| 
| 0x1005 | Melopero S.r.l.s. | Melopero Shake RP2040 | https://www.melopero.com/melopero-shake-rp2040 | 
| 0x1006 | Invector Labs AB | Challenger 2040 | https://site.invector.se/produkt/challenger-2040/ |
| 0x1008 | Pimoroni | Pimoroni PGA2040 | https://shop.pimoroni.com/products/pga2040 | 
| 0x1009 | Pimoroni | Pimoroni Interstate 75 | https://pimoroni.com/i75 |
| 0x100a | Pimoroni | Pimoroni Plasma 2040 | https://pimoroni.com/plasma2040 |
| 0x100b | Invector Labs AB | Challenger RP2040 LTE | https://ilabs.se/product/challenger-rp2040-lte/ |
| 0x100c | Tranquility IT Inc. | CNC Control Pendant | https://www.madewithcnc.com/products/hand-held-console-for-tormach-path-pilot-cnc-machines |
| 0x100d | Invector Labs AB | Challenger NB RP2040 WiFi | https://ilabs.se/product/challenger-nb-rp2040-wifi/ |
| 0x100E | Adafruit Industries LLC | Raspberry Pi Zero | https://circuitpython.org/board/raspberrypi_zero/ |
| 0x100f | Cytron Technologies | Cytron Maker Nano RP2040 | https://www.cytron.io/p-maker-nano-rp2040 |
| 0x1010 | Invector Labs AB | RPICO32 | |
| 0x1011 | Melopero S.r.l. | Melopero Cookie RP2040 | https://melopero.com/melopero-cookie-rp2040 |
| 0x1012 | Adafruit Industries LLC | Raspberry Pi CM4 IO | https://circuitpython.org/board/raspberrypi_cm4io |
| 0x1013 | Adafruit Industries LLC | Raspberry Pi 4 | https://circuitpython.org/board/raspberrypi_pi4b |
| 0x1014 | Adafruit Industries LLC | Raspberry Pi CM4 | https://circuitpython.org/board/raspberrypi_cm4 |
| 0x1015 | Adafruit Industries LLC | Raspberry Pi Zero 2W | https://circuitpython.org/board/raspberrypi_zero2w |
| 0x1016 | Pimoroni Ltd | Pimoroni Tiny 2040 (2MB) | https://pimoroni.com/tiny2040 |
| 0x1017 | Pimoroni Ltd | Pimoroni Automation 2040 W | https://pimoroni.com/automation2040w |
| 0x1018 | Pimoroni Ltd | Pimoroni Inky Frame 5.7" | https://shop.pimoroni.com/products/inky-frame-5-7 |
| 0x1019 | Pimoroni Ltd | Pimoroni Motor 2040 | https://pimoroni.com/motor2040 |
| 0x101A | Pimoroni Ltd | Pimoroni Servo 2040 | https://pimoroni.com/servo2040 |
| 0x101B | Pimoroni Ltd | Pimoroni Badger 2040 | https://pimoroni.com/badger2040 |
| 0x101E | Adafruit Industries | Raspberry Pi Zero W | https://circuitpython.org/board/raspberrypi_zero_w/ |
| 0x101F | Waveshare Electronics | RP2040-Zero | https://www.waveshare.com/rp2040-zero.htm |
| 0x1020 | Waveshare Electronics | RP2040-Plus | https://www.waveshare.com/rp2040-plus.htm |
| 0x1021 | Waveshare Electronics | RP2040-LCD-0.96 | https://www.waveshare.com/rp2040-lcd-0.96.htm |
| 0x1022 | Reserved | | |
| 0x1023 | Invector Labs AB | Challenger RP2040 LoRa | https://ilabs.se/product/challenger-rp2040-lora/ |
| 0x1025 | Lone Dynamics Corporation | M?sli USB Pmod | https://machdyne.com/product/musli-usb-pmod/ |
| 0x1026 | ELECFREAKS TECHNOLOGY | Pico:ed | https://www.elecfreaks.com/picoed.html |
| 0x1027 | WIZnet Co., Ltd. | W5100S-EVB-Pico | https://docs.wiznet.io/Product/iEthernet/W5100S/w5100s-evb-pico |
| 0x1028 | WIZnet Co., Ltd. | WizFi360-EVB-Pico | https://docs.wiznet.io/Product/Open-Source-Hardware/wizfi360-evb-pico |
| 0x1029 | WIZnet Co., Ltd. | W5500-EVB-Pico | https://docs.wiznet.io/Product/iEthernet/W5500/w5500-evb-pico |
| 0x102A | Input Integrity | Lossless Adapter | TBD (No website yet) |
| 0x102B | Input Integrity | Slippi latency tester | TBD (No website yet) |
| 0x102C | Invector Labs AB | Challenger RP2040 WiFi/BLE | https://ilabs.se/challenger-rp2040-wifi-ble-datasheet/ |
| 0x102D | Invector Labs AB | Challenger RP2040 SD/RTC | https://ilabs.se/challenger-rp2040-sd-rtc-datasheet/ |
| 0x102E | Jinan  Yuandi Instrument Equlpment Co.,Ltd | YD-RP2040 | https://www.aliexpress.com/item/1005004004120604.html?spm=5261.ProductManageOnline.0.0.25234edfWXVdRg |
| 0x102F | 20XX Corp | B0XX | https://b0xx.com |
| 0x1030 | maxsol gmbh | RF-ID Reader | www.maxsol.de |
| 0x1031 | maxsol gmbh | RF-ID Reader | www.maxsol.de |
| 0x1032 | Invector Labs AB | Challenger RP2040 SubGHz | https://ilabs.se/challenger-rp2040-subghz-rfm69hcw-datasheet/ |
| 0x1035 | LightWare Optoelectronics (Pty) Ltd | LightWare Lidar | https://lightwarelidar.com/collections/lidar-rangefinders |
| 0x1037 | Electronic Cats | Hunter Cat NFC | https://github.com/ElectronicCats/BomberCat |
| 0x1038 | i4M technologies GmbH | nemi Link USB Receiver | https://nemi.one/en/products.html |
| 0x1039 | Waveshare Electronics | RP2040-LCD-1.28 | No website yet |
| 0x103A | Waveshare Electronics | RP2040-One | No website yet |
| 0x103B | FAST Pinball, LLC | FAST Pinball Controller | https://docs.fastpinball.com/products/controllers/neuron/ |
| 0x103C | FAST Pinball, LLC | FAST Pinball Audio | https://docs.fastpinball.com/products/audio/audio-interface/ |
| 0x103D | FAST Pinball, LLC | FAST Pinball Expansion | https://docs.fastpinball.com/products/expansion/201/ |
| 0x103E | FAST Pinball, LLC | FAST Pinball Display | https://docs.fastpinball.com/products/display/rgb-dmd/ |
| 0x103F | Electronic Cats | BomberCat | https://electroniccats.com/store/bombercat/ |
| 0x1040 | Invector Labs AB | Challenger RP2040 NFC | https://ilabs.se/challenger-rp2040-nfc-datasheet/ |
| 0x1041 | BridgeTek Pte Ltd | IDM2040-7A | https://brtchip.com/ic-module/product/idm2040-7a/ |
| 0x1042 | Interact Labs | TACT | https://www.interact-labs.com/ |
| 0x1044 | Waveshare Electronics | Power Management HAT (B) | https://www.waveshare.com/power-management-hat-b.htm |
| 0x1045 | Velocitronics Motion Systems, Inc. | Vms LX4e Laser Controller | Not assigned yet |
| 0x1046 | WIZnet Co., Ltd. | W6100-EVB-Pico | https://docs.wiznet.io/Product/iEthernet/W6100/w6100-evb-pico |
| 0x1048 | NULLBITS LLC | nullbits Bit-C PRO RP2040 | nullbits.co/bit-c-pro |
| 0x104A | boardsrc | Blok | https://boardsource.xyz/store/628b95b494dfa308a6581622 |
| 0x104B | Datanoise UG (haftungsbeschr?nkt) | PicoADK | https://github.com/DatanoiseTV/PicoADK-Firmware-Template |
| 0x104C |  Advanced Design Technology co.,ltd. | COSMO-Pico | https://pico.cosmo-edtech.jp/ |
| 0x104D |  MaxxStick Controllers | MaxxStick R3 | https://maxxstick.com |
| 0x104E | Spectra GmbH & Co. KG | CDC / HID device |  |
| 0x104F | Pimoroni Ltd | Pimoroni Badger 2040 W | https://shop.pimoroni.com/products/badger-2040-w |
| 0x1050 | Open Gadgets LLC | Pixelcade | http://pixelcade.org |
| 0x1051 | SOELPEC TEKNOLOJI LTD. STI. | SOELPEC - Spectra XR |  |
| 0x1052 | Invector Labs AB | Challenger RP2040 UWB | https://ilabs.se/challenger-rp2040-uwb-datasheet/ |
| 0x1053 | Dahl Design | DDC controller software | https://github.com/andreasdahl1987/DahlDesignDDC |
| 0x1054 | SOELPEC TEKNOLOJI LTD. STI. | SOELPEC - XR-5 Display |  |
