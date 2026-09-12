---
title: "Support `accept_partial` writes via `/api/v3/write_lp` endpoint for partial-failure resilience"
url: "https://community.influxdata.com/t/support-accept-partial-writes-via-api-v3-write-lp-endpoint-for-partial-failure-resilience/58431#post_2"
date: "2026-08-21"
author: "@AnshJ"
feed_url: "https://community.influxdata.com/posts.rss"
---
Hi, following up on this request. We’re currently seeing this issue in a high-throughput use case where a single schema/data error causes the entire batch to be rejected. We then have to process the records individually to identify the bad record and send it to DLQ, which has a significant impact on throughput.
