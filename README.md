# RPI_Audio
Resources for the local CASE Audio system.
### Installation
```
sudo apt-get update
#sudo apt-get install -y python-dev python-pip libfreetype6-dev libjpeg-dev build-essential python-rpi.gpio
sudo pip install --upgrade setuptools pip wheel
sudo pip install --upgrade socketIO-client-2
sudo apt-get install rpi.gpio -y
git clone https://github.com/Stefanlarsson95/RPI_Audio
chmod +x ~/CASE_DSP/AudioSupervisor.py
sudo cp ~/CASE_DSP/AudioSupervisor.service /lib/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable AudioSupervisor.service
sudo dpkg-reconfigure tzdata
reboot
```
#
For programming the ADA1701 DPS the I2C channel 0 is used. To enable this in Volumio add
the following to /boot/config.txt

```shell script
dtparam=i2c_vc=on
```




Creator: Stefan Larsson 2019