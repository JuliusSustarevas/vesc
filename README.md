# About

This repo is a fork from  https://github.com/sbgisen/vesc

## Additions:
- vesc_hw_interface
    - now includes a combined hardware interface for multiple vescs
    - now also publishes vesc driver state message. Rate of publication is controlled via param state_pub_rate (default 10 (Hz))
    - now includes pole_pair parameter for computing eprm (default 1.0 )
    - now has a explicit duty limit parameter duty_limit (default 0.5). This is as sometimes motors are given much more voltage that they are rated for and should not cross some threshold. E.g. input voltage 48v, rated voltage 24v. setDutyCycle should not cross 0.5.
    - now has an explicit erpm_limit parameter that, for ease of mind, sets a very explicit max erpm command.  The default value is 0, which means unless you specify a reasonable range - it will not work.  This is for those, like me, who want to make sure they do not burn any hardware. 

# VESC
## ROS Interfaces for VESC Motor Drivers

<!-- TODO: CI setting -->

## Composition
This repository is composed as follows:

- `vesc` is a meta package to manage the other packages.
- `vesc_driver` is the main library to drive VESCs.
- `vesc_hw_interface` wraps `vesc_driver` as a hardware interface to use `ros_control` systems.
- `vesc_msgs` defines messages to publish VESC status.

## License
This repositry is licensed under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0.html).

## Note
A part of these packages had been developed by Michael T. Boulet at MIT under the BSD 3-clause License until Dec. 2016 in the repository named [mit-racecar/vesc](https://github.com/mit-racecar/vesc). Since Nov. 2019, Softbank Corp. takes over development as new packages.
