**SolaX cloud for Home assistant**
*Based on version 2 of the API*

This Home Assistant reads data from Solax cloud via official API V2 based on document 1.1. I started it to improve the V1 from which this is a fork. But I ended up changing a lot.
Differences with lowprize is that these are all sensors under RESTful API, and grouped. The sensors have the full config of type of measurement so they can be used in the energy overview of Home Assistant.
Sensors don´t return 0.00 when there is no value. If there is no data, it should leave a gap and let HA fix it. Using 0 means that 0 is measured, that is not the case.
Tested on X3 Gen3

Requirements
- Serial number of inverter (Where to find? Read official Solax Docs bellow)
- Token ID: https://www.solaxcloud.com/#/api

Install:
- Edit *secrets.yaml*  (see secrets.yaml.sample)
- create "rest" directory in config directory (config/sensors/)
- edit configuration (see configuration.yaml.sample)

Notes:
- The total yield is not clear. On the cloud and app the value of total yield is lower than the total yield in the API. If you check the total yield in the site statistics, this is the correct value.
- Not all value are read. Most values likve voltage, current of each seperate PV is not send. Even though it is documented. Please comment sensors you don't need.
I am trying to get support from Sola about this.


[Official API Documentation v1.1](https://global.solaxcloud.com/blue/4/user_api/2024/SolaXCloud_User_API_V2.pdf)


This is the first commit. Further commits will have a better Readme.
