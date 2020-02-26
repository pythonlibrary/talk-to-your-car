# talk-to-your-car
An example of sending and receiving CAN messages using python-can library

## virtual_bus.py 

It uses the [python-can](https://python-can.readthedocs.io/en/stable/index.html) built-in virtual bus to simulate the sending and receiving. It doesn't require any CAN hardware. It will send random data with ID 0x7E0 on the virtual bus in a thread every 0.5 second, and the receiver nofitier will print the received messages to the console and write them to the asc log file using built-in can.Logger notifier

## neovi_bus.py

It basically does the same thing as virtual_bus.py, except It requires a real CAN hardware (which is an Intrepid device, probably valueCAN3, or other) . It will send random data on the real bus, so the CAN hardware needs to connect to somewhere (which is another CAN hardware). It will also receive the messages from outside device and save them to asc file

In order to use this file, additional library(python) and drivers(CAN hardward) need to be installed. The guide on how to install can be found on [python-ics](python-ics.readthedocs.io)

## other CAN hardware 

python-can supports lots of CAN hardware including Vector, Kvaser, PCAN, etc. details can be found in Its doc.

