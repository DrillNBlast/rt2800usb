# rt2800 (*rt2800usb*)
## Summary
This is the driver for rt2800. The version in Linux is extremely unstable, and also uses some functions which are incompatible with Linux 3.0.8 or above. This is a fork of a third party driver which should fix these problems.
## Installation
Make sure you have superuser rights before you run these commands (either prefix with `sudo`, run `su`, or login as root)

1. Blacklist the driver in the kernel.
    Edit `/etc/modprobe.d` using your favorite editor and add `blacklist rt2800usb` on a new line at the end.

2. Copy `RT2870STA.dat` to `/etc`
    Create the path `/etc/Wireless/RT2870STA` by running `mkdir /etc/Wireless/RT2870STA`.
    Copy over to the directory: `cp RT2870STA.dat /etc/Wireless/RT2870STA/RT2870STA.dat`.

3. Compile the Driver
    Run `make`.

4. Load Driver
    `cd` into the `tftpboot` directory (in your driver). Load the driver by running `insmod rt3070sta.ko` and `ifconfig ra0 inet up`

5. Unload Driver
    Put the interface down: `ifconfig ra0 inet down`; remove the driver ` rmmod rt3070sta.ko`.

