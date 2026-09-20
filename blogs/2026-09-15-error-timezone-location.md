---
title: "Error timezone.location"
url: "https://community.influxdata.com/t/error-timezone-location/58234#post_3"
date: "2026-09-15"
author: "@JeroenVH"
feed_url: "https://community.influxdata.com/posts.rss"
---
Found the solution — I sent Claude through the Flux source code to work out what was actually going on, and @CZvacko was right about the cause. timezone.location() doesn’t use Go’s standard time.LoadLocation , it uses Flux’s own fork in internal/zoneinfo . That fork reads the IANA files from disk, and its list of search paths ( zoneSources ) is only compiled in on Unix-like builds.
