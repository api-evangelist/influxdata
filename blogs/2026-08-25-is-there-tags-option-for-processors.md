---
title: "Is there \"tags\" option for processors?"
url: "https://community.influxdata.com/t/is-there-tags-option-for-processors/58684#post_5"
date: "2026-08-25"
author: "@JeroenVH"
feed_url: "https://community.influxdata.com/posts.rss"
---
I use multiple inputs (opcua_listener, MQTT, modbus, mock,…) and they all get routed through some processors to align their behavior. The main reason for my question is that I wanted to add a tag to a metric for debugging purposes at the time. Instead of adding them in the Starlark script, I wanted to do this in the configuration of the processor.
