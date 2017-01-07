Andy's Amazing Weather Clock. 2017 01 06

The folder ascii is full of ascii art that the clock will display above the time and weather.  Randomly selected.

The command to run python3 and start it is in /home/pi/.bash_profile:
clear
cd clock
python3 clockweather.py


Had to edit the /boot/config.txt to get the screen full width.
Not sure why there is a purple bar on the left.
TODO: Add config.txt data

To get the pi to update the clock on startup:
apt-get install ntpdate 

then to set New York as the timezone:
sudo dpkg-reconfigure tzdata

Python 3 was already installed.

Needed to install pyfiglet


to keep screen from blanking edited /etc/kbd/config
BLANK_TIME=0
# DID NOT WORK

and .bashrc
setterm -blank 0 -powerdown 0
# THIS DIDN"T WORK EITHER  UGH

# THIS WORKED
edit /boot/cmdline.txt
added to the end of the first line:
consoleblank=0


