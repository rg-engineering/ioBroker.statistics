![Logo](admin/statistics.png)
# ioBroker.statistics

[![NPM version](http://img.shields.io/npm/v/iobroker.statistics.svg)](https://www.npmjs.com/package/iobroker.statistics)
[![Downloads](https://img.shields.io/npm/dm/iobroker.statistics.svg)](https://www.npmjs.com/package/iobroker.statistics)
[![Build Status](https://travis-ci.org/foxthefox/iobroker.statistics.svg?branch=master)](https://travis-ci.org/foxthefox/iobroker.statistics)

[![NPM](https://nodei.co/npm/iobroker.statistics.png?downloads=true)](https://nodei.co/npm/iobroker.statistics/)

## Description
This adapter will make the configuration of statistics more easier.

`The adapter only reacts on state changes (state.ack=true), not on commands!`

choose from the following settings:

* count impulses or on/off changes (Only for binary values and positive edge)
* calculate costs from the counted values (Only for binary values)
* how long was status true/ON and how long false/OFF (Only for binary values)
* delta between logged analogue values (Only for analog values)
* daily max, min and average (Not for delta calculations)
* counts within 5 min and daily max, min and average of it (Not for delta calculations)
* sum up of grouped values

The adapter subscribes to the configured objects and creates his own states in the statistics tree.

2 separate trees are created:
* statistics.0/save -> final stored values of the time frame
* statistics.0/temp -> temporary values through the day

after save or temp the original object is kept (unfortunately it is split by the "." in a deeper structure than needed.

A german HowTo doc is available here: [howto_de](./doc/howto_de.md)

## Settings
* specify the relevant groups in the instance configuration page (admin => instances => statistics config)
* specify the configuration in the settings of the state (admin => objects)

## Changelog
### 0.1.3
* (foxthefox) german doc added
* (foxthefox) error corrections

### 0.1.2 [2018-09-08]
* (bluefox) total refactoring

### 0.0.3
* admin3 implemented
* complete rewrite to have configuration through the settings of the individual states instead in admin page

### 0.0.2
* setup running

### 0.0.1
* initial release 

## License

The MIT License (MIT)

Copyright (c) 2018 foxthefox <foxthefox@wysiwis.net>,
                   bluefox <dogafox@gmail.com>
