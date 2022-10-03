

# pour sauvegarer l'image de la flash

https://opensource.com/article/21/7/custom-raspberry-pi-image

## copy from la flash

- shut down your Raspberry Pi, take out the SD card, and connect it to your PC. Check if your system has automatically mounted the partitions on the SD card by typing lsblk -p

- umount /dev/sdc1 && umount /dev/sdc2

- dd if=/dev/sdc of=~/MyImage.img bs=32M

- Once the copy process is finished, we can shrink the image with the PiShrink. Follow the installation instructions mentioned in the repository which are:

wget https://raw.githubusercontent.com/Drewsif/PiShrink/master/pishrink.sh
chmod +x pishrink.sh
sudo mv pishrink.sh /usr/local/bin

sudo pishrink.sh ~/MyImage.img

## Flashing the image

If you want to flash your own custom Raspberry Pi image back to the SD card using Linux, follow the steps below.

Put the SD card into your PC. Your system will likely automatically mount the filesystem on the SD card if there is already a previous installation. You can check this by opening a command line and typing lsblk -p

As you can see in the screenshot above, my system automatically mounted two filesystems, boot and rootfs as this SD card already contained a Raspberry Pi OS. Before we start flashing the SD card we have to unmount the file systems first by typing:

umount /dev/sdc1 && umount /dev/sdc2

The output of lsblk -p should look like this in order to proceed

Now you can flash the image to the SD card: Open a command line and type:

dd if=/path/to/image.img of=/dev/sdc bs=32M, conv=fsync

With bs=32M, you specify that the SD card is written in 32-megabyte blocks, conv=fsync forces the process to physically write each block.




# raspbot

code in java for a robot made of a raspberry + 2 wheels

$1/2$

# le hat pour controller les moteurs

https://learn.adafruit.com/adafruit-dc-and-stepper-motor-hat-for-raspberry-pi

"Only two GPIO pins (SDA & SCL) are required to drive the multiple motors, and since it's I2C you can also connect any other I2C devices or HATs to the same pins."


[ images/raspberry_pi_2348_top_ORIG.jpg ]

Pinout

[ images/raspberry_pi_2348_top_ORIG.jpg ]




