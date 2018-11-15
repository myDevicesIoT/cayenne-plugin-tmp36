# Cayenne TMP36 Plugin
A plugin allowing the [Cayenne Pi Agent](https://github.com/myDevicesIoT/Cayenne-Agent) to read data from a TMP36 sensor and display it in the [Cayenne Dashboard](https://cayenne.mydevices.com).

## Requirements
### Hardware
* [Rasberry Pi](https://www.raspberrypi.org).
* [TMP36](https://www.adafruit.com/product/165).
* An analog-to-digital converter and its associated plugin, e.g. an [MCP3XXX device](https://github.com/myDevicesIoT/cayenne-plugin-mcp3xxx).

### Software
* [Cayenne Pi Agent](https://github.com/myDevicesIoT/Cayenne-Agent). This can be installed from the [Cayenne Dashboard](https://cayenne.mydevices.com).
* [Git](https://git-scm.com/).

## Getting Started
1. Installation

   From the command line run the following commands to install this plugin.
   ```
   cd /etc/myDevices/plugins
   sudo git clone https://github.com/myDevicesIoT/cayenne-plugin-dht.git
   ```
   Install the ADC plugin following its installation instructions.

2. Setting the ADC and channel

   Specify the ADC device and channel number you are connecting the TMP36 to by modifying `init_args` under `TMP36` in the `cayenne-tmp36.plugin` file.
   The `adc` value should be set to `plugin_name:section` where `plugin_name` is the name of the ADC plugin file name and `section` is the section within that
   file that defines the ADC extension. For example, `cayenne-mcp3xxx:MCP`. The `channel` value should be set to the channel on the ADC device that the
   TMP36 is connected to.

3. Restarting the agent

   Restart the agent so it can load the plugin.
   ```
   sudo service myDevices restart
   ```
