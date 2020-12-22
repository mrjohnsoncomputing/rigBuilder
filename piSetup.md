### OS
Pi installed with GUI Debian through N00bs - NO APPS

### Config
password changed for better security

* Default User: pi
* Default Password: raspberry

To change password and enable ssh:
```console
sudo raspi-config
```
Windows command for access:
```console
ssh pi@<ip>
```

#### GUI Preferences > Raspberry Pi Configuration
Set Network at Boot to "Wait for Network"

### Package Management
```console 
sudo apt-get update && sudo apt-get upgrade
```

### Software Installation
```console
sudo apt-get install git && sudo apt-get install wiringpi
```

### Python Preparation
```bash
sudo apt-get install python3 && sudo apt-get install python3-dev python3-pip
```

#### ESC-POS Library
```console
sudo apt-get install libjpeg-dev zlib1g-dev
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade pillow
sudo pip3 install python-escpos
```

#### RFID Libraries
##### PN532
```console
python3 -m pip install --upgrade adafruit-circuitpython-pn532
pip3 install adafruit-circuitpython-lis3dh
```

##### MFRC522
```bash
sudo pip3 install spidev && sudo pip3 install mfrc522
```

#### LED Libraries
```console
sudo apt-get install python-rpi.gpio python3-rpi.gpio
```
#### LCD Libraries
```console
sudo pip3 install adafruit-blinka
sudo pip3 install adafruit-circuitpython-charlcd
```

### Interface setup
To enable spi:
```console
sudo raspi-config
```
Found in *interfaces*

Check spi:
```console
lsmod | grep spi
```
Passes if **spi_bcm2835** is listed

### Directory Setup
```console
mkdir projects && cd projects && 
```

### git Setup
```console
git clone https://github.com/mrjohnsoncomputing/lotteryprinter.git
git checkout -b <new branch name>
```
