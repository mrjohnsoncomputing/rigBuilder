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

### Git SSH
Source: https://www.freecodecamp.org/news/git-ssh-how-to/
Check for an existing SSH key
First, check if you've already generated SSH keys for your machine. Open a terminal and enter the following command:

ls -al ~/.ssh
If you've already generated SSH keys, you should see output similar to this:

-rw-------  1 user_name user_name  1766 Jul  7  2018 id_rsa
-rw-r--r--  1 user_name user_name   414 Jul  7  2018 id_rsa.pub
-rw-------  1 user_name user_name 12892 Feb  5 18:39 known_hosts
If your keys already exist, skip ahead to the Copy your public SSH key section below.

If you don't see any output or that directory doesn't exist (you get a No such file or directory message), then run:

mkdir $HOME/.ssh
Then generate a new set of keys with:

ssh-keygen -t rsa -b 4096 -C your@email.com
Now check that your keys exist with the ls -al ~/.ssh command and ensure that the output is similar to the one listed above.

Note: SSH keys are always generated as a pair of public (id_rsa.pub) and private (id_rsa) keys. It's extremely important that you never reveal your private key, and only use your public key for things like GitHub authentication. You can read more about how SSH / RSA key pairs work here.

Add your SSH key to ssh-agent
ssh-agent is a program that starts when you log in and stores your private keys. For it to work properly, it needs to be running and have a copy of your private key.

First, make sure that ssh-agent is running with:

eval "$(ssh-agent -s)" # for Mac and Linux
or:

eval `ssh-agent -s`
ssh-agent -s # for Windows
Then, add your private key to ssh-agent with:

ssh-add ~/.ssh/id_rsa
Copy your public SSH key
Next, you need to copy your public SSH key to the clipboard.

For Linux or Mac, print the contents of your public key to the console with:

cat ~/.ssh/id_rsa.pub # Linux
Then highlight and copy the output.

Or for Windows, simply run:

clip < ~/.ssh/id_rsa.pub # Windows
Add your public SSH key to GitHub
Go to your GitHub settings page and click the "New SSH key" button:


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
