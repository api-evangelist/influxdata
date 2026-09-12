---
title: "Replication service for Influxdb 3.0"
url: "https://community.influxdata.com/t/replication-service-for-influxdb-3-0/58629#post_4"
date: "2026-06-29"
author: "@cbowden"
feed_url: "https://community.influxdata.com/posts.rss"
---
This is an entirely different implementation. The end result should be relatively the same, but this is via the InfluxDB 3 processing engine, which is a Python VM embedded within the database. Writes are somewhat durable because of the presence of a write-ahead log that can be read from after a reboot if something goes down, but I wouldn’t say this is identical to the idea of a durable message queue.
