# What
Thi is an application testing my out-of-tree module for Zephyr RTOS.
* The out of tree module (driver) [is here](https://github.com/iwasz/example-zephyr-module).
* A blog post on this subject is [here](https://iwasz.pl/electronics/2021-06-18-out-of-tree-zephyr-module.md/).


Copied from `zephyr/samples/sensor/lsm6dsl`. The only modifications are : 
* `boards` dir with an overlay for H743ZI. It defines a LSM6DS3 accelerometer.
* LSM6DS**L** changed to LSM6DS**3** in 3 places.

# Compile
```sh
cmake -B build -G Ninja -DBOARD=nucleo_h743zi -DBOARD_ROOT=. -DZEPHYR_EXTRA_MODULES=~/my-zephyr-module .
ninja -C build
west flash
```
# Connections
I used nucleo_h743zi, and I provided an overlay for it. You can use any other target supported by Zephyr.


| LSM6DS3 | nucleo_h743zi |
| ------- | ------------- |
| SDA     | PB11          |
| SCL     | PB10          |
| INT1    | PD11          |
