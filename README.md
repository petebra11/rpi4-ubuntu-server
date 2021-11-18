# rpi4-ubuntu-server
Initialize a Raspberry Pi 4 to run Ubuntu Server 20.04 LTS (64-bit)

## Image and config:
  - rpi-imager write Ubuntu 20.04.3 (64-bit) to SD card (DO NOT use custom settings via Ctrl+Shift+X)
  - Copy (overwrite) "network-config" to SD image
  - Copy (overwrite) "user-data" to SD image
  - Insert SD and boot RPi4

## After first boot and restart:

  ### With display and keyboard:
  - Login using ubuntu:ubuntu and change root password
  - sudo apt update
  - sudo apt upgrade
  - reboot

### Add groups and users
    It is best practice to use users and groups to be able to track who does what, and restrict who does what, respectively. 
    Logging in as root is ill advised for many more reasons.
  - To add a group, sudo addgroup groupname
    - To delete a group, sudo delgroup groupname
  - To add a user, sudo adduser username
    - To add a user to a group, sudo adduser username groupname
    - To delete a user, sudo deluser username

  ### Headless:

More To Do:
  - [ ] Add headless config
  - [ ] Set static IP
  - [ ] ssh key-based authentication
  - [X] Add users
  - [ ] Add firewall
  - [ ] Open port to internet
