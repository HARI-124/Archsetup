# Guide for connevting to network in arch cli

`run iwctl`
In the cli run 

- Now the iwctl mode will be running now type  `device list` the wifi adapters will be listed.
- Now run `station DEVICE NAME scan` the device name is the device listed from the above example for me it was `wlan0`. This command will scan for networks.
- Now run `station DEVICE NAME get-networks` to get all the nearby wifi networks.
- Now run `station DEVICE NAME coonect NETWORK NAME` just type the starting networks and press tab to get autocompletion.
- after sucessful connection check whether network is working or not by running `ping google.com`

After connecting with iwctl we need to configure iwctl to network manager to get the connection.

# Install NetworkManager and any other text editor while installing Arch  

## After sucessful installation of Arch

- Now create the following file with your preferred text editor

- I will use neovim here: 
- run `sudo nvim /etc/NetworkManager/conf.d/iwd.conf` This will create iwd.conf if not exists and edit it as follows

```conf
[device]
wifi.backend=iwd

```
- After editing run `:wq` to close it and restart NetworkManager after disabling wpa_supplicant with the following commands

```
sudo systemctl stop NetworkManager
sudo systemctl disable --now wpa_supplicant
sudo systemctl restart NetworkManager

```
After this your wifi internet connection will work perfectly

check it using ping google.com if it is not working you need to connect again

I will prefer `nmtui` for connecting

run nmtui in terminal it will open a TUI and edit and setup your connection it will work

# References
- [Debian wiki](https://wiki.debian.org/NetworkManager/iwd)





