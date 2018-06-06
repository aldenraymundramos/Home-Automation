# My Home Automation Project


This is about my home automation project which will revolve around the Raspberry Pi and other IOT Items. This will be a series of home projects and will add more projects as I make them. Enjoy!

#### Prerequisites

- Raspberry Pi 3 B/+
- 16GB or higher capacity uSD Card
- Micro SD Card Adapter


#### Setting Up Raspberry Pi

##### Install Raspbian into your SD Card (Mac)

(Mostly) graphical interface

1. Download the latest version of Raspbian via link [Raspbian](https://www.raspberrypi.org/downloads/raspbian/).

2. Connect the SD card reader with the SD card inside. Note that it must be formatted as FAT32.

3. From the Apple menu, choose 'About This Mac', then click on 'More info...'. If you are using Mac OS X 10.8.x Mountain Lion or newer, you will then need to click on 'System Report'.
4. Click on 'USB' (or 'Card Reader' if you are using a built-in SD card reader), then search for your SD card in the upper right section of the window. Click on it, then search for the BSD name in the lower right section. It will look something like diskn where n is a number (for example, disk4). Make sure you take a note of this number.
5. Unmount the partition so that you will be allowed to overwrite the disk. To do this, open Disk Utility and unmount it. Do not eject it. If you eject it, you will have to reconnect it. Note that on Mac OS X 10.8.x Mountain Lion, 'Verify Disk' (before unmounting) will display the BSD name as /dev/disk1s2 or similar, allowing you to skip the previous two steps. Note down the number that appears after 'disk', in this case the number '1'.

6. From the terminal, run the following command:
```
sudo dd bs=1m if=path_of_your_image.img of=/dev/rdiskn conv=sync
```
Remember to replace n with the number that you noted before!

   This will take a few minutes, depending on the image file size. You can check the progress by sending a SIGINFO signal (press Ctrl+T).

7. If this command fails, try using disk instead of rdisk:
```
sudo dd bs=1m if=path_of_your_image.img of=/dev/diskn conv=sync
```

   This will take a few minutes, depending on the size of the image file. To check the progress, open Activity Monitor, click the Disk tab and find the process with the name dd. If dd is not in the list, you may need to select 'All Processes' from the View menu. The Bytes Read column will display the amount of data that has been read from the image. Compare that to the file size of the image to determine progress.
