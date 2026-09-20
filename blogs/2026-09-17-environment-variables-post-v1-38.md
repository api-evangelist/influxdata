---
title: "Environment variables post v1.38"
url: "https://community.influxdata.com/t/environment-variables-post-v1-38/58726#post_2"
date: "2026-09-17"
author: "@sebastianthorn"
feed_url: "https://community.influxdata.com/posts.rss"
---
The same goes for int. E! loading config file /etc/telegraf/telegraf.conf failed: error parsing data: line 77: invalid TOML syntax # cat -n /etc/telegraf/telegraf.conf 77 metric_version = ${PROMETHEUS_MONITOR_METRIC_VERSION} # env | grep PROMETHEUS_MONITOR_METRIC_VERSION PROMETHEUS_MONITOR_METRIC_VERSION=1
