# im-so-board

## Introduction
Instructions, sketches, and server code for introductory IoT projects.

## Board Setup
### Intel Edison Kit for Arduino
These steps will help you get your Intel Edison Kit for Arduino board up, running, and ready for code deploy! This is excellently covered [here](http://codefoster.com/edison-setup) by [CodeFoster](https://github.com/codefoster)

1. Flash your Edison
  * [Windows](http://www.intel.com/support/edison/sb/CS-035286.htm)
  * [Mac](http://www.intel.com/support/edison/sb/CS-035262.htm)
  * [Linux](http://www.intel.com/support/edison/sb/CS-035280.htm)

0. Connect through serial

At this point, you really should power your board through a power-only source (i.e. a charger connected to the inner micro USB slot, or use the Arduino barrel plug to power your board).  This will help you distinguish between what you need a power connection for, what you need computer-board USB connection for, what you need a serial connection for, and what you can do wirelessly.
  * Connect your computer to the outer micro USB slot on your board.
  * Find the serial device name: ls /dev/cu.usbserial* (use this name in the next step) (you can totally just use educated tab-completion in the next step)
  * Mac/Linux: screen -L /dev/cu.usbserial-XXXXXXX 115200 -L (where XXXXXXX is your serial device name)
  * Hit enter (once or twice should do it) You will see something similar to this
```
Poky (Yocto Project Reference Distro) 1.7.2 Edison ttyMFD2

Edison login: 
```

  * If this is your first time connecting, the username is root, and if prompted for the password, just press Enter.  If you've set the password for the root user, you'll need to remember it. If you've forgotten it, [I just saved you a Google search](http://www.intel.com/support/edison/sb/CS-035185.htm)
  * To initiate the flash of the board, type ```reboot ota```
  * Watch it do a bunch of stuff (or go get some coffee) and you'll arrive back at the login prompt. Login.
  * Run ```configure_edison --setup```
  * Walk through the setup instructions.  You will be asked to set a password (make this at least 8 characters in order to set up SSL later), and set up wifi.
  * Once you've connected to a wifi network, you should be able to open a web browser and navigate to your board, either through your board's name (i.e. myedison.local) or through the IP address shown when your board successfully connects to the wifi network.
 