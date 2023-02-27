











# ASUS WMI


## Battery

### Max Battery Charge Limit

ASUS_WMI_DEVID_RSOC   0x00120057

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00120057, Value)




## Fans and Thermal
  
### Current `Cpu` And `Gpu` Fan Speed



((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110013).device_Status - 0x10000) * 0x64

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110014).device_Status - 0x10000) * 0x64 

#### Or (Depends On The Laptop)

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110013).device_Status) * 0x64

((Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DSTS(0x00110014).device_Status) * 0x64

#### Thanks Mochaneko!

### Throttle Thermal Policy

ASUS_WMI_DEVID_THROTTLE_THERMAL_POLICY   0x00120075

Values: 0 - Default, 1 - Overboost, 2 - Silent.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00120075, Value)

### Fan Boost Mode

ASUS_WMI_DEVID_FAN_BOOST_MODE   0x00110018

Values: 0 - Normal, 1 - Overboost, 2 - Silent.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00110018, Value)


### Fan Control

~~ASUS_WMI_DEVID_FAN_CTRL   0x00110012 **(Deprecated)**~~

~~Values: 1 - Low Speed, 2 - Medium Speed, 3 - High Speed.~~

### Cpu Fan Control

ASUS_WMI_DEVID_CPU_FAN_CTRL   0x00110013

Values: 0 - Auto, 1 - Fullspeed.


(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00110013, Value)


### Gpu Fan Control

ASUS_WMI_DEVID_GPU_FAN_CTRL   0x00110014

Values: 0 - Auto, 1 - Fullspeed.


(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00110014, Value)


## Panel Overdrive

ASUS_WMI_DEVID_PANEL_OD   0x00050019       
   
Values: 0 - Disable, 1 - Enable.


(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00050019, Value)


## Gpu settings


### Mux Switch

ASUS_WMI_DEVID_GPU_MUX   0x00090016

Values: 0 - dGpu, 1 - iGpu.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00090016, Value)


### Enable/Disable dGpu

ASUS_WMI_DEVID_DGPU   0x00090020

Values: 0 - Enable, 1 - Disable.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00090020, Value)


### Enable/Disable eGpu

ASUS_WMI_DEVID_EGPU   0x00090019

Values: 0 - Enable, 1 - Disable.

(Get-WmiObject -Namespace root/WMI -Class AsusAtkWmi_WMNB).DEVS(0x00090019, Value)
