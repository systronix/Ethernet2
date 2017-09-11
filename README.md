# Ethernet2
* This is a fork of the Adafruit [Ethernet 2 library](https://github.com/adafruit/Ethernet2)
* This library supports the [WIZ85io module] http://www.wiznet.co.kr/product-item/wiz850io/) and W5500 chip

This Arduino library is for shields that use the **Wiznet [W5500]** chipset only.
It does **not** work with other chipsets, such as the original Arduino Ethernet shield which
uses the Wiznet [W5100] chipset.

For some documentation on the functions in this library, see 
http://www.arduino.cc/en/Reference/Ethernet
but note that this is **note** the Arduino Ethernet library. It just supports many of the same functions.

## Changes to this Systronix Fork
Several enhancements have been added to make this library more useful.
- Read of remote IP address. Know who is trying to connect to your system. This seems like such an obvious need but it's not in the Arduino library.
- Read remote IP port
- Read status of each socket

### EthernetClient.cpp
#### IPAddress EthernetClient::remoteIP()
return remote IP address of current socket
#### IPAddress EthernetClient::remoteIP(uint8_t socket)
return remote IP address of a specific socket
#### uint16_t EthernetClient::remotePort()
return remote port of current socket

### Ethernet2.cpp
Socket status for all 8 supported sockets. This is helpful for debugging, for example, am I about to run out of sockets? If so, why? Do I have zombie sockets in a persistent close-wait state?
#### static void printSocketStatusX(uint8_t); 
print any one socket status 
####  static void printSocketStatus(uint8_t); 
print one or more socket status starting with [0]

Output can look like this:
	Socket(1) SnSr=Establ SnMR=TCP IP=192.168.1.1 Port=52645 MAC=20:CF:30:B8:3D:ED


## Example Programs
Lots of examples using this library, many tested 24/7 for months (as of 2017 Sep), with some documentation and an attempt at useful comments in the code

## W5500 Shields
* [Adafruit W5500 Ethernet Shield](https://www.adafruit.com/products/2971)
* [Arduino Ethernet Shield v2](https://www.arduino.cc/en/Main/ArduinoEthernetShieldV2)
* [Industruino Ethernet module](https://industruino.com/shop/product/ethernet-expansion-module-10)
* [Wiznet W5500 Ethernet Shield](http://www.wiznet.co.kr/product-item/w5500-ethernet-shield/)


### Authors
- modified 12 Aug 2013 by Soohwan Kim (suhwan@wiznet.co.kr)

- 10 Apr 2015 Added support for Arduino Ethernet Shield 2  by Arduino.org team

- 2017 Aug bboyes, Systronix. See commit comments in https://github.com/systronix/Ethernet2

### License
Copyright (c) 2009-2016 Arduino LLC. All right reserved.

This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Lesser General Public
License as published by the Free Software Foundation; either
version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public
License along with this library; if not, write to the Free Software
Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA

