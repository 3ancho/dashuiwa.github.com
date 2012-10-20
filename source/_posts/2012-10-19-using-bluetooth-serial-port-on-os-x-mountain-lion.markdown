---
layout: post
title: "Using Bluetooth Serial Port on OS X Mountain Lion"
date: 2012-10-19 00:38
comments: true
categories: arduino, python
---
#### Using Bluetooth Serial Port on OS X Mountain Lion

I am taking a robotics class, and simply wants to play with the bluetooth module. Maybe create a robot later to play with my cats?

So I will send a character "r" to arduino via bluetooth, and the program running on arduino will respond "Nina" as soon as it got the "r". 

#### Procedures


* Find the bluetooth, the name of device is AC, for some unknown reason.

{% img /images/bluetooth/find.png %}

* Pair with it, the pairing code is 0000 in my case.

{% img /images/bluetooth/pair.png %}

* The underlined part have some config to play with. The general idea is to use serial port service.

{% img /images/bluetooth/config.png %}

* `Serial.println()` in arduino will write data to the pin1 (TX) and also to the USB cable. So you could compare your data received via bluetooth serial port with the data received via USB serial port. My usb serial port is `/dev/tty/usbmodemfa131`.  

{% img /images/bluetooth/arduino.png %}

* The image below shows the display while using GNU `screen`

{% img /images/bluetooth/result.png %}


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

