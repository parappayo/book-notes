# About

[Raspberry Pi Cookbook](http://razzpisampler.oreilly.com/)
by Simon Monk
published by O'Reilly Media, 2013

# Thoughts

Great entry level book with a broad overview of helpful hobbyist topics.

# Take-Aways

* Difference between the RPI and Arduino is that the former is more of a microcomputer and the latter is more of a microcontroller; Arduino provides more power to peripherals, easier to attach sensors and drive servos, but sacrifices much compute power
* Use Python 3 when you can, Python 2 when you have to


# Concepts

* Overclocking - bumping the original RPI from 700 mHZ to 1 GHz is a noticeable performance boost but will run hotter
* Comprehensions - Python feature, iterable map from a given iterable
* iterable - Python object that has `__iter__`
* Template Strings - PEP-292, a way of formatting strings


# Techs

* 5V DC - standard power for a Pi; amps drawn depends on peripherals; consider 700mA as a reasonable minimum, but 1.5A or more is good; only the power drawn by the Pi is consumed, so getting a larger PS will not increase your electrical bill; it is possible to get power supplies that turns off when your Pi shuts down
* `/boot/config.txt` - has framebuffer_width and framebuffer_height, useful to force a screen resolution setting (eg. change from 720p to 320 by 240 for composite video displays), tweak overscan setting
* `/etc/hostname` - config file to setup hostname
* `/etc/network/interfaces` - config file to set up a static IP
* `/etc/rc.local` - can add start-up commands, but be careful or your RPI may not start
* `apt-get autoremove` - uninstall software, will cascade dependencies
* `crontab -e` - opens crontab for editing
* `df` - cli disk usage, see also `du`
* `fg` - bring background process (eg. started with `&`) to the foreground; see also `nohup`
* `find` - cli search for file, see also `which`
* `gunzip` - unzip files
* `hostname -I` - command to get host local IP
* `ifconfig` - command to see all of the host's network connections
* `os.system()` - Python method to run a system shell command
* AbiWord - word processor
* avahi-daemon - apt package, needed for Mac Finder integration; RFB service option allows screen sharing from Mac
* bluetooth, bluez-utils, blueman, bluez - Raspbian packages for working with a USB Bluetooth dongle
* Bottle - pip package, Python web server
* Chromium - web browser, alternative to Chrome
* Common Unix Printing System (CUPS) - service to connect to printers
* Console Cable - option to connect headless RPI without a network connection, provides power to the RPI and a serial connection over USB; Windows requires custom driver (SIO (Smart-IO)  > USB to UART/Serial/Printer  > PL2303 Driver), use Putty to open a Serial connection with speed 115200; on Mac, need to open the connection on /dev/cu
* Dynamic Host Configuration Protocol (DHCP) - how computers typically get assigned an IP
* GIMP - Gnu Image Manipulation Program
* Heat Sinks - aluminum sinks on a Pi are like the "go faster" stripes on a car
* Iceweasel - web browser, alternative to Firefox
* Kodi - media center software, based on XMBC
* Libre Office - FOSS productivity software
* lsusb - cli to list USB devices
* LXTerminal - terminal app for LXDE
* microSD Card Images - beware the difference between a partition image and a disk image when writing
* Midori - lightweight web browser
* Minecraft Pi - port of Minecraft, has Python interop, requires openjdk-7-jdk
* motion - apt package, webcam motion detection tool
* netatalk - apt package, add AFP protocol, host will appear in Mac Finder
* Network Attached Storage (NAS) - option for file sharing with Windows
* No-IP - dynamic DNS service, useful for people to register a domain name with their home IP, follows IP changes
* NOOBS - new out of the box software, microSD card image that makes installing common OS options easy for new Pi setup; requires FAT32 file system
* Open Arena - Quake clone
* OpenELEC - media center distro
* Pi Store - app store for RPI
* Pi-View - official HDMI converter
* PiBow Coupe - enclosure, protects the pins on the underside of the RPI board from shorting
* pickle - Python lib to serialize objects as plaintext
* pifm - send FM radio signal using GPIO pin 4 (attach wire for short-range transmission), Imperial College project
* Pre Shared Key (PSK) - WiFi auth method
* Raspberry Pi (RPI) - launched in 2011, sold millions, there are several models and revisions
* raspi-config - cli tool to modify settings; can change overclocking, ssh, I2C, etc.
* raspstill, raspivid - cli tools that work with the RPI camera
* RealVNC - VNC client, available for Windows
* Remote Desktop Protocol (RDP)
* RJ45 Socket - Ethernet socket on the RPI
* Samba - service that supports NAS; smbpasswd and smbmount commands
* samba-common-bin - support apt package
* Screen Share - Mac OSX feature, does not integrate with RDP, may work with VNC
* scrot - screen capture cli
* smtplib - Python lib to talk with SMTP server; eg. `smtp.gmail.com` port 587 will accept requests if given a valid login
* Spigot - Minecraft server
* SSID - WiFi connection point name
* Stella - Atari 2600 emulator, also code name for the Atari 2600 platform
* strftime - Unix lib to format datetime, also in Python
* subprocess - Python lib to run shell command and get its output
* svgwrite - pip package
* tightvncserver - apt package, VNC server
* VESA Mountable Enclosure - designed to be attached to the backside of a TV
* Virtual Network Computing (VNC) - desktop sharing system, uses Remote Frame Buffer (RFB) protocol
* wget - like curl cli
* wpa_supplicant - WiFi service
* xrdp - apt package, RDP server
/etc/init.d/ - where service start and stop scripts live, can add your own here; use update-rc.d to register your service with the system

# Publications

* [eLinux article on converting HDMI to eVGA](https://elinux.org/RPi_VerifiedPeripherals#HDMI-.3EVGA_converter_boxes)
* Getting Started with Raspberry Pi - Matt Richardson, Shawn Wallace book

# Names Dropped

* Simon Monk - proprietor of MonkMakes.com
* Adafruit - popular Pi vendor

# Code

* `cp -r` - copy has a recursive option
* `alias rm='rm -i'` - add to `~/.bashrc` to make rm prompt by default; can mess you up if you switch to another environment though
* `input()` - Python method to read user input
* `list.extend()` - Python method to append a list
* `range()` - Python method to create an iterable sequence
