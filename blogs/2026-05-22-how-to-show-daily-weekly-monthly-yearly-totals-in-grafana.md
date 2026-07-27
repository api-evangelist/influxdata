---
title: "How to show daily/weekly/monthly/yearly totals in Grafana with InfluxDB Cloud Serverless?"
url: "https://community.influxdata.com/t/how-to-show-daily-weekly-monthly-yearly-totals-in-grafana-with-influxdb-cloud-serverless/58531#post_3"
date: "2026-05-22"
author: "@agedekoek"
feed_url: "https://community.influxdata.com/posts.rss"
---
Yeah, I already implemented something similar, but I was wondering if there’s a more native approach. Once you start adding custom code for this kind of setup, it becomes messy pretty quickly. In my case, the project is dockerized and gets deployed multiple times with some custom configuration each time, so I’m trying to keep the repository as clean and maintainable as possible.
