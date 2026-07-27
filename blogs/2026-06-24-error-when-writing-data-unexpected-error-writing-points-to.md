---
title: "Error when writing data : unexpected error writing points to database: [shard 2613] unexpected end of JSON input"
url: "https://community.influxdata.com/t/error-when-writing-data-unexpected-error-writing-points-to-database-shard-2613-unexpected-end-of-json-input/22883#post_6"
date: "2026-06-24"
author: "@seb"
feed_url: "https://community.influxdata.com/posts.rss"
---
Hi everyone, I’m not sure if this information will be helpful, but in my project I needed to restore a single bucket in Influx. After performing the restore through the Influx CLI, I was no longer able to write new data to the restored bucket because Influx kept returning the following error: Writing error: shard group X covering X to X has no shard I managed to solve the issue by following these steps: I created a new empty bucket, for example bucket_copy . Using the UI, I went to Data Explorer and copied all the data from the original bucket to the temporary bucket by running the following q
