# MoodeAudio-IR
MoodeAudio IR Setup


Step 1: Install lirc

$ sudo apt-get update
$ sudo apt-get install lirc

Step 2: Edit lirc_options.conf
Edit /etc/lirc/lirc_options.conf as follows by changing these two lines:

sudo nano /etc/lirc/lirc_options.conf
:
driver = default
device = /dev/lirc0
:

Step 3: Edit /boot/config.txt
Edit /boot/config.txt as follows:

sudo nano /boot/config.txt
:
dtoverlay=gpio-ir,gpio_pin=27
:

Step 4: Copy lircd.conf and irexec.lircrc

sudo cp irexec.lircrc /etc/lirc/
sudo cp lircd.conf /etc/lirc/

Step 5: Start IR service

sudo systemctl start lircd.service
sudo systemctl start irexec.service
