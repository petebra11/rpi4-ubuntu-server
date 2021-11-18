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
  - Run command sudo apt update
  - Run command sudo apt upgrade
  - reboot
 ##### Add groups and users
  (It is best practice to use users and groups to be able to track who does what, and restrict who does what, respectively. Logging in as root is ill advised for many more reasons.)
  - Run command sudo addgroup <groupname>
    - To delete a group, run command sudo delgroup groupname
  - Run command sudo adduser <username>
    - To delete a user, run command sudo deluser <username>

  #### Headless:

More To Do:
  - [ ] Add headless config
  - [ ] Set static IP
  - [ ] ssh key-based authentication
  - [ ] Add users
  - [ ] Add firewall
  - [ ] Open port to internet
