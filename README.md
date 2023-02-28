# MoodeAudio-IR
MoodeAudio IR Setup


Step 1: Install lirc
<pre><code>
$ sudo apt-get update
$ sudo apt-get install lirc
</code></pre>

Step 2: Edit lirc_options.conf
Edit /etc/lirc/lirc_options.conf as follows by changing these two lines:
<pre><code>
$ sudo nano /etc/lirc/lirc_options.conf
:
driver = default
device = /dev/lirc0
:
</code></pre>

Step 3: Edit /boot/config.txt
Edit /boot/config.txt as follows:
<pre><code>
sudo nano /boot/config.txt
:
dtoverlay=gpio-ir,gpio_pin=27
:
</code></pre>

Step 4: Copy lircd.conf and irexec.lircrc
<pre><code>
$ sudo cp irexec.lircrc /etc/lirc/
$ sudo cp lircd.conf /etc/lirc/
</code></pre>

Step 5: Start IR service
<pre><code>
$ sudo systemctl start lircd.service
$ sudo systemctl start irexec.service
</code></pre>
