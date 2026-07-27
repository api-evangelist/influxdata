---
title: "InfluxDB Connection Refused inconsistently"
url: "https://community.influxdata.com/t/influxdb-connection-refused-inconsistently/58509#post_2"
date: "2026-05-20"
author: "@cbowden"
feed_url: "https://community.influxdata.com/posts.rss"
---
There’s a couple possible thoughts that come to mind: You’re running pre-existing instances of InfluxDB on the servers that are failing, causing the default port to be unavailable. Even with the same code, if a port is already occupied, the InfluxDB instance will increment to the next available port, which would cause an error as you try to connect to some prior instance. The servers that aren’t working have a poor network connection.
