---
title: "Telegraf parsing/processing JSON data (dynamic field name)"
url: "https://community.influxdata.com/t/telegraf-parsing-processing-json-data-dynamic-field-name/58447#post_5"
date: "2026-06-04"
author: "@00fake"
feed_url: "https://community.influxdata.com/posts.rss"
---
Thank you for this solution and different approach. Meanwhile I expanded the code of the starlark processor with different (if/else) conditions and additional logging to indentify wrongly named devices to drop their metric in order to not “destroy” the database scheme and report the issue to me. Unfortunately this can’t be solved with xpath .
