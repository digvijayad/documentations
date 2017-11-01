---
title: Introduction ( Rpi )
keywords: Noobs, Install
summary: 
sidebar: raspberry_sidebar
permalink: /rpi_introduction.html
folder: raspberry
---

## Raspberry Pi Introduction
To Download and Install NOOBS either follow the following steps or watch the [video instruction](https://www.raspberrypi.org/help/noobs-setup/2/) from official website: 
## DOWNLOAD

We recommend using an SD card with a minimum capacity of 8GB.

1. Using a computer with an SD card reader, visit the [Downloads](http://www.raspberrypi.org/downloads/) page.
1. Click on NOOBS, then click on the Download ZIP button under ‘NOOBS (offline and network install)’, and select a folder to save it to.
1. Extract the files from the zip.

## FORMAT YOUR SD CARD

It is best to format your SD card before copying the NOOBS files onto it. To do this:

1. Visit the [SD Association’s website](http://www.sdcard.org/) and download [SD Formatter 4.0](https://www.sdcard.org/downloads/formatter_4/) for either Windows or Mac.
1. Follow the instructions to install the software.
1. Insert your SD card into the computer or laptop’s SD card reader and make a note of the drive letter allocated to it, e.g. G:/
1. In SD Formatter, select the drive letter for your SD card and format it.

## DRAG AND DROP NOOBS FILES

1. Once your SD card has been formatted, drag all the files in the extracted NOOBS folder and drop them onto the SD card drive.
1. The necessary files will then be transferred to your SD card.
1. When this process has finished, safely remove the SD card and insert it into your Raspberry Pi.

## FIRST BOOT

1. Plug in your keyboard, mouse, and monitor cables.
1. Now plug the USB power cable into your Pi.
1. Your Raspberry Pi will boot, and a window will appear with a list of different operating systems that you can install. We recommend that you use Raspbian – tick the box next to Raspbian and click on ```Install```.
1. Raspbian will then run through its installation process. Note that this can take a while.
1. When the install process has completed, the Raspberry Pi configuration menu (raspi-config) will load. Here you are able to set the time and date for your region, enable a Raspberry Pi camera board, or even create users. You can exit this menu by using Tab on your keyboard to move to ```Finish```.

## LOGGING IN AND ACCESSING THE GRAPHICAL USER INTERFACE

The default login for Raspbian is username pi with the password raspberry. Note that you will not see any writing appear when you type the password. This is a security feature in Linux.

To load the graphical user interface, type startx and press Enter.