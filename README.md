# rpi-headless-setup

# Step 1. Download/Install Raspberry Pi Imager
* [Raspberry Pi Software](https://www.raspberrypi.org/software/)

# Step 2. Run Raspberry Pi Imager
1. Click Choose OS
2. Click Raspberry Pi OS (Other)
3. Select Raspberry Pi OS Lite (32 bit)
4. Click Choose SD Card
5. Select your SD Card
6. Click Write

# Step 3. Enable SSH and Add Network Info
* Using VSCode or Bash
1. Create a file named "ssh" in the root directory of the drive
```
  touch /Volumes/boot/ssh
``` 
2. Create a file named "wpa_supplicant.conf" in the root directory of the drive
3. Add the following content to that file, substitute your network information in the indicated spots
```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="NETWORK-NAME"
    psk="NETWORK-PASSWORD"
}
```

# Step 4. Boot the Raspberry Pi
1. Eject the SD card from your computer and install it in the Raspberry Pi
2. Power on the Raspberry Pi using a micro-USB power cable

# Step 5. Run Putty
1. If you don't have Putty, download it from [Putty](https://www.putty.org/)

# Step 5. Login Over Wifi
1. Wait up to 90 seconds for the Raspberry Pi to boot
2. In Putty:
* Set Host Name to: raspberrypi.local
* Set port to 22 (should be default)
* Set connection type to SSH
* Click Open
* Click Yes on security alert, if it pops-up
* default username/password is pi/raspberry

# Step 6. Change Username/Password
1. Type:
```
sudo raspi-config
```
2. Select the options for changing the hostname and password.
* Note: The username will still be "pi"
* Note: You will need to change your Putty connection to "hostname.local" next time you connect

# Step 7. Update the Raspberry Pi
1. Type:
```
sudo apt-get update -y
```


