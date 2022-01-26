![dwm.png](dwm.png)
# dwm - dynamic window manager
---
dwm is an extremely fast, small, and dynamic window manager for X.

## Patches
---
The installed patches currently are listed in the patches directory

## Requirements
---
In order to build dwm you need:
 - Xlib header files
 - xcompmgr
 - xrandr
 - xinerama

## Installation
---
1. clone this repository with git
2. cd into the cloned repo
3. edit config.mk to match your local setup (dwm is installed into the /usr/local namespace by default).
4. run `make clean install` (you might need root privilages)

## Running dwm
Add the following line to your .xinitrc to start dwm using startx:
```sh
exec dwm
```

In order to connect dwm to a specific display, make sure that the DISPLAY environment variable is set correctly, e.g.:
```sh
DISPLAY=foo.bar:1 exec dwm
```
(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something like this in your .xinitrc:
```sh
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
	sleep 1
done &
exec dwm
```

## Configuration
---
The configuration of dwm is done by creating a custom config.h and (re)compiling the source code.
In this version, use config.def.h because `make clean` will remove and recreate config.h
