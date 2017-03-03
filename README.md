# Raspberry-Pi-App-without-desktop-environment
This is tutorial on how to set up Raspbian lite to run a single window app on startup, without any need of full fledge desktop environement

First of all, you need to burn the raspbian lite image that is availabe on the official download page. 

After that setup wifi and ssh accordingly.

Now execute the script or manually enter the commands in the following order.

```bash
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install matchbox xorg x11-xserver-utils ttf-mscorefonts-installer xwit sqlite3 libnss3
```

```bash
sudo nano /etc/rc.local
```
and add this line before the exit command

```bash
startx &
```

now save the file, and edit this file
```bash
sudo nano /etc/X11/xinit/xinitrc
```

remove all content and add 
```bash
while true; do

xset -dpms
xset s off
matchbox-window-manager &
galculator (replace with the program of your choice)

done;
```
That it..

