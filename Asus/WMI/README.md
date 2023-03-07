











# ASUS WMI


## Battery

### Max Battery Charge Limit

Device_ID 0x00120057

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00120057, Value)




## Fans and Thermal
  
### Current `Cpu` `Gpu` `System` Fan Speed



((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110013).device_Status - 0x10000) * 0x64

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110014).device_Status - 0x10000) * 0x64 

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110031).device_Status - 0x10000) * 0x64

#### Or (Depends On The Laptop)

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110013).device_Status) * 0x64

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110014).device_Status) * 0x64

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110031).device_Status) * 0x64

##### Thanks Mochaneko for the help with (0x00110013 0x00110014).device_Status) * 0x64! 

### Throttle Thermal Policy

Device_ID 0x00120075

Values: 0 - Default, 1 - Overboost, 2 - Silent.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00120075, Value)

### Fan Boost Mode

Device_ID 0x00110018

Values: 0 - Normal, 1 - Overboost, 2 - Silent.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00110018, Value)


### Fan Control

Device_ID 0x00110012 **(Deprecated)**~~

~~Values: 1 - Low Speed, 2 - Medium Speed, 3 - High Speed.~~

### Cpu Fan Control

Device_ID 0x00110013

Values: 0 - Auto, 1 - Fullspeed.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00110013, Value)


### Gpu Fan Control

Device_ID 0x00110014

Values: 0 - Auto, 1 - Fullspeed.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00110014, Value)

## Display

### Panel Overdrive

Device_ID 0x00050019       
   
Values: 0 - Disable, 1 - Enable.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00050019, Value)


### Check Your Laptop For Panel OD Support

Device_ID 0x00050020

Device_Status Values:  4294967294 - Not Supported OD Panel, 65536 - Not Supported OD Panel, 65537 - Support OD panel.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00050020)


### BackLight Control

Device_ID 0x0005001e

Values 0 - One Zone, 1 - Multi-Zone.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x0005001e, Value)

## Gpu settings


### Mux Switch

Device_ID 0x00090016

Values: 0 - dGpu, 1 - iGpu.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00090016, Value)


### Enable/Disable dGpu

Device_ID 0x00090020

Values: 0 - Enable, 1 - Disable.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00090020, Value)


### Enable/Disable eGpu

Device_ID 0x00090019

Values: 0 - Disable, 1 - Enable.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00090019, Value)


### Is the eGpu connected to the device?

Device_ID 0x00090018

Values: 65536 - Not Connected, 65537 - Сonnected.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00090018)

##### Thanks to RomanYazvinsky (https://github.com/fumetsu0/Laptops/issues/2)
