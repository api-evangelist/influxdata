---
name: Write time series data to InfluxDB
description: Authenticate, resolve or create a bucket, then write line-protocol points to InfluxDB Cloud/OSS.
api: openapi/influxdata-cloud-openapi-original.yml
operations: [GetBuckets, PostBuckets, PostWrite]
---

# Write time series data to InfluxDB

Use the InfluxDB v2 `/api/v2` API to write time series data.

## Auth
Every request sends `Authorization: Token <INFLUX_API_TOKEN>`. See `authentication/influxdata-authentication.yml`.

## Steps
1. **Find the bucket** — `GetBuckets` (`GET /buckets?org=<org>`). If it does not exist, create it with `PostBuckets` (`POST /buckets`, body includes `orgID`, `name`, `retentionRules`).
2. **Write points** — `PostWrite` (`POST /write?org=<org>&bucket=<bucket>&precision=ns`). Body is line protocol, e.g. `cpu,host=server01 usage=0.64 1700000000000000000`. Content-Type is `text/plain`.
3. Check the response: `204` on success; on `400` inspect the `Error.message` (bad line protocol), `413` means the batch is too large (split it), `429` means slow down and honor `Retry-After`.

## Conventions
- No idempotency key: a point is identified by measurement + tag set + timestamp, so re-writing the same point overwrites it (last-write-wins). See `conventions/influxdata-conventions.yml`.
- Errors follow `errors/influxdata-problem-types.yml`.
