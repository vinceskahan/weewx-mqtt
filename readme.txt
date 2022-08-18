mqtt - weewx extension that sends data to an MQTT broker
Copyright 2014-2020 Matthew Wall
Distributed under the terms of the GNU Public License (GPLv3)

vds fork notes:
 - look for my initials in mqtt.py for a one-liner patch
   that I needed to do here so that it uses float for the values.

   My memory is hazy but I 'think' it was needed so that my setup
   using telegraf to import into influxdb for a grafana dashboard
   saved the value as a number.   This is likely me not knowing how
   to set up telegraf appropriately to do it natively.

===============================================================================
Pre-Requisites

Install the MQTT python bindings

For python3:

  sudo pip3 install paho-mqtt

For python2:

  sudo pip install paho-mqtt

===============================================================================
Installation instructions:

1) download

wget -O weewx-mqtt.zip https://github.com/matthewwall/weewx-mqtt/archive/master.zip

2) run the installer:

wee_extension --install weewx-mqtt.zip

3) modify weewx.conf:

[StdRESTful]
    [[MQTT]]
        server_url = mqtt://username:password@example.com:1883

4) restart weewx

sudo /etc/init.d/weewx stop
sudo /etc/init.d/weewx start


===============================================================================
Options

For configuration options and details, see the comments in mqtt.py
