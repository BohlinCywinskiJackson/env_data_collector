# Data Collector

This repository will house the software and hardware decisions required to turn a RaspberryPi3 into the collection device for a deployment of data sensors.

Any number of sensor devices can be deployed to a site at either pre- or post-construction.
This would allow for the collection of existing conditions to be measured and improved or for the collection of post-occupancy data to determine if the construction is meeting design objectives and requirements.

## Device Responsibilities

At it's core, this device will need to provide basic MQTT broker functions to collect data between the various sensors being deployed.

It should also though be able to deploy a masked SSID wifi network to which the sensor devices can use to connect to the broker.
This will keep the sensor data transfer off of the Owner's WiFi network and keep the deployment self-contained.

The collector will also be responsible for aggregating and sorting the incoming data to be use on external devices.
The working thought is to append incoming data to a running *.csv file until the data is able to be offloaded from the device.
This keeps the device from having to "phone home", but means that analysis of the data is unable to occur until it's picked up.
It also had the unfortunate affect of not knowing if there is an issue until you try to open the *.csv file.

An alternate solution may be to stream the data out of the network, but to *also* store it in a *.csv for archival purposes.

## Moving forward

I'm sure that there are other functions for this device.
Currently, it's the most expensive piece of the setup and is probably the most under-used.

As the project develops, we'll have to keep a mindful eye opened to how else we are able to offload functions to this otherwise idle device.
