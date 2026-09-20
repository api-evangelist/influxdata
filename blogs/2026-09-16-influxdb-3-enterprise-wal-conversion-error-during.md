---
title: "InfluxDB 3 Enterprise WAL conversion error during historical writes, without triggers"
url: "https://community.influxdata.com/t/influxdb-3-enterprise-wal-conversion-error-during-historical-writes-without-triggers/58723#post_1"
date: "2026-09-16"
author: "@i.mayson"
feed_url: "https://community.influxdata.com/posts.rss"
---
We use InfluxDB 3 Enterprise with an at-home licence, packaged as Home Assistant app 1.1.3 on Raspberry Pi 5. The app maintainer’s changelog identifies Enterprise 3.11.4; the running binary version has not been independently confirmed. The maintainer directed us to InfluxData: InfluxDB3 Enterprise processing-engine WAL conversion error with no configured triggers · Issue #63 · erik73/app-influxdb3 · GitHub During bounded historical migration from InfluxDB 1 through /api/v3/write_lp, the server repeatedly logs: influxdb3_processing_engine::ent::wal: failed to convert WalFlushTableData to Record
