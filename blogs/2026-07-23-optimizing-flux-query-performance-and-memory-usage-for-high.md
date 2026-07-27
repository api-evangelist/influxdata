---
title: "Optimizing Flux query performance and memory usage for high-cardinality downsampling tasks"
url: "https://community.influxdata.com/t/optimizing-flux-query-performance-and-memory-usage-for-high-cardinality-downsampling-tasks/58649#post_1"
date: "2026-07-23"
author: "@Maaz"
feed_url: "https://community.influxdata.com/posts.rss"
---
Hi everyone, I am working on optimizing a set of data processing and downsampling tasks in InfluxDB and running into a performance bottleneck when handling high-cardinality time-series data. Current Setup: InfluxDB version managing high-frequency sensor and metric streams. Running scheduled Flux tasks to aggregate raw data into hourly and daily rollups.
