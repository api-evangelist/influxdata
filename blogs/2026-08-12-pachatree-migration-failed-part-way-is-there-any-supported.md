---
title: "PachaTree migration failed part-way — is there any supported way to resume it?"
url: "https://community.influxdata.com/t/pachatree-migration-failed-part-way-is-there-any-supported-way-to-resume-it/58695#post_3"
date: "2026-08-12"
author: "@pradig"
feed_url: "https://community.influxdata.com/posts.rss"
---
Thanks @hiltontj — yes, retention is configured, and the hypothesis is half right: retention did delete those files. But not during the migration. Every retention-caused deletion here predates the upgrade by weeks to months, and the remaining five refs are in a database that had no retention at all.
