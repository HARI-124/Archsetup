# Required tools to install
bluetoothcl, bluez, bluez-utils,btusb,

# now eable and start bluetooth service

`sudo systemctl enable bluetooth.service`

`sudo systemctl start bluetooth.service`


# Using bluetoothctl
- now run `bluetoothctl power on`
- now run `bluetoothctl discoverableon`    
- now run `bluetoothctl pairable on`

# Listing the device controllers

Run `bluetoothctl list`


# Scanning for devices

`bluetoothctl scan on` 
`bluetoothctl devices`


# Use the mac address from above and connect it here

`bluetoothctl pair MAC ADDRRESS`

- The device will be connected after this


