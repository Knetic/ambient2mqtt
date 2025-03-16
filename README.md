Ambient2MQTT
============

Originally by Patrick Wagstrom &lt;patrick@wagstrom.net&gt;, 2021-10

Updated for ws-2902d and influx documentation in 2025-03

Overview
---------

This is a simple single binary server that acts as a target for your Ambient Weather station on your local network and relays the data over MQTT so other IoT related devices can make use of it.

You will need to have a newer firmware installed for your Ambient Weather station in order to make use of this feature.

Usage
-----

```bash
./ambient2mqtt -config config.toml
```

Configuration
-------------

Configuration is done via a TOML file. Here's a simple example configuration:

```toml
[http]
    port = 2466

[mqtt]
    broker_host = "mqtt-broker.lan"
    broker_port = 1883
    broker_username = ""
    broker_password = ""
    client_id = "ambient2mqtt"
    topic_prefix = "weather"
    topic = "ws-2902"

[hass]
    discovery = true
    discovery_prefix = "homeassistant"
    object_id = "ws-2902d"
    device_model = "ws-2902d"
    device_name = "ws-2902d"

[influx]
    Hostname = "localhost"
    Port = 8086
    Database = "ambientweather"

```
