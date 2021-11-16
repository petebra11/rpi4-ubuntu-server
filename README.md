# rpi4-ubuntu-server
Initialize a Raspberry Pi 4 to run Ubuntu Server 20.04 LTS (64-bit)

### Image and config:
  - rpi-imager write Ubuntu 20.04.3 (64-bit) to SD card (DO NOT use custom settings via Ctrl+Shift+X)
  - Copy (overwrite) "network-config" to SD image
  - Copy (overwrite) "user-data" to SD image
  - Insert SD and boot RPi4

### After first boot and restart:

  #### (With display attached):
  - Login using ubuntu:ubuntu and change root password
  - sudo apt update
  - sudo apt upgrade
  - reboot

  #### Headless:

More To Do:
  - [ ] Add headless config
  - [ ] Set static IP
  - [ ] ssh key-based authentication
  - [ ] Add users
  - [ ] Add firewall
  - [ ] Open port to internet
