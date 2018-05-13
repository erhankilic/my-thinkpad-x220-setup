# my-thinkpad-x220-setup
Setup for my thinkpad x220 after new OS installation

### 1) Install lm-sensors with the following command

```sudo apt-get install lm-sensors```

### 2) Install thinkfan with the following command

```sudo apt-get install thinkfan```

### 3) Create this file

```sudo nano /etc/modprobe.d/thinkfan.conf```

### 4) Add this line to /etc/modprobe.d/thinkfan.conf

```options thinkpad_acpi fan_control=1```

### 5) Activate the command

```modprobe thinkpad_acpi```

### 6) Edit default thinkfan

```nano -w /etc/default/thinkfan```

### 7) Make START to yes. If it isn't exist, add.

```START=yes```

### 8) Enable fan control

```sudo systemctl enable thinkfan.service```

### 9) Add the following lines to enable the proper sensors in the X220:

"tp_fan /proc/acpi/ibm/fan

hwmon /sys/class/thermal/thermal_zone0/temp"

```sudo nano -w /etc/thinkfan.conf```

My fan config: 

```
(0,     0,      40)
(1,     40,     60)
(2,     60,     65)
(3,     65,     70)
(4,     70,     75)
(5,     75,     80)
(7,     80,     32767)
```


### 10) See sensor readings with the following command:

```sensors```

### 11) Install TLP for better battery optimization

```
sudo add-apt-repository ppa:linrunner/tlp
sudo apt-get update
sudo apt-get install tlp tlp-rdw tp-smapi-dkms acpi-call-dkms 
```
