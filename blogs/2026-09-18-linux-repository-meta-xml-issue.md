---
title: "Linux repository Meta XML issue"
url: "https://community.influxdata.com/t/linux-repository-meta-xml-issue/58728#post_3"
date: "2026-09-18"
author: "@jeffreyhodge"
feed_url: "https://community.influxdata.com/posts.rss"
---
We’re experiencing this as well. The repomd.xml file has a different date than the other files which mean it was not generated with the same “createrepo .” command. Someone just needs to rerun “createrepo .” in that repository.
