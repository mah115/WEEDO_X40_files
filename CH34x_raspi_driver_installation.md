# How to install the patched CH34x driver

```
sudo apt-get install raspberrypi-kernel-headers
sudo reboot

#after rebooting
sudo apt-get update
sudo apt-get upgrade

git clone https://github.com/juliagoda/CH341SER.git
cd CH341SER/
make clean
make

#if you get error "/lib/modules/4.14.50-v7+/build: No such file or directory.", then
#run
#	sudo apt-get update && sudo apt-get install --reinstall raspberrypi-bootloader raspberrypi-kernel
#and try again


#load new driver
sudo make load

#unload old driver
sudo rmmod ch341

#copy new driver into driver folder
sudo cp ch34x.ko /usr/lib/modules/$(uname -r)/kernel/drivers/usb/serial 

#delete old driver
sudo rm /usr/lib/modules/$(uname -r)/kernel/drivers/usb/serial/ch341.ko

#rebuild dependency tree
sudo depmod
```
