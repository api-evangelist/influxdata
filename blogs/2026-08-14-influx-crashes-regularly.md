---
title: "Influx crashes regularly"
url: "https://community.influxdata.com/t/influx-crashes-regularly/58696#post_5"
date: "2026-08-14"
author: "@atticus-sullivan"
feed_url: "https://community.influxdata.com/posts.rss"
---
Save report to check what data will be missing $ sudo influxd inspect report-tsm --data-path /var/lib/influxdb/engine/data > report.txt analyze what files are corrupt and move them elsewhere $ sudo influxd inspect verify-tsm --engine-path /var/lib/influxdb/engine Broken Blocks: 27 / 7235913, in 703.767274329s $ sudo influxd inspect verify-tsm --engine-path /var/lib/influxdb/engine -v 2>&1 | tee log $ awk '!/healthy$/ {sub(/:$/, "", $1); print $1}' log > unhealthy $ readarray -t array I’ll test tomorrow whether this actually helped as this takes time (in the past influx was fine for a couple of
