configuration files for lirc remotes
to setup lirc, follow these steps:

```
sudo apt-get install lirc
```

Modify modules with the appropiate pin number

```
sudo nano /etc/modules
```

Add the following lines:

```
lirc_dev
lirc_rpi gpio_in_pin=23 gpio_out_pin=22
```

Open the following file

```
sudo nano /etc/lirc/hardware.conf
```

Make the following modifications

```
LIRCD_ARGS="--uinput"
DRIVER="default"
DEVICE="/dev/lirc0"
MODULES="lirc_rpi"
```
