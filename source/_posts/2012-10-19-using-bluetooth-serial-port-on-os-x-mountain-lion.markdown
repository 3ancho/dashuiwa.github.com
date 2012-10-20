---
layout: post
title: "Using Bluetooth Serial Port on OS X Mountain Lion"
date: 2012-10-19 00:38
comments: true
categories: arduino, python
---
#### Using Bluetooth Serial Port on OS X Mountain Lion

I am taking a robotics class, and simply wants to play with the bluetooth module. Maybe create a robot later to play with my cats?

#### Procedures


* Find the bluetooth, the name of device is AC, for some unknown reason.

{% /images/bluetooth/find %}

* Pair with it, the pairing code is 0000 in my case.

{% /images/bluetooth/pair %}

* The underlined part have some config to play with. The general idea is to use serial port service.

{% /images/bluetooth/config %}

* `Serial.println()` in arduino will write data to the pin1 (TX) and also to the USB cable. So you could compare your data received via bluetooth serial port with the data received via USB serial port. My usb serial port is `/dev/tty/usbmodemfa131`.  

{% /images/bluetooth/arduino %}

* The image below shows the display while using GNU `screen`

{% /images/bluetooth/result %}


#### Using screen

The number after the device name is the baud rate, which need to be the same as source.
```
screen tty.AC-DevB 9600
```

#### Using PySerial

```
In [2]: s = serial.Serial('/dev/tty.AC-DevB', 9600, timeout=1)

In [3]: s.write("r")
Out[3]: 1

In [4]: s.read()
Out[4]: 'N'

In [5]: s.read()
Out[5]: 'i'

In [6]: s.read()
Out[6]: 'n'

In [7]: s.read()
Out[7]: 'a'

In [8]: s.read(10)
Out[8]: '\r\n'

In [9]: s.read(10)
Out[9]: ''

In [10]: s.write("r")
Out[10]: 1

In [11]: s.read(10)
Out[11]: 'Nina\r\n'
```

