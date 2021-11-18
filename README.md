# Ubuntu Server 20.04 on Raspberry Pi 4
A reference to consistently initialize a Raspberry Pi 4 to run Ubuntu Server 20.04 LTS (64-bit)

## Image and config:
Using rpi-imager, write Ubuntu 20.04.3 (64-bit) to SD card (DO NOT use custom settings via Ctrl+Shift+X)

Copy (overwrite) "network-config" to SD

Copy (overwrite) "user-data" to SD

Insert SD and boot RPi4

## After first boot and restart:

### Headless:
(To do notes: We will probably touch ssh in config and enable it before first boot. Ideally this will just add two steps to the setup, being touch and ssh)

(We will also probably want to setup users promptly, ssh into that username, verify we have root, and disable root ssh access)

(Read up on auth-only ssh; pros: very strong, major con: can't remotely login from a new computer without the ssh key... Will depend on the usage of the server)

ssh into the rpi4 via hostname@IP address (LAN)
  ```
  ssh hostname@255.255.255.255
  ```

### With display and keyboard:
Login and change root password
  ```
  ubuntu login: ubuntu
  Password: ubuntu
  ```
Update apt and upgrade currently installed packages
  ```  
  sudo apt update
  sudo apt upgrade
  reboot
  ```

### Add groups and users
It is best practice to use users and groups to be able to track who does what, and restrict who does what, respectively. 
Logging in as root is ill advised for many more reasons.

#### To add/delete a group:
```
sudo addgroup groupname
sudo delgroup groupname
```
  
#### To add/delete a user:
```
sudo adduser username [groupname]
sudo deluser username
```
  
When a new user is created, the adduser utility creates a brand new home directory named /home/username. The default profile is modeled after the contents found  in the directory of /etc/skel, which includes all profile basics.

If your server will be home to multiple users, you should pay close attention to the user home directory permissions to ensure confidentiality. By default, user home directories in Ubuntu are created with world read/execute permissions. This means that all users can browse and access the contents of other users home directories. This may not be suitable for your environment.    

More To Do:
- [ ] Add headless config
- [ ] Set static IP
- [ ] ssh key-based authentication
- [X] Add users
- [ ] Add firewall
- [ ] Open port to internet
