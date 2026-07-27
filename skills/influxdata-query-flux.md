---
name: Query InfluxDB with Flux
description: Run a Flux query against InfluxDB and read the annotated-CSV result.
api: openapi/influxdata-cloud-openapi-original.yml
operations: [PostQuery]
---

# Query InfluxDB with Flux

## Auth
`Authorization: Token <INFLUX_API_TOKEN>`.

## Steps
1. **Run the query** — `PostQuery` (`POST /query?org=<org>`). Body: `{"query": "from(bucket:\"my-bucket\") |> range(start: -1h)", "type": "flux"}`, Content-Type `application/json`.
2. The response is annotated CSV (`Accept: application/csv`). Parse the header annotations (`#datatype`, `#group`, `#default`) to type the columns.
3. On `422` the Flux is semantically invalid — inspect `Error.message`. On `429` back off and retry.

## Notes
- `PostQueryAnalyze` and `PostQueryAst` help validate/parse Flux before running it.
- InfluxDB 3 additionally supports SQL and InfluxQL over the v3 query API.
