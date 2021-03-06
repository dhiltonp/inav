# INAV - navigation capable flight controller

![INAV](http://static.rcgroups.net/forums/attachments/6/1/0/3/7/6/a9088858-102-inav.png)
![Travis CI status](https://travis-ci.org/iNavFlight/inav.svg?branch=master)

## Fork Features

* iNav 1.9.1, with a couple of patches applied.
* CC3D and OLIMEXINO targets can be compiled (`./build.sh CC3D`).
* NAZE32, PORT103R, OLIMEXINO, EUSTM32F103RC, CRAZEPONYMINI and CJMCU are enabled, but do not compile due to [this pr](https://github.com/iNavFlight/inav/pull/2290). As I have a CC3D, I didn't bother fixing the issues.

Why use 1.9.1 instead of upstream's 1.7.3?

*FPort*

Note that the default targets ROM sizes are too large:

https://github.com/iNavFlight/inav/wiki/Building-custom-firmware

If no barometer is needed, disable USE_BARO in `src/main/target/$TARGET/target.h` and you'll have enough space.

A list of devices that can be enabled is in `src/main/drivers/bus.h`.

If using a bin instead of a hex file (OPBL=yes), lots of slimming will be necessary; I removed support for barometers, magnetometers, all unused telemetry and rx protocols plus a little extra.


## Features

* Outstanding navigation performance out of the box
* Position Hold, Altitude Hold, Return To Home and Missions
* Excellent support for fixed wing UAVs: airplanes, flying wings 
* Pitot tube support
* Rangefinder support (sonar and laser)
* Oneshot and Multishot ESC support.
* Blackbox flight recorder logging (to onboard flash or external SD card).
* Support for more than 8 RC channels - (e.g. 16 Channels via FrSky X4RSB SBus).
* Support for N-Position switches via flexible channel ranges - not just 3 like baseflight or 3/6 in MultiWii
* Lux's new PID (uses float values internally, resistant to looptime variation).
* Simultaneous Bluetooth configuration and OSD.
* Better PWM and PPM input and failsafe detection than baseflight.
* Better FrSky Telemetry than baseflight.
* LTM Telemetry.
* Smartport Telemetry.
* RSSI via ADC - Uses ADC to read PWM RSSI signals, tested with FrSky D4R-II and X8R.
* OLED Displays - Display information on: Battery voltage, profile, rate profile, version, sensors, RC, etc.
* In-flight manual PID tuning and rate adjustment.
* Rate profiles and in-flight selection of them.
* Multiple simultaneous telemetry providers.
* Configurable serial ports for Serial RX, Telemetry, MSP, GPS - Use most devices on any port, softserial too.
* Multi-color RGB LED Strip support (each LED can be a different color using variable length WS2811 Addressable RGB strips - use for Orientation Indicators, Low Battery Warning, Flight Mode Status, etc)
* PIDs from CF/BF can be used in INAV, no need to retune for INAV
* And many more minor bug fixes.

For a list of features, changes and some discussion please review the thread on RCGroups forums and consult the documentation.

## Tools

### INAV Configurator

Official too for INAV can be downloaded [here](https://github.com/iNavFlight/inav-configurator/releases). It can be run on Windows, MacOS and Linux machines and standalone application.  

### INAV Blackbox Explorer

Tool for Blackbox logs analysis is available [here](https://github.com/iNavFlight/blackbox-log-viewer/releases)

### Telemetry screen for OpenTX

Users of FrSky Taranis X9 and Q X7 can use INAV Lua Telemetry screen created by @teckel12 . Software and installation instruction are available here: [https://github.com/iNavFlight/LuaTelemetry](https://github.com/iNavFlight/LuaTelemetry)

## Installation

See: https://github.com/iNavFlight/inav/blob/master/docs/Installation.md

## Documentation, support and learning resources

* [Official documentation](https://github.com/iNavFlight/inav/tree/master/docs)
* [Official Wiki](https://github.com/iNavFlight/inav/wiki)
* [Slack channel](https://inavflight.signup.team/)
* [RC Groups Support](https://www.rcgroups.com/forums/showthread.php?2495732-Cleanflight-iNav-(navigation-rewrite)-project)
* [Video series by Painless360](https://www.youtube.com/playlist?list=PLYsWjANuAm4qdXEGFSeUhOZ10-H8YTSnH)
* [Video series by Paweł Spychalski](https://www.youtube.com/playlist?list=PLOUQ8o2_nCLloACrA6f1_daCjhqY2x0fB)

## Contributing

Contributions are welcome and encouraged.  You can contribute in many ways:

* Documentation updates and corrections.
* How-To guides - received help?  help others!
* Bug fixes.
* New features.
* Telling us your ideas and suggestions.

The best place to start is the IRC channel on freenode (see above), drop in, say hi. Next place is the github issue tracker:

https://github.com/iNavFlight/inav/issues

https://github.com/iNavFlight/inav-configurator/issues

Before creating new issues please check to see if there is an existing one, search first otherwise you waste peoples time when they could be coding instead!

## Developers

Please refer to the development section in the [docs/development](https://github.com/iNavFlight/inav/tree/master/docs/development) folder.


## INAV Releases
https://github.com/iNavFlight/inav/releases
