# jetson nano oled
----
This repo is based on work found in website:   
https://custom-build-robots.com/top-story-en/jetson-nano-oled-display-ssd1306/12124?lang=en#prettyPhoto
----
## installation
### library
<code> git clone https://github.com/adafruit/Adafruit_Python_SSD1306.git

<code> cd Adafruit_Python_SSD1306

<code> sudo python setup.py install


### user to i2c group
<code> sudo usermod -aG i2c <username>

<code> sudo reboot

test that i2c works, and oled is connected(3c)

<code> sudo i2cdetect -y -r 1

----
## Autorun script 
With a cron we can run script automaticly at reboot

gitclone tonaalt/oled or download from links, and unzip.


<code> sudo cp -i ~/oled/stats.py /bin/stats.py

<code> sudo crontab -e

add this as last line:

<code> @reboot python /bin/your_script.py &

<code> sudo reboot