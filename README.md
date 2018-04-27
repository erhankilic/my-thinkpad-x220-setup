# my-thinkpad-x220-setup
Setup for my thinkpad x220 after new OS installation

1) Install lm-sensors with the following command

```sudo apt-get install lm-sensors```

2) Install thinkfan with the following command

```sudo apt-get install thinkfan```

3) Enable fan control

```sudo systemctl enable thinkfan.service```

4) Add the following lines to enable the proper sensors in the X220:

"tp_fan /proc/acpi/ibm/fan

hwmon /sys/class/thermal/thermal_zone0/temp"

```sudo nano -w /etc/thinkfan.conf```

5) See sensor readings with the following command:

```sensors```

6) Install TLP for better battery optimization

```
sudo add-apt-repository ppa:linrunner/tlp
sudo apt-get update
sudo apt-get install tlp tlp-rdw
```
