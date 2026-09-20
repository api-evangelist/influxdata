---
title: "BucketService::getBuckets() does not return all buckets for an organization (influxdb-client-php)"
url: "https://community.influxdata.com/t/bucketservice-getbuckets-does-not-return-all-buckets-for-an-organization-influxdb-client-php/34760#post_5"
date: "2026-09-15"
author: "@seb"
feed_url: "https://community.influxdata.com/posts.rss"
---
For me, changing the token did not solve the issue. In my Go project, I resolved the problem by using a custom query instead of BucketsAPI() . Before: func (r *Reader) GetBuckets() []string { if r.client == nil { return nil } buckets, err := r.client.BucketsAPI().GetBuckets(context.Background()) if err != nil { sentry.CaptureException(err) log.Fatal(err) } result := make(\[\]string, len(\*buckets)) for i, bucket := range \*buckets { result\[i\] = bucket.Name } return result } After: func (r *Reader) GetBuckets() ([]string, error) { if r.client == nil { return nil, fmt.Errorf("client not initia
