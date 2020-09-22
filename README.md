# jetson nano oled
----
This repo is based on work found in website:   
https://custom-build-robots.com/top-story-en/jetson-nano-oled-display-ssd1306/12124?lang=en#prettyPhoto
----
## installation
### library
<code> git clone https://github.com/adafruit/Adafruit_Python_SSD1306.git</code>

<code> cd Adafruit_Python_SSD1306</code>

<code> sudo python setup.py install</code>


### user to i2c group
<code> sudo usermod -aG i2c <username></code>

<code> sudo reboot</code>

test that i2c works, and oled is connected(3c)

<code> sudo i2cdetect -y -r 1</code>

----
## Autorun script 
With a cron we can run script automaticly at reboot

gitclone tonaalt/oled or download from links, and unzip.


<code> sudo cp -i ~/oled/stats.py /bin/stats.py</code>

<code> sudo crontab -e</code>

add this as last line:

<code> @reboot python /bin/your_script.py &</code>
The reboot machine, and everything should work.

<code> sudo reboot</code>