---
title: "Error while defining location parameter for aggregateWindow"
url: "https://community.influxdata.com/t/error-while-defining-location-parameter-for-aggregatewindow/24433#post_12"
date: "2026-06-29"
author: "@cbowden"
feed_url: "https://community.influxdata.com/posts.rss"
---
Ah, yeah, that’ll do it. In case anyone else comes across this thread, use set if you’re setting the environment variable via a terminal/command line interface. If you use a UI or are editing a file that stores environment variables, you can just specify the variable directly.
